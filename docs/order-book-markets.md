---
description: BTC, ETH, SOL and 180+ more perpetuals on Hyperliquid's order book, traded from your Hest Trading Wallet.
---

# Order Book Markets

Order Book markets trade on **Hyperliquid**, the deepest perpetuals order book in crypto: BTC, ETH, SOL and 180+ more, plus the Robinhood Chain tokens Hyperliquid lists (today **CASHCAT** and **PONS**).

Hest is the front end and the brain on top of that book. Your orders are placed on Hyperliquid's order book from your [Hest Trading Wallet](trading-wallet.md). Your positions and margin live in that wallet's own Hyperliquid account, and Hest adds Super Intelligence, Risk Shield and Copilot on top.

![Browsing Markets and reading a market with Super Intelligence](assets/gifs/markets-and-si.gif)

## At a Glance

| | |
| --- | --- |
| Venue | Hyperliquid order book |
| Your account | The Hyperliquid account of your Trading Wallet |
| Collateral | USDC |
| Fees | Hyperliquid's fee (0.045% taker, 0.015% maker at the base tier) plus the Hest fee of 0.05%. See [Fees](fees.md). |
| Leverage | Up to the market's maximum, set by Hyperliquid (40x on BTC, lower on smaller markets) |
| Order types | Market, Limit, Stop Market, Stop Limit, Scale, TWAP, plus TP/SL. See [Order Types](order-types.md). |
| Margin | Cross or isolated |
| Minimum order | $10 (Hyperliquid rule) |
| Funding | Hourly, between longs and shorts. See [Funding](funding.md). |

## Robinhood Chain Tokens on the Book

When Hyperliquid lists a Robinhood Chain token, it trades here with real two-sided liquidity and Hest marks it **Robinhood Chain** in the Markets table. Leverage on these markets is set by Hyperliquid and is usually low on new listings. Robinhood Chain memecoins that Hyperliquid does not list trade on [Hest Pools](hest-pools.md).

## Your Hyperliquid Account

* **Activation.** Your first Order Book deposit activates the Trading Wallet's Hyperliquid account. Hyperliquid keeps 1 USDC once for this.
* **Deposits** arrive as USDC in that account. See [Deposit](deposit.md).
* **Withdrawals** go to your connected wallet on Arbitrum. Hyperliquid charges 1 USDC. See [Withdraw](withdraw.md).
* **Settlement.** Hest is never the counterparty on Order Book markets. Your counterparty is another participant in Hyperliquid's order book, and Hyperliquid's clearing engine margins, liquidates and settles positions under its own rules.

## Mark and Oracle Prices

Positions are valued at Hyperliquid's **mark price**, which tracks the **oracle** (an external reference price) and cannot be moved by a single trade. Both are shown in the strip at the top of every trade page.
