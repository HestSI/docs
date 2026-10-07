# Leverage and Liquidation

## Leverage

Leverage multiplies your exposure: $100 of margin at 10x controls a $1,000 position. The maximum differs per market and is shown next to the market name:

* **Order Book markets**: set by Hyperliquid, from 3x on new listings to 40x on BTC.
* **Hest Pools markets**: up to 5x.

Choose it with the leverage control in the order panel. Presets show the common steps; the slider goes to the market maximum.

## Margin Modes (Order Book)

* **Cross**: all your free USDC backs all your cross positions. A losing position can draw on the rest of your balance before it is liquidated; a winning one supports the others.
* **Isolated**: only the margin you assign to this position is at risk. Liquidation comes sooner, but the rest of your balance is untouched.

## Liquidation

A position is liquidated when its margin falls to the **maintenance margin**. On Order Book markets Hyperliquid sets the maintenance margin at half of the initial margin at the market's maximum leverage: 1.25% on a 40x market, 16.7% on a 3x market.

Liquidation distance from entry, as a percentage of price:

`100 / leverage − maintenance margin`

| Leverage | BTC (40x max, 1.25% maintenance) | A 3x market (16.7% maintenance) |
| --- | --- | --- |
| 2x | 48.75% | 33.3% |
| 3x | 32.08% | 16.7% |
| 5x | 18.75% | – |
| 10x | 8.75% | – |
| 20x | 3.75% | – |
| 40x | 1.25% | – |

The order panel shows the exact liquidation price before you confirm, and [Risk Shield](risk-shield.md) tests that distance against the worst 1-hour candle of the past week.

## What Happens at Liquidation

* **Order Book**: Hyperliquid's clearing engine closes the position under Hyperliquid's rules. Any remaining margin stays in your Hyperliquid account.
* **Hest Pools**: the position is closed against Hest at the market's price, and any remaining collateral returns to your Trading Wallet.

{% hint style="warning" %}
Leverage cuts both ways. Hest shows you the numbers before every order; the maximum leverage is a ceiling, not a recommendation.
{% endhint %}
