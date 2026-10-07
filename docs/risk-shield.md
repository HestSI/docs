# Risk Shield

Risk Shield is the check that runs **before you click buy**, on every trade page, under the order form. It answers one question: *would a normal bad hour in this market liquidate this position?*

![Risk Shield on BTC: the verdict turns as leverage goes to 40x and back to 5x, then Copilot answers "Is this size safe?"](assets/gifs/risk-shield.gif)

## The Calculation

1. **Liquidation distance** = `100 / leverage − maintenance margin`, in percent of price. At 5x on BTC (1.25% maintenance margin) liquidation sits 18.75% away; at 40x it sits 1.25% away.
2. **Worst candle** = the largest 1-hour drop of the last 7 days in this market, read from live candles. Shown as **Max Wick 7D**.
3. **Ratio** = liquidation distance ÷ worst candle.

## The Verdict

| Ratio | Verdict |
| --- | --- |
| under 1.0 | **One normal candle liquidates this.** A move the market already made this week would take the position out. |
| 1.0 to 1.5 | **Tight.** You survive the worst candle of the week, with little to spare. |
| over 1.5 | **Room to breathe.** Liquidation sits comfortably beyond anything the market did this week. |

The readout also shows the market's SI Score, so you see market quality next to position risk.

## Ask Before You Trade

Under the verdict, Copilot takes questions about the order you are drafting: **Is this size safe?**, **Why this score?**, **Safer leverage?**, or anything you type. See [Copilot](copilot.md).

## What It Does Not Do

Risk Shield does not block orders and does not predict direction. A good verdict means the position survives a repeat of this week's worst hour, not that next week will look like this one.

## Try It on the Home Page

The home page has a live Risk Shield: pick long or short and a leverage, and watch the verdict change with real numbers.
