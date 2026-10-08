---
description: >-
  BTC, ETH, SOL and 180+ more perpetuals on Hyperliquid's order book, traded
  from your Hest Trading Wallet. How orders are signed, sent and settled.
---

# Order Book Markets

Order Book markets trade on **Hyperliquid**, a perpetuals exchange with a fully on-chain central limit order book: BTC, ETH, SOL and 180+ more, plus the Robinhood Chain tokens Hyperliquid lists (today **CASHCAT** and **PONS**).

Hest is the interface and the risk layer on top of that book. Your orders are signed by your [Hest Trading Wallet](../getting-started/trading-wallet.md) and placed on Hyperliquid's order book; your positions and margin live in that wallet's own Hyperliquid account. Hest adds Super Intelligence, Risk Shield and Copilot, and charges a builder fee on each fill.

![Browsing Markets and reading a market with Super Intelligence](../.gitbook/assets/markets-and-si.gif)

## At a Glance

|               |                                                                                                                                               |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Venue         | Hyperliquid order book                                                                                                                        |
| Your account  | The Hyperliquid account of your Trading Wallet                                                                                                |
| Counterparty  | Other participants in Hyperliquid's order book. Hest is never the counterparty.                                                               |
| Collateral    | USDC                                                                                                                                          |
| Fees          | Hyperliquid's fee (0.045% taker, 0.015% maker at Hyperliquid's base tier) plus the Hest builder fee of 0.05%. See [Fees](../trading/fees.md). |
| Leverage      | Up to the market's maximum, set by Hyperliquid (for example 40x on BTC, lower on smaller markets and new listings)                            |
| Margin modes  | Cross or isolated, set per market                                                                                                             |
| Order types   | Market, Limit, Stop Market, Stop Limit, Scale, TWAP, plus take profit and stop loss. See [Order Types](../trading/order-types.md).            |
| Minimum order | $10 of order value (Hyperliquid rule; reduce-only orders are exempt)                                                                          |
| Funding       | Hourly, between longs and shorts. See [Funding](../trading/funding.md).                                                                       |
| Settlement    | Hyperliquid's clearing engine margins, liquidates and settles positions under its own rules                                                   |

## How an Order Travels

1. **You confirm** an order in the order panel. The panel has already shown the liquidation price, order value, margin required, estimated slippage, fees and route, and Risk Shield's verdict.
2. **Hest signs it.** The order is signed with your Trading Wallet key in Hyperliquid's own signature format. Hest adds the builder fee to every order it signs; nothing else about the order changes.
3. **Your browser sends it** straight to Hyperliquid's exchange API. Hest's servers sign but do not relay orders, so every user's orders reach Hyperliquid from their own connection.
4. **Hyperliquid matches it** against the book. Fills, positions, open orders and funding appear in the tabs under the chart and in Portfolio, read from Hyperliquid.

Before an order that can open or increase a position, Hest also signs a leverage update for that market, which sets the leverage and the cross or isolated mode you chose in the panel. Reduce-only orders skip this step.

The trading endpoint only signs trading actions: orders, cancels, leverage updates, TWAP orders and TWAP cancels. It refuses anything that moves funds. Withdrawals have their own path, which can only pay out to your connected wallet. See [Security](../help/security.md).

## The Builder Fee Approval

Hyperliquid lets an interface charge a fee on the orders it routes (a **builder fee**) only after the account owner approves a maximum rate. Your Trading Wallet approves Hest's builder fee **once**, at a maximum of **0.05%**, together with your first order: the approval is signed and submitted just before that order, and Hest checks on Hyperliquid that it is in place. Hest charges exactly 0.05%, and Hyperliquid rejects any builder fee above the approved maximum.

The approval can be revoked on Hyperliquid by the account owner, using the Trading Wallet key.

## Your Hyperliquid Account

* **Activation.** Your first Order Book deposit activates the Trading Wallet's Hyperliquid account. Hyperliquid keeps 1 USDC once for this. Until the account is active, orders fail with "Your Hyperliquid account is not active yet. Deposit USDC first: the first deposit activates it."
* **Deposits** arrive as USDC in that account through Relay. See [Deposit](../getting-started/deposit.md).
* **Withdrawals** go to your connected wallet on Arbitrum. Hyperliquid charges 1 USDC; the minimum is 2 USDC. See [Withdraw](../getting-started/withdraw.md).
* **Direct access.** The account belongs to your Trading Wallet address. If the Hest interface is unavailable, you can import the Trading Wallet key into any EVM wallet and manage the account directly on Hyperliquid.

## Prices, Sizes and Units

* **Mark and oracle.** Positions are valued at Hyperliquid's **mark price**, which tracks the **oracle** price (an external reference) and cannot be moved by a single trade. Both are shown in the strip at the top of the trade page, with 24h change, 24h volume, open interest and **Funding / Countdown**.
* **Price precision.** Prices are rounded to Hyperliquid's rules (at most 5 significant figures, and a maximum number of decimals that depends on the market). Sizes are rounded down to the market's size step.
* **Thousand-unit markets.** Hyperliquid quotes some low-priced coins per 1,000 tokens (kPEPE, kBONK and others). Hest shows them per single token under the plain symbol and converts sizes and prices when it builds the order.
* **Data refresh.** Market prices, volume, open interest and funding for the whole list update every 10 seconds; the order book and recent trades on the trade page refresh every 2 seconds, and the chart every 3 seconds.

## Robinhood Chain Tokens on the Book

When Hyperliquid lists a Robinhood Chain token, it trades here with real two-sided liquidity and Hest marks it **Robinhood Chain** in the Markets table. Leverage on these markets is set by Hyperliquid and is usually low on new listings. Robinhood Chain memecoins that Hyperliquid does not list trade on [Hest Pools](hest-pools.md), and a token that Hyperliquid lists cannot be opened as a Hest Pools market.

## Paused Markets

Hest can pause an Order Book market on Hest, for example during an incident on the market. While a market is paused, Hest does not sign new orders or orders that increase a position on it. Orders that only reduce a position, such as closing it or a take profit or stop loss, are still signed, so you can always get out. The market itself keeps trading on Hyperliquid.

## Read Next

* [Order Types](../trading/order-types.md): how each order type is built and sent.
* [Leverage and Liquidation](../trading/leverage-and-liquidation.md): margin modes and liquidation distance.
* [Fees](../trading/fees.md): the full fee schedule.
