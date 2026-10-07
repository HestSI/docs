---
description: How a Hest Pools market is priced, how big a position can be, and what happens to your collateral and profit when a position closes.
---

# How Hest Pools Work

A Hest Pools market is a perpetual contract on a Robinhood Chain memecoin, settled against Hest. This page walks through one position from open to close.

## The Price

Every Hest Pools market reads its price from the token's real **Uniswap pools on Robinhood Chain**. Two numbers are tracked all the time:

* **Spot**: the current pool price.
* **TWAP**: the 15-minute time-weighted average of that price.

Every open and every close uses **whichever of the two is worse for you**. A long opens at the higher of the two and closes at the lower; a short opens at the lower and closes at the higher.

This is deliberate. A thin memecoin pool can be pushed for a few seconds, and a lagging average can be traded against. Taking the worse of the two on both ends means neither trick pays: pushing the pool up to short at an inflated price, or racing the TWAP after a fast move, costs more than it can earn.

The trade-off for you is a wider effective spread than on a deep order book.

## Collateral and Fees

* **Collateral is WETH** on Robinhood Chain. Balances, margin and profit and loss are shown in WETH with their live dollar value, so the dollar value of your collateral also moves with the price of ETH.
* **Network fees are paid in ETH.** Keep a little ETH in your Trading Wallet: about $1 covers hundreds of transactions on Robinhood Chain.
* **Trading fee:** 0.30% of the position size to open and 0.30% to close.

## Leverage and Limits

* **Leverage** up to 5x.
* **Capacity.** Each market has a capacity based on the token's DEX liquidity. See [Open a Market](open-a-market.md) for how it is set.
* **One position** can use at most **10% of the market's capacity** and at most **2% of the token's DEX liquidity**, whichever is lower.
* **Open interest** per side (all longs together, all shorts together) is capped.

The limits keep any single trade small relative to the pool the price comes from.

## When a Position Closes

| Result | What happens |
| --- | --- |
| **Loss** | The loss is kept and the **remaining collateral returns to your Trading Wallet immediately**. |
| **Profit** | Your collateral returns to your Trading Wallet and the **profit is credited to your [Earnings](earnings.md) balance**. It is locked for 7 days, then reviewed and paid by Hest, with a transaction link. |

The 7-day lock and review are how Hest keeps markets on thin memecoins honest: profits that come from manipulation, linked accounts trading against each other or a broken price can be withheld.

## Automatic Pause

A market can **pause automatically** when its price moves abnormally, for example a sudden jump or a large gap between spot and TWAP. While a market is paused you cannot open new positions on it.

## Super Intelligence on Hest Pools

Every Hest Pools market has an SI Score, and Risk Shield compares your liquidation distance with the worst 1-hour candle of the past week before you trade. See [SI Score](si-score.md) and [Risk Shield](risk-shield.md).
