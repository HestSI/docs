# Deposit

Every deposit goes into your [Trading Wallet](trading-wallet.md). You choose where it should land, Hest gives you a deposit address, and you send from almost any wallet or exchange.

![Signing in, opening Deposit, choosing the network and token, switching between Hest Pools and Order Book](assets/gifs/deposit.gif)

## How to Deposit

1. Connect your wallet and sign in. If you do not have a Trading Wallet yet, Hest creates one first.
2. Click **Deposit** (in Portfolio, or in the wallet menu at the top right).
3. Choose the side:
   * **Hest Pools**: arrives as **ETH in your Trading Wallet on Robinhood Chain**. Hest Pools markets trade in WETH, and ETH pays network fees.
   * **Order Book**: arrives as **USDC in your Trading Wallet's Hyperliquid account**. Hyperliquid keeps 1 USDC once to activate a new account.
4. Pick **Send From** (the network you are sending from) and the **Token**, and enter the amount.
5. Click **Get Deposit Address**. Hest shows a deposit address and QR code, together with the full breakdown: what you send, the Hest fee, network and bridge fees, what you receive and how long it takes.
6. Send exactly that token on exactly that network to the address, from any wallet or exchange. On EVM networks you can also click **Send from Connected Wallet**.
7. The dialog follows the transfer until it arrives. It keeps working if you close the dialog.

Deposits are routed by **Relay**, which bridges and swaps the funds to the right place.

## Supported Networks and Tokens

| Send from | Tokens |
| --- | --- |
| Ethereum | ETH, USDC, USDT |
| Arbitrum | ETH, USDC, USDT |
| Base | ETH, USDC |
| Optimism | ETH, USDC |
| BNB Chain | BNB, USDT, USDC |
| Polygon | USDC, USDT |
| Solana | SOL, USDC |
| Robinhood Chain | ETH, USDG |

{% hint style="danger" %}
Send only the token and network you selected. A token that is not on this list, or a token sent on the wrong network, cannot be recovered. Each deposit address is for one deposit only.
{% endhint %}

## Fees

* **Hest deposit fee: 0.8%.**
* **Relay's fee and network gas**, which depend on the route.

All of them are shown before you send. If you already hold ETH on Robinhood Chain and choose Hest Pools, you can send it straight to your Trading Wallet address with no Hest fee.

## Sending From Solana

Relay can only refund a failed Solana deposit on Solana, so the dialog asks for **Your Solana Address**: the Solana wallet you are sending from. It is used only for refunds.

## Keep Some ETH on Robinhood Chain

Every Hest Pools trade and withdrawal is a Robinhood Chain transaction, paid in ETH from your Trading Wallet. About $1 of ETH covers hundreds of transactions.
