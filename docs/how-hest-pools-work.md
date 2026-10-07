---
description: One Hest Pools position from open to close, with the exact sizing, fee, liquidation and settlement rules and a worked example.
---

# How Hest Pools Work

A Hest Pools market is a perpetual contract on a Robinhood Chain memecoin, settled against Hest. Collateral is **WETH** on Robinhood Chain, prices come from the token's Uniswap v3 pool (see [Hest Pools Pricing](hest-pools-pricing.md)), and every position is opened, monitored and closed by the Hest Pools engine. This page follows one position through its whole life.

## Parameters

| Parameter | Value |
| --- | --- |
| Collateral | WETH on Robinhood Chain |
| Leverage | 1x to 5x, whole numbers. A market can have a lower maximum, shown next to its name. |
| Opening fee | 0.30% of the order value |
| Closing fee | 0.30% of the position value at exit |
| Maintenance margin | 6% of the position value at entry |
| Liquidation fee | 1% of the position value at entry |
| Funding | None |
| Minimum margin | 0.002 WETH |
| Largest position | 10% of the market's capacity, and 2% of the token's DEX liquidity, whichever is lower |
| Open interest per side | 50% of the market's capacity, and 10% of the token's DEX liquidity, whichever is lower |
| Order types | Market, with optional take profit and stop loss |
| Engine cycle | Every minute: liquidations, take profit, stop loss, pause and resume |

## 1. Opening a Position

You choose the side, the leverage and the **order value** (the size of the position in dollars). The order panel converts it to WETH at the live ETH price and computes:

```
margin      = order value / leverage
opening fee = 0.30% × order value
you pay     = margin + opening fee
```

When you confirm, the engine runs these checks in order. If any fails, nothing is sent and the panel shows the reason.

1. The market is active (not paused or closed).
2. Leverage is between 1x and the market's maximum.
3. The margin is at least 0.002 WETH.
4. Spot and the 15-minute TWAP are read from the pool. If they are more than 10% apart, the market pauses and the order is rejected.
5. The position fits the caps: the position limit, and the open interest left on your side of the market.
6. The entry price is set: the higher of spot and TWAP for a long, the lower for a short.

The engine then sends **margin plus opening fee** in WETH from your [Trading Wallet](trading-wallet.md) to the Hest Pools collateral wallet, a Hest wallet used only for Hest Pools. If your Trading Wallet holds ETH but not enough WETH, the missing amount is wrapped from ETH first, and a small amount of ETH is always kept back for network fees. Opening is one or two Robinhood Chain transactions, paid in ETH from your Trading Wallet.

The position is open once the transfer is confirmed on Robinhood Chain, usually within seconds. One opening or closing per account runs at a time; a second request while the first is going through returns "Another trade is still going through. Wait a moment."

{% hint style="info" %}
If the collateral transfer is not confirmed within 5 minutes, the opening is marked as failed and no position exists. If the transfer did confirm, the position is opened by the engine on its next run.
{% endhint %}

## 2. While the Position Is Open

The position is valued at its **mark**: the price it would close at now, which is the lower of spot and TWAP for a long and the higher for a short. Every minute the engine reads each market's pool and checks every open position, in this order:

1. **Liquidation**, if the remaining margin has fallen to the maintenance margin.
2. **Take profit**, if set and the mark has reached it (long: mark at or above the price; short: at or below).
3. **Stop loss**, if set and the mark has reached it (long: mark at or below the price; short: at or above).

The first condition met closes the position at the mark of that run. Because checks run once a minute, a fast market can move past your trigger before the position is closed; the close happens at the price of the run that caught it, not at the trigger price.

Take profit and stop loss prices are stored in WETH per token. The dollar value shown next to them moves with ETH.

## 3. Closing a Position

You close from the **Positions** tab under the chart on the trade page. The exit price is the lower of spot and TWAP for a long and the higher for a short.

```
position value at exit = position value at entry × exit price / entry price
profit or loss (long)  = position value at entry × (exit price / entry price − 1)
profit or loss (short) = position value at entry × (1 − exit price / entry price)
closing fee            = 0.30% × position value at exit
```

| Result | Returned to your Trading Wallet at once | Credited to [Earnings](earnings.md) |
| --- | --- | --- |
| **Loss** | margin − loss − closing fee | nothing |
| **Profit** | margin − closing fee | the full profit, locked for 7 days, then reviewed and paid by Hest |

The refund is sent in WETH from the collateral wallet by Hest, so **closing costs you no network fee**. Losses and fees stay with Hest. Closing works even while a market is paused.

{% hint style="warning" %}
If the refund transaction cannot be sent at once, the position shows as closing and the engine retries every minute until the refund is confirmed on Robinhood Chain. The settlement amount is fixed at the moment you close and does not change while the refund is pending.
{% endhint %}

## 4. Liquidation

A position is liquidated when, at the mark:

```
margin + profit or loss ≤ 6% × position value at entry
```

which puts the liquidation price at:

```
long:  entry × (1 − (1 / leverage − 0.06))
short: entry × (1 + (1 / leverage − 0.06))
```

The liquidation distance is therefore `100 / leverage − 6` percent: 44% at 2x, 27.33% at 3x, 14% at 5x. The order panel shows the exact liquidation price before you confirm, and the Positions tab shows it while the position is open.

At liquidation the position is closed at the mark, the closing fee and a **liquidation fee of 1% of the position value at entry** are charged, and whatever margin remains is returned to your Trading Wallet. The return can never be negative: you cannot lose more than the collateral of the position.

## Worked Example

A **3x long** with **$500 of margin** on a token whose pool shows spot $0.0100 and TWAP $0.0098. Amounts are settled in WETH; dollar figures assume the ETH price does not move during the trade.

| Step | Calculation | Amount |
| --- | --- | --- |
| Order value | $500 × 3 | $1,500.00 |
| Opening fee | 0.30% × $1,500 | $4.50 |
| Sent from your Trading Wallet | $500 + $4.50 | $504.50 |
| Entry price | higher of $0.0100 and $0.0098 | $0.0100 |
| Liquidation distance | 100 / 3 − 6 | 27.33% |
| Liquidation price | $0.0100 × (1 − 0.2733) | $0.00727 |

{% tabs %}
{% tab title="Close in Profit" %}
Spot rises to $0.0118 and the TWAP to $0.0110. A long closes at the lower: **$0.0110**, +10.0%.

| | Calculation | Amount |
| --- | --- | --- |
| Profit | $1,500 × 10% | $150.00 |
| Position value at exit | $1,500 × 1.10 | $1,650.00 |
| Closing fee | 0.30% × $1,650 | $4.95 |
| Returned to your Trading Wallet now | $500 − $4.95 | $495.05 |
| Credited to Earnings, locked 7 days | | $150.00 |

Net result after both fees: $150 − $4.50 − $4.95 = **+$140.55**.
{% endtab %}

{% tab title="Close at a Loss" %}
Spot falls to $0.0090 and the TWAP to $0.0093. A long closes at the lower: **$0.0090**, −10.0%.

| | Calculation | Amount |
| --- | --- | --- |
| Loss | $1,500 × 10% | $150.00 |
| Position value at exit | $1,500 × 0.90 | $1,350.00 |
| Closing fee | 0.30% × $1,350 | $4.05 |
| Returned to your Trading Wallet now | $500 − $150 − $4.05 | $345.95 |

Net result: $345.95 − $504.50 = **−$158.55**.
{% endtab %}

{% tab title="Liquidation" %}
The mark (the lower of spot and TWAP) reaches **$0.00727** at an engine run.

| | Calculation | Amount |
| --- | --- | --- |
| Loss | $1,500 × 27.33% | $410.00 |
| Position value at exit | $1,500 × 0.7267 | $1,090.00 |
| Closing fee | 0.30% × $1,090 | $3.27 |
| Liquidation fee | 1% × $1,500 | $15.00 |
| Returned to your Trading Wallet now | $500 − $410 − $3.27 − $15 | $71.73 |

If the price gaps past the liquidation price between two engine runs, the loss is larger and the return smaller, down to zero.
{% endtab %}
{% endtabs %}

## Capacity and Caps

Every market has a **capacity**: the amount of open interest Hest is prepared to carry as counterparty. For markets opened through [Open a Market](open-a-market.md) it is set at 20% of the token's DEX liquidity, between $10,000 and $20,000, and fixed in WETH when the market opens. Hest can adjust it.

The caps are computed in WETH from the capacity and from the pool's current DEX liquidity:

| | Formula | Capacity $20,000, DEX liquidity $200,000 | Capacity $10,000, DEX liquidity $50,000 |
| --- | --- | --- | --- |
| Largest position | min(10% × capacity, 2% × DEX liquidity) | $2,000 | $1,000 |
| Open interest per side | min(50% × capacity, 10% × DEX liquidity) | $10,000 | $5,000 |

Positions count toward open interest at their value at entry, and positions still opening or closing count too. When a side is full, the panel shows how much is left; the trade page shows how much of each side is used. If DEX liquidity falls, the caps fall with it and new positions shrink accordingly; existing positions are not affected.

## Where You See It

* **Trade page:** Spot, TWAP 15m, Capacity and DEX Liquidity in the panel next to the chart, with long and short usage. The order panel shows the liquidation price, order value, margin, fee and route before you confirm.
* **Positions tab and Portfolio:** open Hest Pools positions with entry, mark, profit and loss, liquidation price and margin.
* **Earnings tab in Portfolio:** each credited profit with its unlock countdown and, once paid, a link to the transaction on robin.etherscan.io.

## Read Next

* [Hest Pools Pricing](hest-pools-pricing.md): spot, TWAP and the automatic pause.
* [Earnings](earnings.md): how profits are locked, reviewed and paid.
* [Hest Pools Risks](hest-pools-risks.md): read before you trade.
