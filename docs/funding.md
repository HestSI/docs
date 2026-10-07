---
description: Hourly funding on Order Book markets, how a payment is calculated, how to read the rate, and why Hest Pools markets have none.
---

# Funding

A perpetual contract has no expiry, so something has to keep its price close to the underlying asset. On Order Book markets that mechanism is **funding**: a payment between longs and shorts every hour, set and settled by Hyperliquid. Funding is not a Hest fee; it flows between traders, and Hest takes no part of it.

## How It Works

* The rate is shown in the strip at the top of the trade page as **Funding / Countdown**, for example `0.0013% 32:05`: the current hourly rate and the time until the next payment, on the hour.
* The Markets table shows each market's hourly rate in the **Funding / 1h** column.
* **Positive rate:** longs pay shorts. The perpetual trades above the oracle price and the long side is crowded.
* **Negative rate:** shorts pay longs.
* The payment for one hour is:

```
funding payment = position size × oracle price × hourly rate
```

Payments are settled from your margin every hour, listed under **Funding History** on the trade page and in Portfolio, and included in the position's funding column.

## Worked Example

A **$10,000 long** on a market with a rate of **+0.0013% per hour**:

| Period | Calculation | Long pays |
| --- | --- | --- |
| 1 hour | $10,000 × 0.0013% | $0.13 |
| 8 hours | $0.13 × 8 | $1.04 |
| 24 hours | $0.13 × 24 | $3.12 |
| 30 days | $0.13 × 24 × 30 | $93.60 |

The same rate held for a year is about 11.4% of the position's value. At 10x leverage that is 114% of the margin over a year, which is why funding matters more the longer you hold and the higher your leverage. A short of the same size receives these amounts.

## Reading the Rate

About 0.0013% per hour (roughly 0.01% per 8 hours) is what a balanced market looks like on Hyperliquid. Rates several times higher, or a large negative rate, mean one side is crowded and paying to stay in, and crowded sides are the ones that get squeezed.

Super Intelligence uses this in two places:

* **SI Score:** the **Funding skew** factor scores how far the rate sits from neutral. See [SI Score](si-score.md).
* **Copilot:** answers which side is paying and what the current rate costs over 24 hours as a share of position size. See [Copilot](copilot.md).

## Hest Pools Markets

Hest Pools markets have **no funding**. Their price is not a separate perpetual price that needs anchoring: every open and close is priced directly from the token's Uniswap pool, at the worse of spot and the 15-minute TWAP. The strip on a Hest Pools trade page shows **Pricing: Worse of Spot / TWAP** where Order Book markets show funding. Holding a Hest Pools position costs nothing per hour; its costs are the opening and closing fees. See [Fees](fees.md).
