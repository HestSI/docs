---
description: >-
  What can go wrong on a Hest Pools market, for traders and for market owners,
  and what the rules do and do not protect against.
---

# Hest Pools Risks

Hest Pools markets trade the youngest and most volatile tokens on Hest, against Hest, on prices read from small DEX pools. Read this page before you trade one or apply to open one. The legal version is in the [Risk Disclosure](../legal/risk-disclosure.md).

## For Traders

### Memecoins Move Violently

A Robinhood Chain memecoin can halve or double in an hour, and many go to zero. With the 6% maintenance margin, liquidation sits only `100 / leverage − 6` percent away from entry:

| Leverage             | 1x  | 2x  | 3x     | 4x  | 5x  |
| -------------------- | --- | --- | ------ | --- | --- |
| Liquidation distance | 94% | 44% | 27.33% | 19% | 14% |

At 5x a 14% move against you, at the worse of spot and TWAP, liquidates the position, and liquidation also costs a 1% fee on the position value. Risk Shield compares this distance with the worst 1-hour candle of the past week before you trade; on young tokens that candle is often larger than 14%.

### The Engine Runs Once a Minute

Liquidation, take profit and stop loss are checked every minute, at the price of that minute. A fast market can move well past your liquidation price, stop loss or take profit before the next check, and the position is closed at the price of the check that catches it, not at your trigger. Take profit and stop loss are not guaranteed exit prices.

### The Price Comes From a DEX Pool

Prices come from the token's Uniswap v3 pool on Robinhood Chain. Taking the worse of spot and the 15-minute TWAP protects the market from short manipulation, but it also means:

* **A round trip costs more than the fees.** Fees are 0.30% to open and 0.30% to close; on top of that you pay the gap between spot and TWAP on both ends, which can be several percent after a fast move.
* **After a fast move the TWAP lags.** The price you get can be far from what a chart elsewhere shows. Charts on Hest Pools markets are for display; fills use spot and TWAP only.
* **The fill rule does not stop a sustained move.** Someone with enough capital can move a thin pool and hold it there for 15 minutes. Position and open interest caps tied to DEX liquidity limit what can be gained, but do not make it impossible.
* **The pool can fail.** If liquidity is pulled, the token is rugged or the pool is abandoned, the price can collapse faster than positions can be closed.

### Markets Can Pause

A market pauses automatically when spot and TWAP are more than 10% apart, and Hest can pause or close a market manually. While paused you cannot open positions; closing, liquidation, take profit and stop loss continue. A market can stay paused for as long as its price is unstable.

### Capacity Can Be Full

Each side of a market has an open interest limit. When it is reached, new positions on that side are rejected until others close. The limits also shrink when the pool's liquidity shrinks.

### Profits Are Paid After Review

Profits are credited to your Earnings balance, locked for 7 days, then reviewed and paid by Hest in WETH. Until they are paid they are not in your wallet. Profits that come from manipulation, linked accounts trading against each other, a breach of the [Terms](../legal/terms.md) or a faulty price can be withheld. Losses, by contrast, are settled the moment the position closes.

### Hest Is the Counterparty

On Hest Pools you trade against Hest, not against other traders. Your collateral sits in the Hest Pools collateral wallet while the position is open, the refund at close is sent by Hest, and payment of profits depends on Hest. Hest can change market parameters (leverage, capacity, caps, fees, maintenance margin) or stop a market.

### Collateral Is WETH, Fees Are ETH

Your margin is WETH. Its dollar value moves with the price of ETH, independently of the memecoin you trade, so a winning trade can still lose dollar value if ETH falls. Opening a position also needs a little ETH for Robinhood Chain network fees; without it, the collateral transfer cannot be sent and the position does not open.

## For Market Owners

### The Seed Is First-Loss

When traders on your market win overall, the loss comes out of your seed first. A strong one-way move on a hyped token can take a large part of the seed, or all of it. The 15% fee share and the 30% profit share are paid for carrying that risk; they do not remove it.

### Locked and Marked to Market

The seed is locked for 7 days from approval. After that, its value includes the unrealised profit and loss of open positions, so withdrawing while traders are winning locks in their gains against you. Withdrawing ends your shares in the market.

### One Token, No Diversification

A seed backs one market on one token. Nothing inside a market spreads the risk, and the token's own collapse can affect both the seed and the market's activity.

{% hint style="danger" %}
Only trade or seed with funds you can afford to lose entirely.
{% endhint %}
