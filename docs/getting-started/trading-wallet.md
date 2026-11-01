---
description: >-
  The separate wallet Hest creates for you to trade from, how its key is
  created, stored, shown and used, and how to keep it safe.
---

# Hest Trading Wallet

After you connect a wallet and sign in, Hest creates a **Trading Wallet** for you: a new, separate wallet that holds your trading funds and places your trades. You deposit into it, trade from it, and withdraw from it back to the wallet you connected. It is **not** your connected wallet and does not share its key.

## Two Wallets, Two Jobs

|                   | Connected wallet                                                       | Trading Wallet                                                                                         |
| ----------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| What it is        | Your own wallet (MetaMask, Phantom, Rabby and others)                  | A new wallet Hest creates for you                                                                      |
| Who holds the key | Only you                                                               | You and Hest                                                                                           |
| Used for          | Identity: signing in, approving the display of your Trading Wallet key | Holding trading funds and placing trades                                                               |
| Funds             | Stay where they are; Hest never moves them                             | Hest Pools on Solana: SOL. Hest Pools on Robinhood Chain: ETH and WETH. Order Book: USDC in the wallet's own Hyperliquid account. |
| Withdrawals       | Always arrive here                                                     | Always leave to your connected wallet                                                                  |

The Trading Wallet is one Ethereum address used on two venues: on Robinhood Chain it holds ETH and WETH for Hest Pools; on Hyperliquid the same address owns your Order Book account.

Solana uses a different kind of key, so Hest creates a **second address** for it, your **Solana Trading Wallet**, which holds the SOL you trade Solana markets with. It belongs to the same Hest account and has its own private key.

## Creating It

1. Sign in, then click **Create Trading Wallet** (offered after sign-in, from **Deposit**, or from the **Not Ready to Trade** checklist on a trade page).
2. Hest generates a new private key, stores it, and reads the stored copy back to check it matches the new address before going any further. If the check fails, nothing is created and you are asked to try again.
3. The key is shown to you, masked. Click **Show** or **Copy** and save it somewhere safe and offline.
4. Click **I Saved My Private Key**, then confirm once more with **Yes, I Saved It** on **Is Your Key Saved?**

Deposits and trading unlock only after this confirmation. If you close the dialog before confirming, **Finish Your Trading Wallet Setup** appears the next time; sign with your connected wallet to see the key again and confirm.

### The Solana Address

Your Solana Trading Wallet is created the first time you need it: when you open the **Solana** tab in Deposit, or from the **Create Your Solana Wallet** step in the **Not Ready to Trade** checklist of a Solana market. It is created with the same care as the first one, the key is stored and read back before the address is used, and it then appears in the wallet menu as **Hest Pools · Solana** and in **Show Key** next to your EVM key. If you never trade Solana markets, it is never created.

## The Private Key

* **Format.** A standard Ethereum private key: `0x` followed by 64 hexadecimal characters. It is not a seed phrase. Any EVM wallet that can import a private key (MetaMask, Rabby, Phantom and others) opens the Trading Wallet with it.
* **The Solana key.** If you have a Solana Trading Wallet, **Show Key** shows its key as well, as a base58 string in the format Phantom, Solflare and Backpack accept when you import a private key. It is a separate key for a separate address: the EVM key does not open the Solana wallet and the Solana key does not open the EVM one.
* **Shown again on request.** Click **Show Key** in Portfolio or in the wallet menu and sign the message "Reveal my Hest Trading Wallet private key." with your connected wallet. The signature must come from the wallet you signed in with. Accounts signed in with Google confirm with the same Google account instead (see [Sign In with Google](connect-a-wallet.md#sign-in-with-google)). The key can be shown at most 5 times per hour.
* **Hest keeps a copy.** That is how Hest signs your trades and transfers on your instructions, and why there is no wallet pop-up on every order. Every use of the key, to sign or to show it, is logged with its purpose.
* **What Hest signs with it.** Only actions you start in the interface: Order Book orders, cancels, leverage changes and TWAP orders; Hest Pools collateral transfers; market application payments; and withdrawals to your connected wallet. See [Security](../help/security.md).

{% hint style="danger" %}
Anyone who has a key controls that wallet and everything in it: the EVM key covers Robinhood Chain and Hyperliquid, the Solana key covers your SOL. Never share them, never paste them into a website, and never send them to anyone. Hest never asks for them: not in the app, not on Discord, not on X, not by email.
{% endhint %}

## Using the Key Outside Hest

With the key imported into another wallet you can:

* see and move the ETH and WETH on Robinhood Chain directly;
* open app.hyperliquid.xyz with the imported wallet and manage your Order Book positions and USDC, including when the Hest interface is unavailable;
* revoke Hest's builder fee approval on Hyperliquid;
* with the Solana key imported into Phantom, Solflare or Backpack, see and move the SOL in your Solana Trading Wallet.

Hest Pools positions cannot be managed outside Hest: their collateral is held by Hest while they are open, and they are opened, closed and settled by the Hest Pools engine.

## What This Means for You

Because Hest keeps a copy of the key and signs your trades, **the Trading Wallet is not a self-custody wallet**: you and Hest can both control it. Keep in it what you are trading with, and withdraw the rest to your connected wallet. See [Withdraw](withdraw.md), [Security](../help/security.md) and the [Risk Disclosure](../legal/risk-disclosure.md).

If you believe your key has been exposed, withdraw everything to your connected wallet immediately, then open a ticket marked **Security** on [Discord](https://discord.gg/hest).
