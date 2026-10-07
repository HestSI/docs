# Copilot

Copilot is the part of Super Intelligence you can talk to. It lives in two places: the **Super Intelligence** page (full chat, any market) and under **Risk Shield** on every trade page (short chat, this market, your drafted order).

## What it knows

Every answer is grounded in live data for the market you are looking at:

* mark price, 24h change, volume, open interest, hourly funding, maximum leverage
* the SI Score and every factor behind it, plus the project notes on memecoins
* the worst 1-hour candle of the last 7 days
* your open positions in that market, and on the trade page the order you are drafting (side, size, leverage, liquidation distance)

It does not invent prices or events. If something is not in that data, it says so.

## What to ask

* "Is this size safe at 10x?" – it computes your liquidation distance against the worst candle and gives a yes, a no, or a safer leverage.
* "Is the long side crowded?" – funding skew and open interest versus volume.
* "Who holds the supply?" / "Is the team known?" / "What is the joke?" – the on-chain and social read on a memecoin.
* "Worst candle this week?" / "What are the fees?" / "Why this score?"

The mascot reacts to the answer: happy, idle, worried or scared.

## Tone

Copilot is written to behave like a sharp colleague on a risk desk: direct, specific, short, never salesy. It will tell you no.

{% hint style="info" %}
Copilot is information, not financial advice. It reads the market; the decision is yours.
{% endhint %}
