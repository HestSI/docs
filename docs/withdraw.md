---
description: Withdraw from either side of your Trading Wallet to the wallet you signed in with. Destinations, minimums, fees, timing, statuses and what happens when something fails.
---

# Withdraw

Withdrawals go **only to your connected wallet**: the wallet you signed in with. You never type a destination address; Hest takes it from your signed-in session, so a withdrawal cannot be sent anywhere else. **Hest charges no withdrawal fee.**

## How to Withdraw

1. Click **Withdraw** in Portfolio (or in the wallet menu at the top right).
2. Choose the side: **Hest Pools** or **Order Book**. The dialog shows your live balances.
3. Enter the amount, or click **Max**.
4. Click **Review Withdrawal**. Hest checks the amount against your live balance and shows **You Withdraw**, the network, bridge or Hyperliquid fee, **Hest Fee $0.00**, **You Receive** and **Arrives In**.
5. Click **Confirm Withdrawal**. The dialog follows it until it settles, with a transaction link. The withdrawal is also listed under **Deposits and Withdrawals** in Portfolio.

## Hest Pools Side (Robinhood Chain)

| | |
| --- | --- |
| Assets | ETH or WETH from your Trading Wallet |
| Receive On | Robinhood Chain, Arbitrum, Ethereum or Base |
| Robinhood Chain | Sent directly to your connected wallet, as ETH or WETH. Arrives in a few seconds. |
| Arbitrum, Ethereum, Base | Bridged by Relay and delivered as ETH. WETH is unwrapped to ETH first, in a separate transaction. Minimum about $1. |
| Gas reserve | When withdrawing ETH, a small amount stays in the Trading Wallet for network fees. The dialog shows how much. Withdrawing WETH requires that reserve in ETH. |
| Costs | Robinhood Chain network fee, plus Relay's fee when bridged |

Bridged withdrawals are protected in two ways: the Relay route is checked field by field before use (recipient, amount, network, output token), and if the amount you would receive drops by more than 1% between review and confirmation, you are asked to review the new amount and confirm again.

## Order Book Side (Hyperliquid)

| | |
| --- | --- |
| Asset | USDC from your Trading Wallet's Hyperliquid account |
| Delivered | As USDC to your connected wallet on Arbitrum |
| Hyperliquid fee | 1 USDC per withdrawal |
| Minimum | 2 USDC |
| Precision | Up to 6 decimals |
| Time | About 5 minutes |

**Available** is what Hyperliquid lets you withdraw now: margin backing open positions is not available. If part of your USDC sits in your Hyperliquid spot balance, Hest moves the shortfall to perps first, then withdraws. **Example:** withdrawing 100 USDC delivers 99 USDC on Arbitrum.

## Statuses

| Status | Meaning |
| --- | --- |
| **Sending** | The transaction is being signed and sent. |
| **Bridging** | Sent on Robinhood Chain; Relay is delivering it to the destination network. |
| **Sent** / **Arrived** | Done. For Order Book withdrawals, Hyperliquid releases the USDC on Arbitrum in about 5 minutes. |
| **Refunded** | The bridge could not complete and returned the ETH to your Trading Wallet. |
| **Not completed** | It did not go through. The message says where your funds are. |

## Safeguards

* **Destination fixed by your session.** The connected wallet you signed in with is the only possible destination.
* **One withdrawal at a time.** While one is in progress, a second is refused with "Another withdrawal is still in progress."
* **No double sends.** Each withdrawal has a unique ID created when you review it. A double click or a retry returns the same withdrawal instead of sending again.
* **Recorded before sent.** Every signed transaction is recorded before it is broadcast, so an interruption can always be resolved from the chain. Withdrawals that stop half way are settled automatically, and the status shows the result.

## If Something Fails

| Message | What happened |
| --- | --- |
| Something went wrong before sending. Nothing left your wallet. | Nothing was signed or sent. Try again. |
| Stopped after unwrapping: your WETH is now ETH in your trading wallet. | The unwrap succeeded but the bridge transfer did not. Withdraw the ETH. |
| The bridge refunded the ETH to your trading wallet. | Relay returned the funds. Try again. |
| Hyperliquid did not record the withdrawal. Your USDC is still there. | No withdrawal reached Hyperliquid's ledger within 30 minutes. Try again. |

If you need help, open a ticket on [Discord](https://discord.gg/hest).

## What You Cannot Withdraw

* **Margin that backs open positions or resting orders.** On Hest Pools it is held in the collateral wallet until the position closes; on the Order Book, Hyperliquid reserves it.
* **Your [Earnings](earnings.md) balance.** Profits and owner shares are paid by Hest into your Trading Wallet after their 7-day lock and review. Once paid, they are ordinary WETH you can withdraw.
