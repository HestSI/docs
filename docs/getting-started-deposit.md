# Deposit USDC

All trading on Hest is collateralised in **USDC**. One balance covers every market: order book majors, Robinhood Chain memecoins and Hest Pool markets.

![Depositing USDC from the Account panel](assets/gifs/deposit.gif)

## How to deposit

1. Connect your wallet.
2. Open any trade page and click **Deposit** in the Account panel (bottom right).
3. Enter the amount and confirm two transactions in your wallet: an approval (first time only) and the deposit itself.
4. Your **USDC balance** updates as soon as the transaction confirms.

## Where the USDC comes from

Hest accepts native USDC on Robinhood Chain. If your USDC is on another network:

* **Arbitrum, Ethereum, Base, Solana**: bridge to Robinhood Chain first. The deposit dialog links to the bridge.
* **Centralised exchange**: withdraw to Arbitrum, then bridge. Withdraw USDC, not USDC.e.

Keep a few dollars of the network's gas token in your wallet for the approval and deposit transactions.

## Withdrawals

Click **Withdraw** in the Account panel. Only **free collateral** can be withdrawn: margin locked in open positions or resting orders stays until those are closed or cancelled. Withdrawals settle to the same wallet that deposited.

{% hint style="info" %}
During the Beta, deposits and withdrawals are capped per wallet. The current cap is shown in the deposit dialog.
{% endhint %}
