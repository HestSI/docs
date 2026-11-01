---
description: >-
  Follow any wallet you know: its Hest Pools positions and its Hyperliquid
  fills, listed separately and marked on the chart where it opened and closed.
---

# Tracked Wallets

**Tracked Wallets** lets you follow wallets you already know, on both venues. Paste an address and you see what it has traded; leave it switched on and its trades appear on the chart of whatever market you are looking at.

The card is in **Portfolio**, under Referrals. The markers it draws appear on the trade page.

## Adding a Wallet

1. Open **Portfolio** and find **Tracked Wallets**.
2. Paste an address: an EVM address (`0x...`) or a Solana address.
3. Click **Track**.

You can track up to **12 wallets**. Click a wallet to expand it, use the X to stop tracking it.

Which address to paste depends on what you want to see:

| Address                                               | What you get                                                                 |
| ----------------------------------------------------- | ---------------------------------------------------------------------------- |
| A Hest [Trading Wallet](../getting-started/trading-wallet.md) (`0x...`) | Its Hest Pools positions on Robinhood Chain and its Hyperliquid fills        |
| A Hest Solana Trading Wallet                          | Its Hest Pools positions on Solana markets                                   |
| Any other Hyperliquid account                         | Its Hyperliquid fills. There are no Hest Pools positions to show.            |

Hest Pools positions belong to a Trading Wallet, so the address of someone's connected wallet shows nothing. Hyperliquid accounts are EVM addresses, so a Solana address never has a Hyperliquid list.

## What You See

Each wallet opens into two lists, read live from each venue and never mixed:

* **Hest Pools:** the wallet's most recent positions, with market, side and leverage, size, entry, exit, PNL and the time it opened or closed. Open positions show **Open** instead of an exit. Amounts are converted to dollars at the live SOL or ETH price of that market.
* **Hyperliquid:** the wallet's most recent fills, with market, action, size, price, closed PNL and time, straight from Hyperliquid's public API.

A wallet with a Hest profile shows its **username and picture**. Wallets without one show a letter avatar made from the address. Each read is kept for about a minute, so opening the card again, or going back to a trade page, gives you a fresh one.

## On the Chart

Switch **Show Tracked Wallets on the Chart** on in the card, and **On Chart** on for each wallet you want to see. Then, on the trade page:

* On a **Hest Pools** market, a marker is drawn where the wallet opened a position and where it closed it, at the price it filled at.
* On an **Order Book** market, a marker is drawn at every fill.
* The marker is the wallet's avatar, ringed in green for a buy or long and red for a sell or short. Hover it to see the name, what the wallet did (for example **Opened Long 3x**) and the price.

Markers are drawn only for the market on screen. The toggles are remembered, so you can keep a list and turn the chart layer off when you want a clean chart.

## What Is and Is Not Published

* **There is no public feed of Hest Pools trades.** Nothing lists who traded what. You see a wallet's trades only when you ask for that specific address.
* **Your list stays in your browser.** The addresses you track are kept in that browser's local storage, not on Hest's servers. Tracking someone tells them nothing and tells Hest nothing about you.
* **Your own Trading Wallet can be tracked the same way.** Its Hest Pools positions are on-chain transfers to and from the Hest Pools collateral wallet, and its Hyperliquid fills are public on Hyperliquid, so anyone who knows the address can read them with or without Hest.
* **Your connected wallet is never revealed.** The profile picture of a tracked wallet is served through the Trading Wallet address, so following a trader never shows the account behind it. Only the username and picture you chose yourself are shown.

If you would rather not be followed, keep in mind that both venues are public by design, and that the address someone needs is the Trading Wallet address, not your connected wallet.

## Limits

| Limit                   | Value                                                               |
| ----------------------- | ------------------------------------------------------------------- |
| Wallets tracked         | 12                                                                  |
| Positions read          | The 60 most recent per wallet, the newest 25 shown                  |
| Hyperliquid fills read  | The 80 most recent per wallet, the newest 25 shown                 |
| How long a read is kept | About a minute per wallet                                           |
| Lookups                 | Rate limited per IP address. Too many at once return "Too many lookups." |

## Read Next

* [How Hest Pools Work](../markets/how-hest-pools-work.md): what the entry, exit and PNL of a pool position mean.
* [Order Book Markets](../markets/order-book-markets.md): how fills reach Hyperliquid.
* [Hest Trading Wallet](../getting-started/trading-wallet.md): the address these lists belong to.
