---
description: >-
  Where Hest Pools prices come from on Solana and on Robinhood Chain, how the
  15-minute TWAP is built, which price every fill uses, and when a market pauses.
---

# Hest Pools Pricing

Hest Pools markets have no order book. Every price is read directly from the token's **own DEX pool** at the moment it is needed, and every trade is filled at the price that is **worse for the trader** of two readings of that pool. This page describes both readings on both chains, the fill rule and the automatic pause.

## The Price Source

Each Hest Pools market is bound to one pool:

| Chain               | Pool                                               | Prices quoted in | Dollar values                          |
| ------------------- | -------------------------------------------------- | ---------------- | -------------------------------------- |
| **Solana**          | A PumpSwap pool pairing the token with SOL         | SOL per token    | × the live SOL/USD price               |
| **Robinhood Chain** | A Uniswap v3 pool pairing the token with WETH      | WETH per token   | × the live ETH/USD price               |

Live SOL and ETH prices come from Hyperliquid.

Three values are read on every open, every close and every engine run:

| Value             | On Solana                                                          | On Robinhood Chain                                                   | Used for                                         |
| ----------------- | ------------------------------------------------------------------ | -------------------------------------------------------------------- | ------------------------------------------------ |
| **Spot**          | The pool's two vault balances: SOL in the pool ÷ tokens in the pool | The pool's current tick (`slot0`), converted to a price             | Fill price, mark, pause check                    |
| **TWAP 15m**      | The average of Hest's own minute samples of spot over 15 minutes   | The pool's own price observations over the last 900 seconds (`observe`) | Fill price, mark, pause check                 |
| **DEX liquidity** | Twice the SOL held by the pool, valued in dollars                  | Twice the WETH held by the pool, valued in dollars                   | Position and open interest caps, market capacity |

### How the TWAP Is Computed on Robinhood Chain

Uniswap v3 pools store a cumulative sum of the price tick over time. Hest reads that sum now and 900 seconds ago, divides the difference by 900 to get the average tick over the window, and converts the tick to a price:

```
average tick = (tickCumulative[now] − tickCumulative[now − 900 s]) / 900
price        = 1.0001 ^ average tick   (adjusted for token decimals and pair order)
```

Because the average is taken over ticks (the logarithm of the price), the result is a **time-weighted geometric mean** of the price over the last 15 minutes. A price spike that lasts a few seconds moves it by a few seconds' worth of weight; holding the pool at a distorted price for minutes costs the manipulator the arbitrage losses for those minutes.

### How the TWAP Is Computed on Solana

Solana AMM pools keep no price history of their own: there is nothing on chain to read an average from. Hest therefore builds the average itself. Every minute, a Hest job reads the spot price of every Solana market from its pool and stores the sample. The TWAP is the average of the samples of the last 15 minutes.

```
TWAP = average of the minute samples taken in the last 15 minutes
```

It needs at least **12 samples** inside that window. If fewer exist, for example because the market is new or a sampling run was missed, the market has no TWAP and **cannot price a fill**: opening is refused and the market stays paused until the history is there again. Closing a position needs a TWAP too, so a market without one is frozen for everyone, Hest included, until sampling catches up.

The effect is the same as a pool oracle: a spike that lasts seconds barely moves a 15-minute average, and holding a pool away from its true price for minutes costs the manipulator the arbitrage. The difference is that the samples are taken by Hest once a minute rather than recorded continuously by the pool, so a very short spike between two samples is not in the average at all.

{% hint style="info" %}
Charts, 24h change and 24h volume on Hest Pools markets come from GeckoTerminal and are for display only. No trade, liquidation or take profit is ever priced from chart data.
{% endhint %}

## The Fill Rule

Every open and every close uses **whichever of spot and the 15-minute TWAP is worse for the trader**.

| Action                                        | Long                    | Short                   |
| --------------------------------------------- | ----------------------- | ----------------------- |
| Open                                          | higher of spot and TWAP | lower of spot and TWAP  |
| Close                                         | lower of spot and TWAP  | higher of spot and TWAP |
| Liquidation, take profit and stop loss checks | lower of spot and TWAP  | higher of spot and TWAP |

The price used to check a position for liquidation, take profit and stop loss (its **mark**) is the price it would close at right now. A position is never valued at a better price than it could actually be closed at.

### Why the Worse Price

A thin memecoin pool can be pushed for a few seconds, and a lagging average can be traded against after a fast move. Taking the worse of the two readings on both ends closes both doors:

* **Pushing spot** to open or close at a distorted price does not help, because the TWAP has not moved and the worse of the two is used.
* **Racing the TWAP** after a real move does not help either, because spot has already moved and, again, the worse of the two is used.

The cost to an honest trader is a wider effective spread than on a deep order book. When spot and TWAP agree, the spread is close to zero; after a fast move it can be several percent.

### Example

A token's pool shows **spot $0.0100** and **TWAP $0.0098**.

* A long opens at **$0.0100** (the higher). A short opens at **$0.0098** (the lower).
* Later spot is **$0.0118** and the TWAP **$0.0110**. The long closes at **$0.0110** (the lower), a gain of 10.0%. A short opened earlier would close at **$0.0118** (the higher).
* The interface shows both numbers at all times: **Spot** and **TWAP 15m** in the panel next to the chart, and the strip at the top of the trade page reads **Pricing: Worse of Spot / TWAP**.

## Automatic Pause

The gap between spot and TWAP is measured as:

```
deviation = |spot − TWAP| / TWAP
```

| Condition                                                  | Effect                                                                                                                 |
| ---------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Deviation above **10%**, at any open attempt or engine run | The market pauses. New positions are rejected with "The price is moving too fast. This market is paused for a moment." |
| Deviation back below **5%**, checked every minute          | An automatically paused market resumes by itself.                                                                      |

The gap between the two thresholds keeps a market from switching on and off while the price hovers around 10%.

While a market is paused:

* **Opening** new positions is not possible.
* **Closing** stays open: you can close at any time, at the worse of spot and TWAP as usual.
* **Liquidations, take profit and stop loss** keep running every minute.

Hest can also pause a market manually, with a reason that is shown on the trade page. A manually paused market only resumes when Hest resumes it.

## New Markets Without Price History

A new market always opens paused, with the reason **building its 15-minute price history**, and starts trading by itself about 15 minutes later once the TWAP can be read. How the history is built depends on the chain:

* **Solana:** Hest starts sampling the pool every minute as soon as the market is listed. After 15 minutes the TWAP exists and the market resumes on its own.
* **Robinhood Chain:** many young Uniswap v3 pools store only one price observation, which is not enough for a 15-minute TWAP. Anyone can ask a pool to store more history, and Hest does so when it opens such a market (the pool is set to keep up to 1,000 observations). The TWAP can then be read 15 minutes later.

## Read Next

* [How Hest Pools Work](how-hest-pools-work.md): a position from open to close, with numbers.
* [Leverage and Liquidation](../trading/leverage-and-liquidation.md): the liquidation formula on both venues.
* [Hest Pools Risks](hest-pools-risks.md): what the fill rule does not protect against.
