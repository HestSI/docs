---
description: >-
  Leverage limits, margin modes, the liquidation formula on Order Book and Hest
  Pools markets, and what happens to your margin at liquidation.
---

# Leverage and Liquidation

## Leverage

Leverage is position value divided by margin: $100 of margin at 10x controls a $1,000 position, and a 1% price move changes the position's value by $10, which is 10% of the margin. The maximum differs per market and is shown next to the market name and in the Markets table:

* **Order Book markets:** set by Hyperliquid per market, for example 40x on BTC and as low as 3x on new listings.
* **Hest Pools markets:** 1x to 5x, whole numbers. A market can have a lower maximum.

Choose it with the leverage control in the order panel. Presets show the common steps; the slider goes to the market maximum.

## Margin Modes (Order Book)

* **Cross:** all your free USDC backs all your cross positions. A losing position can draw on the rest of your balance before it is liquidated; a winning one supports the others.
* **Isolated:** only the margin assigned to this position is at risk. Liquidation comes sooner, but the rest of your balance is untouched.

Hest Pools positions are always isolated: each position has its own WETH margin and can lose at most that margin.

## Maintenance Margin

A position is liquidated when its margin, including unrealised profit and loss, falls to the **maintenance margin**.

| Venue      | Maintenance margin                                                                                                                                                            |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Order Book | Set by Hyperliquid: half of the initial margin at the market's maximum leverage, `1 / (2 × max leverage)`. 1.25% on a 40x market, 2.5% on a 20x market, 16.7% on a 3x market. |
| Hest Pools | 6% of the position value at entry, on every market.                                                                                                                           |

## Liquidation Distance

How far the price can move against a fresh position before it is liquidated, as a percentage of the entry price:

```
liquidation distance = 100 / leverage − maintenance margin %
```

{% tabs %}
{% tab title="Order Book" %}
| Leverage | BTC (40x max, 1.25%) | A 20x market (2.5%) | A 3x market (16.7%) |
| -------- | -------------------- | ------------------- | ------------------- |
| 2x       | 48.75%               | 47.5%               | 33.3%               |
| 3x       | 32.08%               | 30.83%              | 16.7%               |
| 5x       | 18.75%               | 17.5%               | –                   |
| 10x      | 8.75%                | 7.5%                | –                   |
| 20x      | 3.75%                | 2.5%                | –                   |
| 40x      | 1.25%                | –                   | –                   |

On cross margin the actual liquidation price also depends on your other positions and free balance, because they share the same margin. Hyperliquid's figure in the Positions tab is the authoritative one.
{% endtab %}

{% tab title="Hest Pools" %}
| Leverage | Liquidation distance | Liquidation price for a long entered at $0.0100 |
| -------- | -------------------- | ----------------------------------------------- |
| 1x       | 94%                  | $0.00060                                        |
| 2x       | 44%                  | $0.00560                                        |
| 3x       | 27.33%               | $0.00727                                        |
| 4x       | 19%                  | $0.00810                                        |
| 5x       | 14%                  | $0.00860                                        |

For a short, the liquidation price is the same distance above the entry. The distance is measured against the position's mark, which is the price it would close at: the lower of spot and TWAP for a long, the higher for a short.
{% endtab %}
{% endtabs %}

The order panel shows the exact liquidation price before you confirm, and [Risk Shield](../super-intelligence/risk-shield.md) tests the distance against the worst 1-hour candle of the past week.

## What Happens at Liquidation

{% tabs %}
{% tab title="Order Book" %}
Hyperliquid's clearing engine monitors the position continuously and closes it under Hyperliquid's rules, including its liquidation and auto-deleveraging mechanisms. Hest has no role in it. Any margin left after the liquidation stays in your Hyperliquid account.
{% endtab %}

{% tab title="Hest Pools" %}
The Hest Pools engine checks every open position once a minute. When `margin + profit or loss ≤ 6% × position value at entry` at the mark, the position is closed at that mark and settled:

```
returned = margin + profit or loss − closing fee − liquidation fee
closing fee     = 0.30% × position value at exit
liquidation fee = 1% × position value at entry
```

The return is sent in WETH to your Trading Wallet at once and can never be negative. Example: a 3x long with $500 of margin ($1,500 position) liquidated exactly at its liquidation price returns $500 − $410 − $3.27 − $15.00 = **$71.73**. If the price gaps past the liquidation price between two checks, the return is smaller, down to zero. See [How Hest Pools Work](../markets/how-hest-pools-work.md#worked-example).
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
Leverage cuts both ways. Hest shows you the numbers before every order; the maximum leverage is a ceiling, not a recommendation.
{% endhint %}
