---
description: >-
  How Hest protects your account, your Trading Wallet key and your funds, the
  limits that apply, and what to do if something goes wrong.
---

# Security

Hest holds a copy of your Trading Wallet key so it can trade for you without a wallet pop-up on every order. This page explains what that key can and cannot be used for, the safeguards around sign-in, signing and withdrawals, and what you should do yourself.

## The Security Model in One Table

| Asset                                   | Who controls it  | Protection                                                                                                                                                 |
| --------------------------------------- | ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Your connected wallet                   | Only you         | Hest never holds its key and never asks for it. It only signs messages: sign-in and key display.                                                           |
| Trading Wallet on Robinhood Chain       | You and Hest     | Hest signs only actions you start in the interface. Withdrawals can only go to your connected wallet.                                                      |
| Trading Wallet's Hyperliquid account    | You and Hest     | Hest signs only trading actions there. Withdrawals can only go to your connected wallet.                                                                   |
| Collateral of open Hest Pools positions | Hest             | Held in a Hest wallet used only for Hest Pools. Every minute its balance is checked against the collateral and refunds owed to open and closing positions. |
| Earnings                                | Hest, until paid | Paid by Hest from its treasury into your Trading Wallet after review.                                                                                      |

## Sign-In

* Sign-in uses **Sign-In with Ethereum (EIP-4361)**: a plain-text message for the domain hest.si that your wallet shows you before you sign. It cannot move funds and costs no gas.
* Each sign-in message carries a one-time nonce and expires after **5 minutes**. A signed message cannot be replayed, and a sign-in signature cannot be reused to show your key.
* **Sign in with Google** uses Google's signed ID token. Hest checks Google's signature, that the token was issued for Hest, that it has not expired and that the email is verified. Showing the key needs a fresh Google confirmation (under 5 minutes old) from the same Google account.
* A session lasts **7 days** on that browser. **Disconnect** ends it. Changing accounts in your wallet ends it.

## The Trading Wallet Key

* **Created safely.** When your Trading Wallet is created, the key is stored and read back to confirm it matches the new address before it is shown to you or used. If the check fails, nothing is created.
* **Shown only to you, only with your signature.** After creation, the key is shown only when you sign a separate message ("Reveal my Hest Trading Wallet private key.") with the wallet you signed in with. A signature from any other wallet is refused. The key can be shown at most **5 times per hour**.
* **Every use is logged.** Each time the key is used to sign or is shown, the use is recorded with its purpose. Repeated failed attempts to show a key raise an alert to the Hest team.
* **Checked before every use.** Before signing anything, Hest checks that the stored key still opens your Trading Wallet address. If it does not, nothing is signed.

## What Hest Will Sign

Hest signs with your Trading Wallet key only for actions you start in the interface:

| Venue           | Actions Hest signs                                                                                                                     |
| --------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Hyperliquid     | Orders, cancels, leverage and margin-mode changes, TWAP orders and TWAP cancels, and the one-time builder fee approval (maximum 0.05%) |
| Robinhood Chain | Hest Pools collateral transfers when you open a position, market application payments, and withdrawals to your connected wallet        |

The trading endpoint refuses every Hyperliquid action that moves funds, such as transfers to other accounts or agent approvals. Every order it signs carries Hest's builder fee and nothing else is added. Orders are submitted to Hyperliquid by your own browser.

## Withdrawals

* The destination is the connected wallet of your signed-in session. No request can name another address.
* For Google accounts the destination is the account's withdrawal address. A new address applies only 48 hours after it is set, can be cancelled until then, and every change alerts the Hest team. A stolen Google account cannot redirect withdrawals at once.
* Only one withdrawal can be in progress per Trading Wallet.
* A withdrawal has a unique ID, so double clicks and retries never send twice.
* Every signed transaction is recorded before broadcast, and unfinished withdrawals are settled automatically from the chain.
* Bridge routes are checked field by field before use, and a quote that worsens by more than 1% must be confirmed again.
* Very large or very frequent withdrawals raise an alert to the Hest team.

## Limits

| Limit                                                                                           | Value                                                            |
| ----------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| Sign-in message validity                                                                        | 5 minutes                                                        |
| Session length                                                                                  | 7 days                                                           |
| Showing the Trading Wallet key                                                                  | 5 times per hour                                                 |
| Trading requests (Order Book orders, cancels and leverage changes; Hest Pools opens and closes) | 60 per minute per account, combined                              |
| Withdrawals in progress                                                                         | 1 at a time                                                      |
| Copilot questions                                                                               | Daily allowance, see [Copilot](../super-intelligence/copilot.md) |

Exceeding a rate limit returns a short message such as "Too many orders. Wait a few seconds."

## What You Should Do

* **Check the address bar.** Hest is only at **hest.si**. The documentation is at hest.gitbook.io/hest-docs.
* **Read every wallet prompt.** Hest only ever asks your connected wallet for message signatures (sign-in and key display) and, if you use **Send from Connected Wallet**, for the deposit transfer you set up.
* **Store the Trading Wallet key offline.** Never paste it into a website or send it to anyone.
* **Keep in the Trading Wallet only what you are trading with.** Withdraw the rest.
* **Be wary of anyone who contacts you first.** Hest never asks for a seed phrase, a private key or your Trading Wallet key, in the app, on Discord, on X or by email.

## If Something Goes Wrong

1. **Your Trading Wallet key may be exposed:** withdraw everything from both sides to your connected wallet immediately. Anyone with the key can move funds too, so speed matters.
2. **Your connected wallet may be compromised:** disconnect from Hest, move your funds to a new wallet, and open a ticket. Withdrawals from your Trading Wallet go to the connected wallet, so the Hest team needs to know.
3. **Your Google account may be compromised** (if you sign in with Google): secure it with Google, check **Withdrawal Address** for a change you did not ask for and cancel it, and open a ticket.
3. **You found a vulnerability:** open a ticket marked **Security** on [discord.gg/hest](https://discord.gg/hest). The team moves it to a private channel. Do not disclose it publicly until it is fixed.

{% hint style="warning" %}
**Hest has no token.** Anything claiming to be a Hest token, airdrop or claim without an official announcement on [hest.si](https://hest.si) and [@HestSI](https://x.com/HestSI) is fake.
{% endhint %}
