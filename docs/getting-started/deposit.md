---
description: >-
  How to fund your Trading Wallet from eight networks through Relay deposit
  addresses, what arrives where, every fee, and what to do if a deposit fails.
---

# Deposit

Every deposit goes into your [Trading Wallet](trading-wallet.md). You choose which side it is for, Hest gives you a one-time deposit address, and you send from almost any wallet or exchange. Deposits are routed by **Relay**, which swaps and bridges the funds and delivers them to the right place.

![Signing in, opening Deposit, choosing the network and token, switching between Hest Pools and Order Book](../.gitbook/assets/deposit.gif)

## Where a Deposit Arrives

| Side           | Arrives as | Where                                                                                                                                    |
| -------------- | ---------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **Solana**     | SOL        | Your Solana Trading Wallet. Solana Hest Pools markets trade in SOL, and the network fee comes out of the same balance.                   |
| **Hest Pools** | ETH        | Your Trading Wallet on Robinhood Chain. ETH is wrapped to WETH automatically when you open a position, and part of it pays network fees. |
| **Order Book** | USDC       | Your Trading Wallet's Hyperliquid account, ready to trade. Hyperliquid keeps 1 USDC once to activate a new account.                      |

The **Hest Pools** tab is the Robinhood Chain side of Hest Pools; the **Solana** tab is its Solana side. Which one you need depends on the market you want to trade, and the trade page tells you if you are on the wrong side.

## How to Deposit

1. Connect your wallet and sign in. Create your Trading Wallet and confirm that you saved its key; deposits unlock after that confirmation.
2. Click **Deposit** (in Portfolio, or in the wallet menu at the top right).
3. Choose the side: **Hest Pools**, **Order Book** or **Solana**. Opening the Solana tab creates your Solana Trading Wallet if you do not have one yet.
4. Pick **Send From** (the network you are sending from) and the **Token**, and enter the amount.
5. Click **Get Deposit Address**. Hest asks Relay for a route and shows the full breakdown: **You Send**, **Hest Fee (0.8%)**, **Network and Bridge Fees**, **You Receive** and **Arrives In**, with the deposit address and its QR code.
6. Send exactly that token, on exactly that network, to the address, from any wallet or exchange. On EVM networks you can instead click **Send from Connected Wallet**: your wallet switches to the right network (adding Robinhood Chain if it does not know it) and asks you to approve the transfer.
7. The dialog follows the transfer: **Waiting for your transfer**, then **Transfer received, delivering to your Trading Wallet**, then **Arrived** with a link to the delivery transaction. It keeps following it if you close the dialog, and the deposit is also listed under **Deposits and Withdrawals** in Portfolio.

The quote for the last deposit address stays in the dialog for 30 minutes, so you can reopen it and copy the address again.

## Supported Networks and Tokens

| Send from       | Tokens          |
| --------------- | --------------- |
| Arbitrum        | ETH, USDC, USDT |
| Ethereum        | ETH, USDC, USDT |
| Base            | ETH, USDC       |
| Optimism        | ETH, USDC       |
| BNB Chain       | BNB, USDT, USDC |
| Polygon         | USDC, USDT      |
| Solana          | SOL, USDC       |
| Robinhood Chain | ETH, USDG       |

Any of these can be sent to any side: Relay swaps it into SOL on Solana, into ETH on Robinhood Chain for Hest Pools, or into USDC on Hyperliquid for the Order Book.

{% hint style="danger" %}
Send only the token and network shown for that deposit address. A token that is not on this list, or a token sent on the wrong network, cannot be recovered. Each deposit address is for one deposit only: get a new address for every deposit.
{% endhint %}

## Fees

|                                                                                     | Amount                                      |
| ----------------------------------------------------------------------------------- | ------------------------------------------- |
| Hest deposit fee                                                                    | 0.8% of the amount you send                 |
| Relay fee and network fees                                                          | Depend on the route; quoted before you send |
| ETH already on Robinhood Chain, sent straight to your Trading Wallet for Hest Pools | No Hest fee, only the network fee           |
| SOL already on Solana, sent straight to your Solana Trading Wallet                  | No Hest fee, only the network fee           |

**Example.** 500 USDC from Base to the Order Book side: the Hest fee is $4.00, and you receive about 496 USDC on Hyperliquid minus Relay's fee and network fees as quoted. On a first Order Book deposit, Hyperliquid keeps 1 USDC of that to activate the account.

## Already on the Destination Chain

Two routes need no bridge, no Relay and no Hest fee. The dialog shows your own address and its QR code instead of a deposit address:

* **Hest Pools** and **Robinhood Chain / ETH:** send ETH straight to your Trading Wallet on Robinhood Chain.
* **Solana** and **Solana / SOL:** send SOL straight to your Solana Trading Wallet.

Send only that token on that network to those addresses. They are your own wallets, so they can be reused for as many deposits as you like, unlike Relay deposit addresses.

USDG on Robinhood Chain and USDC on Solana go through Relay like any other token.

## Sending From Solana

Relay can only refund a failed Solana deposit on Solana, so the dialog asks for **Your Solana Address**: the Solana wallet you are sending from. It is used only for refunds. **Send from Connected Wallet** is not available for Solana; send from your Solana wallet to the deposit address.

## If a Deposit Fails

If Relay cannot complete a deposit, it refunds it on the network you sent from:

* **EVM networks:** the refund goes to your **connected wallet address** on that network (for Google accounts, your withdrawal address), even if you sent from an exchange.
* **Solana:** the refund goes to the Solana address you entered.

The dialog then shows **Refunded to your wallet** or **Deposit failed**. If you need help, open a ticket on [Discord](https://discord.gg/hest) with the deposit address.

## Keep Some Gas on Each Chain

Opening a position, applying for a market and withdrawing are transactions from your Trading Wallet, paid in the chain's own native token:

* **Robinhood Chain:** ETH. About $1 of ETH covers hundreds of transactions. When ETH is wrapped for a position, a small reserve is always left unwrapped for these fees.
* **Solana:** SOL, out of the same balance you trade with. A transaction costs a fraction of a cent, and a small amount of SOL always stays behind when you withdraw with **Max**.

On Order Book markets there is nothing to keep: Hyperliquid charges no network fee for trading.
