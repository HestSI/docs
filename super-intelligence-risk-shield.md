# Risk Shield

Risk Shield is the check that runs **before you click buy**, on every trade page, under the order form. It answers one question: *would a normal bad hour in this market liquidate this position?*

## The calculation

1. **Liquidation distance** = `100 / leverage − maintenance margin`. At 5x on an order book market with 1.25% maintenance margin, liquidation sits 18.75% away. On a Hest Pool market (6% maintenance margin) at 5x, it sits 14% away.
2. **Worst candle** = the largest 1-hour drop in the last 7 days for this market, read from live candles.
3. **Ratio** = liquidation distance ÷ worst candle.

## The verdict

| Ratio | Verdict | Mascot |
| --- | --- | --- |
| under 1.0 | **One normal candle liquidates this.** A move the market already made this week would take the position out. | scared |
| 1.0 – 1.5 | **Tight.** You survive the worst candle of the week, with little to spare. | worried |
| over 1.5 | **Room to breathe.** Liquidation sits comfortably beyond anything the market did this week. | happy |

The readout also shows the SI Score so you see the market quality next to the position risk.

## What it does not do

Risk Shield does not block orders and does not predict direction. A green verdict means the position survives a repeat of this week's worst hour, not that next week will look like this one. Leverage caps on Hest Pool markets are enforced separately by Super Intelligence.

## Try it on the home page

The home page carries a live Risk Shield demo: pick any market, long or short, 2x to 20x, and watch the verdict change with real numbers.
