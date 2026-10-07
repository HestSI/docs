---
description: Apply to list a Robinhood Chain token on Hest Pools, seed it, and earn a share of its fees and profit.
---

# Open a Market

Anyone can apply to open a Hest Pools market for a Robinhood Chain token that is not already listed on Hest. The applicant pays a listing fee and puts up a seed in WETH; in return the opener earns a share of the market's trading fees and of its profit.

## Requirements

A token can be listed only if it meets all four:

1. **Bonded** from its launchpad: it has graduated from the bonding curve to a DEX pool.
2. **DEX liquidity of at least $50k.**
3. **Older than 24 hours.**
4. **SI Score of 45 or more.**

Paste the token's contract address on the **Open a Market** page and click **Check** to see whether it qualifies.

## Capacity and Seed

Every Hest Pools market has a **capacity**: **20% of the token's DEX liquidity, between $10k and $20k.** Capacity sets the position limits of the market (one position is capped at 10% of capacity).

To open a market you pay:

| Item | Amount |
| --- | --- |
| Listing fee | $20 |
| Seed | 10% of the market's capacity, minimum $1,000, paid in WETH |

## Review

**Hest reviews every application.** If an application is rejected, the listing fee and the seed are refunded.

## What the Opener Earns

* **15% of the market's trading fees.** Credited per trade to your [Earnings](earnings.md) balance, each amount locked for 7 days, paid out weekly.
* **30% of the market's profit as counterparty.** When traders on your market lose overall, you receive 30% of that profit.

## The Seed Is First-Loss

The seed is not a deposit that sits aside. It backs the market:

* **Market losses come out of the seed first.** If traders on your market win, the seed pays before anything else.
* **The seed is locked for 7 days.**
* **At withdrawal its value includes the unrealised profit and loss of open positions** on the market. If traders are winning when you withdraw, you receive less.
* **Withdrawing the seed ends your shares** in that market's fees and profit.

{% hint style="warning" %}
A seed can lose value, and can be lost entirely, if traders on the market win. Read [Hest Pools Risks](hest-pools-risks.md) before you apply.
{% endhint %}
