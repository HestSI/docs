# Leverage and liquidation

## Leverage

Leverage multiplies your exposure: $100 of margin at 10x controls a $1,000 position. The maximum differs per market and is shown next to the market name:

* **Order book markets**: set by the book, from 3x on new listings to 40x on BTC.
* **Hest Pool markets**: set by Super Intelligence from the token's SI Score, 2x to 5x.

Choose it with the leverage dial in the order panel. Presets show the common steps; the slider goes to the market maximum.

## Margin modes

* **Cross** – all your free USDC backs all your cross positions. A losing position can draw on the rest of your balance before it is liquidated; a winning one supports the others.
* **Isolated** – only the margin you assign to this position is at risk. Liquidation happens sooner, but the rest of your balance is untouched.

## Liquidation

A position is liquidated when its margin falls to the **maintenance margin**:

| Market type | Maintenance margin |
| --- | --- |
| Order book | half of the initial margin at the market's maximum leverage (1.25% on a 40x market, 16.7% on a 3x market) |
| Hest Pool | 6% |

Liquidation distance from entry, as a percentage: `100 / leverage − maintenance margin`.

| Leverage | Order book (BTC, 1.25% mm) | Hest Pool (6% mm) |
| --- | --- | --- |
| 2x | 48.75% | 44% |
| 5x | 18.75% | 14% |
| 10x | 8.75% | 4% |
| 20x | 3.75% | – |

The order panel shows the exact liquidation price before you confirm, and **Risk Shield** tests that distance against the worst 1-hour candle of the week.

## What happens at liquidation

The position is closed at the mark price. On order book markets the clearing engine closes it against the book; on Hest Pool markets it settles against the vault at the TWAP. Remaining margin, if any, is returned to your balance.

{% hint style="warning" %}
Leverage cuts both ways. Hest shows you the numbers before every order; the maximum leverage is a ceiling, not a recommendation.
{% endhint %}
