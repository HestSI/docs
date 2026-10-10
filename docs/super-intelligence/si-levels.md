---
description: Support, resistance, trend and expected range, drawn on the chart by Super Intelligence.
---

# SI Levels

Super Intelligence does not only score a market. It also reads the chart and draws what it found, directly on the price.

## What Gets Drawn

| Line | Meaning |
| --- | --- |
| **Support 1 / Support 2** | Price areas below the current price where selling has stopped before. Computed by clustering the swing lows and highs of the recent candles; the strongest two below the price are kept. |
| **Resist 1 / Resist 2** | The same read above the price: areas where rallies have stalled before. |
| **Trend channel** | A regression line through the recent closes, with a band two standard deviations wide on each side. The slope is the trend: rising, falling or flat. |
| **24h Range** | The band the price is expected to stay inside for the next 24 hours with roughly 68% probability, from the market's own recent volatility. A calm market gets a narrow band, a violent one a wide band. |
| **Worst 1h** | The price the market would hit if the worst 1-hour candle of the last 7 days repeated from here. This is the same candle Risk Shield checks your liquidation against. |
| **Your Liq** | Only when you have an order drafted: the liquidation price of that draft. If this line sits inside the Worst 1h move, one bad hour can close you. |

## Where It Lives

- **The trade page.** The chart toolbar has a **Super Intelligence** toggle. Turn it off and the chart is a plain chart again; the choice is remembered.
- **The Super Intelligence page.** Every market's page shows a clean analysis chart with the levels always on, plus a summary row: trend and slope, support and resistance, the 24h range, RSI and ATR.

Copilot and the SI Brief read the same levels, so when the text says "support near a price", that price is the line on the chart.

## How It Is Computed

Everything is computed from the market's real candles, in code, at the moment you look:

- Support and resistance come from pivot points (local highs and lows) clustered together when they sit within half an ATR of each other. More touches and more recent touches make a level stronger.
- The trend channel is a least-squares regression over the recent closes.
- The 24h range scales the standard deviation of recent returns to one day.
- RSI 14 and ATR 14 use their standard definitions.

With too little candle history the layer hides instead of guessing: a market that is a few hours old shows no levels, because there is nothing honest to draw.

## What It Is Not

Levels are a map of where the market has reacted before and how far it tends to move. They are not a prediction and not advice: a level can break, a range can be exceeded, and a trend can reverse without warning. Size your positions so that being wrong is acceptable.
