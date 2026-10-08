---
description: Which wallets work with Hest, how the gas-free sign-in works, signing in with Google, how long a session lasts, and your profile.
---

# Connect a Wallet

Your wallet is your identity on Hest. You connect it, sign in with a signature, and Hest creates a separate [Trading Wallet](trading-wallet.md) for you to trade from. Withdrawals always go back to the wallet you connected.

No wallet yet? You can also [sign in with Google](#sign-in-with-google). Your Google account becomes your identity, and you choose one address that receives your withdrawals.

## Supported Wallets

Open [hest.si](https://hest.si) and click **Log In**. The **Log In to Hest** dialog offers **Continue with Google** and lists the wallets that work with Hest:

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
| Session length | 7 days on that browser (wallet and Google sign-in alike) |
| Ending a session | **Disconnect** in the wallet menu signs you out and removes the session from the browser |
| Switching accounts in your wallet | Signs you out of the previous account; the new account signs in separately |

{% hint style="info" %}
Sign-in needs a regular wallet account that signs with its own key. Smart-contract wallets (for example Safe multisigs) cannot sign in to Hest.
{% endhint %}

## Sign In with Google

Click **Log In**, then **Continue with Google**, and choose your Google account in Google's window. Hest receives your Google account ID, email address and name, and nothing else: no access to your mail, contacts or files. The Google account needs a verified email address.

Because a Google account has no wallet to send withdrawals to, the next step is **Set Your Withdrawal Address**:

1. Enter the address of a wallet you control (MetaMask, Phantom, Rabby and similar). Do not use an exchange deposit address, and do not use your Hest Trading Wallet.
2. Tick the box to confirm the address is correct, and save.
3. Hest then creates your [Trading Wallet](trading-wallet.md) as for any other account.

Your email appears at the top right instead of a wallet address. Clicking it opens **Signed in with Google**: the account, where withdrawals go, any address change in progress, and **Sign Out**.

### Changing the Withdrawal Address

The first address applies at once. A later change waits **48 hours** before it applies:

* Until then, withdrawals keep going to the current address.
* The change in progress and the time it applies are shown in the account dialog and under **Change** in **Withdraw**, where you can cancel it at any time before it applies.
* The Hest team is alerted to every change.

The delay means that someone who takes over your Google account cannot send your funds to a new address straight away. If you did not ask for a change, cancel it and open a ticket marked **Security** on [Discord](https://discord.gg/hest).

### Showing Your Key with Google

Accounts signed in with Google confirm **Show Key** with Google instead of a wallet signature: Hest opens Google's window again, and only a fresh confirmation (less than 5 minutes old) from the same Google account shows the key.

{% hint style="info" %}
A Google account and a wallet are separate Hest accounts, even if you use both. Funds, Trading Wallet and history are not shared between them.
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
