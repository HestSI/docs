# Funding

A perpetual has no expiry, so something has to keep its price pinned to the underlying. That something is **funding**: a payment between longs and shorts every hour.

## How It Works

* The funding rate is shown on the trade page strip as **Funding / countdown**, for example `0.0013% 32:05` – the rate for the coming hour and the time until it is paid.
* **Positive rate**: longs pay shorts. The perpetual is trading above spot and longs are the crowded side.
* **Negative rate**: shorts pay longs.
* The payment is `position size × rate`. A $10,000 long at 0.0013% pays $0.13 that hour. Over a day at that rate, about $3.

Payments are settled from your margin every hour on the hour and listed under **Funding history**. The **Funding** column in Positions shows the running total for each position.

## Reading It

0.0013% per hour is the neutral rate (0.01% per 8 hours), which is what a balanced market looks like. Rates several times higher mean one side is crowded and paying to stay in; Super Intelligence turns this into the **Funding skew** factor of the SI Score, and Copilot will tell you which side is paying.

## Hest Pool Markets

Pool markets also use hourly funding, computed from the gap between the TWAP mark and the DEX price. The Hest Pool rate is shown the same way on the strip, with the countdown to the next TWAP window beside it.
