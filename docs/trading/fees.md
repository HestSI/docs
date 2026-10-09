---
description: >-
  The complete Hest fee schedule for Hest Pools, Order Book markets, deposits,
  withdrawals and opening a market, with worked examples.
---

# Fees

Every fee is shown before you confirm: in the order panel and confirmation dialog for trades, and in the breakdown of every deposit and withdrawal. Trading fees are charged on **position value** (order value), not on margin.

## Summary

| Activity                                                | Hest fee                                                  | Other costs                                                                             |
| ------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Hest Pools: open                                        | 0.30% of order value                                      | ETH network fee for the collateral transfer                                             |
| Hest Pools: close                                       | 0.30% of position value at exit                           | None (the refund is sent by Hest)                                                       |
| Hest Pools: liquidation                                 | 1% of position value at entry, plus the 0.30% closing fee | None                                                                                    |
| Order Book: trade                                       | 0.05% builder fee on every fill                           | Hyperliquid's trading fee                                                               |
| Deposit through Relay                                   | 0.8%                                                      | Relay's fee and network fees                                                            |
| Deposit of ETH already on Robinhood Chain to Hest Pools | None                                                      | Network fee                                                                             |
| Withdrawal                                              | None                                                      | Network fees; Relay's fee when bridged; 1 USDC to Hyperliquid on Order Book withdrawals |
| Open a Market                                           | $20 listing fee                                           | A seed of 10% of capacity (refunded with the fee if the application is rejected)        |
| Funding (Order Book)                                    | None                                                      | Paid or received hourly between traders                                                 |

## Hest Pools

| Fee             | Rate  | Charged on                                                           | Taken from                                   |
| --------------- | ----- | -------------------------------------------------------------------- | -------------------------------------------- |
| Opening fee     | 0.30% | Order value                                                          | Paid on top of your margin when you open     |
| Closing fee     | 0.30% | Position value at exit (`value at entry × exit price / entry price`) | Deducted from the collateral returned to you |
| Liquidation fee | 1%    | Position value at entry                                              | Deducted from the collateral returned to you |

There is no maker or taker distinction and no funding. Fees are paid in WETH, the collateral of these markets. On a market opened by a user through [Open a Market](../markets/open-a-market.md), 15% of every opening and closing fee is credited to the market's owner; this comes out of Hest's fee, not on top of it.

**Example.** A $1,500 position (3x on $500 of margin) pays $4.50 to open. Closed at +10%, its exit value is $1,650 and the closing fee is $4.95: **$9.45** in fees for the round trip, 0.63% of the entry value.

{% hint style="info" %}
The fees are not the whole cost of a Hest Pools round trip. Every open and close is priced at the worse of the pool's spot price and its 15-minute TWAP, so whenever the two differ you also pay that gap, on both ends. See [Hest Pools Pricing](../markets/hest-pools-pricing.md).
{% endhint %}

## Order Book

| Fee                     | Taker      | Maker      | Who receives it |
| ----------------------- | ---------- | ---------- | --------------- |
| Hyperliquid (base tier) | 0.045%     | 0.015%     | Hyperliquid     |
| Hest builder fee        | 0.05%      | 0.05%      | Hest            |
| **Total**               | **0.095%** | **0.065%** |                 |

**Example.** A $1,000 market order pays $0.45 to Hyperliquid and $0.50 to Hest: **$0.95**. A $1,000 limit order that rests and fills as maker pays $0.15 + $0.50 = **$0.65**.

* **Hyperliquid's fee** depends on your Trading Wallet's trading volume on Hyperliquid, under Hyperliquid's own fee schedule. The base tier is shown above. Portfolio shows your current taker and maker rates and your 14-day volume.
* **The Hest fee** uses Hyperliquid's builder fee mechanism. Your Trading Wallet approves a maximum of 0.05% once, with your first order, and Hest adds exactly 0.05% to every order it signs. Hyperliquid enforces the approved maximum. The fee is itemised in the order panel before you confirm.

## Deposits

* **Hest deposit fee: 0.8%** of the amount you send, collected by Relay as part of the route.
* **Relay's own fee and network fees**, which depend on the network, the token and whether a swap or bridge is needed.

The deposit dialog lists **You Send**, **Hest Fee (0.8%)**, **Network and Bridge Fees**, **You Receive** and **Arrives In** before it shows you the deposit address.

**Example.** Sending 1,000 USDC from Arbitrum to the Order Book side: the Hest fee is $8.00, and you receive about 992 USDC on Hyperliquid minus Relay's fee and network fees as quoted. If this is the account's first deposit, Hyperliquid keeps 1 USDC once to activate the account.

**No Hest fee** applies when you already hold ETH on Robinhood Chain and send it straight to your Trading Wallet address for Hest Pools.

## Referral Share

If you joined through someone's referral link, nothing changes for you: your fees are exactly those above. Your referrer earns **10% of your Hest Pools fees**, paid out of Hest's part. See [Referrals](../getting-started/referrals.md).

## Withdrawals

Hest charges **no withdrawal fee**.

| Side                                               | Costs                                                                              |
| -------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Hest Pools, received on Robinhood Chain            | Network fee in ETH, quoted before you confirm                                      |
| Hest Pools, received on Arbitrum, Ethereum or Base | Network fees on Robinhood Chain plus Relay's bridge fee, quoted before you confirm |
| Order Book                                         | 1 USDC, charged by Hyperliquid. Minimum withdrawal 2 USDC.                         |

## Opening a Market

A **$20 listing fee** plus a **seed** of 10% of the market's capacity (at least $1,000), both paid in WETH. If the application is rejected, both are refunded in full. See [Open a Market](../markets/open-a-market.md).

## Network Fees on Robinhood Chain

Every Hest Pools opening, market application and Robinhood Chain withdrawal is a transaction from your Trading Wallet, paid in **ETH** (not WETH). Robinhood Chain fees are small: about $1 of ETH covers hundreds of transactions. When ETH is wrapped for you, or withdrawn with **Max**, a small reserve is always left in the Trading Wallet for these fees.
