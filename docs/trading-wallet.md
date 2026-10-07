---
description: The separate wallet Hest creates for you to trade from, who holds its key, and how to keep it safe.
---

# Hest Trading Wallet

After you connect a wallet and sign in, Hest creates a **Trading Wallet** for you: a separate wallet that holds your trading funds and places your trades. You deposit into it, trade from it, and withdraw from it back to the wallet you connected.

## Two Wallets, Two Jobs

| | Connected wallet | Trading Wallet |
| --- | --- | --- |
| What it is | Your own wallet (MetaMask, Phantom, Rabby and others) | A wallet Hest creates for you |
| Used for | Identity: signing in, approving sensitive actions | Holding trading funds and placing trades |
| Funds | Stay where they are; Hest never moves them | Your deposits for Hest Pools (Robinhood Chain) and Order Book (its own Hyperliquid account) |
| Withdrawals | Always arrive here | Always leave to your connected wallet |

## The Private Key

* **You see it once, at creation.** Hest shows the Trading Wallet's private key and asks you to save it. You then confirm you saved it by typing back a few of its characters.
* **You can see it again** with **Show Key** in Portfolio, after signing a request with your connected wallet.
* **Hest keeps a copy of the key.** That is how Hest signs your trades for you, and why there is no wallet pop-up on every order.
* It is a standard Ethereum private key. With it you can import the Trading Wallet into any EVM wallet that supports importing a private key, and reach your Hyperliquid account directly.

{% hint style="danger" %}
Anyone who has the key controls the Trading Wallet and everything in it. Never share it, never paste it into a website, and never send it to anyone. Hest never asks for it: not in the app, not on Discord, not on X, not by email.
{% endhint %}

## What This Means for You

Because Hest keeps a copy of the key and signs your trades, **the Trading Wallet is not a self-custody wallet**: you and Hest can both control it. Keep in it what you are trading with, and withdraw the rest to your connected wallet. See [Withdraw](withdraw.md) and the [Risk Disclosure](risk-disclosure.md).
