---
description: The Super Intelligence Score, 0 to 100, computed live from the market itself.
---

# SI Score

Every market on Hest carries a **Super Intelligence Score** from 0 to 100. **Higher is safer.** It is shown in the Markets table, inside Risk Shield on every trade page, and in full on the **Super Intelligence** page.

![Browsing Markets, then reading HYPE, BTC and SOL on the Super Intelligence page and asking Copilot why](assets/gifs/markets-and-si.gif)

The score answers one question: **how can this market hurt you right now?** It does not say whether the price will go up.

## How It Is Computed

On Order Book markets the score is computed **live from the market itself**, from five factors:

| Factor | What it measures |
| --- | --- |
| Funding skew | How far the hourly funding rate sits from neutral. A crowded side pays to stay in, and crowded sides get squeezed. |
| Crowding | Open interest relative to 24h volume. When open interest is a multiple of the volume, positions cannot all exit without moving the price. |
| Volatility | Today's move plus the worst hour of the week. A calm market scores high regardless of the coin's reputation. |
| Liquidity depth | How much the market trades. Deep markets absorb liquidations; thin ones gap through them. |
| Worst candle | The largest 1-hour drop in the last 7 days. |

The Super Intelligence page shows each factor as its own bar, the worst 1-hour candle of the week, and a one-line read of the market. Numbers refresh with the market data.

## What the Score Is Used For

* **Listing on Hest Pools**: a token needs an SI Score of 45 or more to be opened as a market. See [Open a Market](open-a-market.md).
* **Risk Shield**: the worst-candle number is what your liquidation distance is tested against.
* **Copilot**: answers are grounded in the same numbers.

{% hint style="info" %}
The score is information, not advice. A market with a high score can still drop sharply in a day. It tells you how the market can hurt you, not where the price goes next.
{% endhint %}
