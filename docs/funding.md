# Funding

A perpetual has no expiry, so something has to keep its price pinned to the underlying. On Order Book markets that something is **funding**: a payment between longs and shorts every hour, set and settled by Hyperliquid.

## How It Works

* The rate is shown on the trade page strip as **Funding / Countdown**, for example `0.0013% 32:05`: the rate for the coming hour and the time until it is paid.
* **Positive rate**: longs pay shorts. The perpetual is trading above spot and longs are the crowded side.
* **Negative rate**: shorts pay longs.
* The payment is `position size × rate`. A $10,000 long at 0.0013% pays $0.13 that hour; over a day at that rate, about $3.

Payments are settled from your margin every hour and listed under **Funding History**.

## Reading It

0.0013% per hour (about 0.01% per 8 hours) is what a balanced market looks like. Rates several times higher mean one side is crowded and paying to stay in. Super Intelligence turns this into the **Funding skew** factor of the [SI Score](si-score.md), and Copilot will tell you which side is paying.

Funding is not a Hest fee: it flows between traders.
