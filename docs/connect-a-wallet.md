---
description: Which wallets work with Hest, how the gas-free sign-in works, how long a session lasts, and your profile.
---

# Connect a Wallet

Your wallet is your identity on Hest. You connect it, sign in with a signature, and Hest creates a separate [Trading Wallet](trading-wallet.md) for you to trade from. Withdrawals always go back to the wallet you connected.

## Supported Wallets

Open [hest.si](https://hest.si) and click **Connect Wallet**. The dialog lists the wallets that work with Hest:

* MetaMask
* Phantom
* Rabby
* Base (formerly Coinbase Wallet)
* Trust Wallet
* OKX Wallet
* Rainbow
* Zerion
* Robinhood Wallet (on mobile, see below)

Wallets installed in your browser are discovered automatically (EIP-6963), shown in colour and marked **Detected**. The others are greyed out; clicking one opens its download page.

Any of these works for every network Hest uses: you sign in with an Ethereum-style (EVM) account, and Hest never asks your connected wallet to hold funds on a specific network.

## Sign In

1. Click your wallet and approve the connection in the wallet's own window.
2. Approve the **sign-in signature**. It is a standard Sign-In with Ethereum message (EIP-4361) for the domain hest.si, with the statement "Sign in to Hest. This request does not move funds or cost gas." It is a message, not a transaction: it costs no gas and moves no funds.
3. Your address appears at the top right. You are signed in.

The first sign-in creates your Hest account, tied to your wallet address. No email, name or document is needed.

### Session Rules

| Rule | Value |
| --- | --- |
| Validity of a sign-in request | 5 minutes, single use |
| Session length | 7 days on that browser |
| Ending a session | **Disconnect** in the wallet menu signs you out and removes the session from the browser |
| Switching accounts in your wallet | Signs you out of the previous account; the new account signs in separately |

{% hint style="info" %}
Sign-in needs a regular wallet account that signs with its own key. Smart-contract wallets (for example Safe multisigs) cannot sign in to Hest.
{% endhint %}

## On Mobile

Open hest.si inside your wallet app's built-in browser (MetaMask, Phantom, Trust, Rabby and others). The wallet is detected like a browser extension, and everything works as on desktop.

**Robinhood Wallet** is a mobile app: open hest.si from the browser inside the Robinhood Wallet app.

## The Wallet Menu

Once signed in, your short address sits at the top right. Hover or tap it for your Hyperliquid and Hest Pools balances, how many Robinhood Chain transactions your ETH still covers, and **Deposit**, **Withdraw**, **Show Key** (once you have a Trading Wallet) and **Disconnect**. **Portfolio** in the top menu opens the full account page.

## Your Profile

When you first sign in, Hest gives you a username derived from your address, for example ScalperOfHest1234. You can change it with **Edit Profile** in the Connected Wallet dialog:

* 3 to 18 characters: letters, numbers and underscore.
* One change every 30 days. The automatic first name does not start the 30-day timer.
* Names already taken, names starting with 0x, offensive names and names that impersonate Hest are refused.

{% hint style="warning" %}
Hest will never ask for the seed phrase or private key of your connected wallet, or for your Trading Wallet key, in the app, on Discord, on X or by email. Anyone asking for them is not Hest.
{% endhint %}
