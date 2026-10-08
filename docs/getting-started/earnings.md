---
description: >-
  What goes into your Earnings balance, how each amount is locked for 7 days,
  reviewed and paid in WETH, and how to follow it in Portfolio.
---

# Earnings

Your **Earnings** balance holds what Hest owes you on top of your own funds. It is shown as **Locked Earnings** in Portfolio, with a line for every amount in the **Earnings** tab. Earnings are paid by Hest after a 7-day lock and a review; they are never paid automatically.

## What Is Credited

| Type (as shown in Portfolio)  | When it is credited                                                                            | Amount                                                  |
| ----------------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| **Hest Pools profit**         | When one of your Hest Pools positions closes in profit, by you, by take profit or by stop loss | The full profit of the position, in WETH                |
| **Market owner fee share**    | On every opening and every closing on a market you own                                         | 15% of the 0.30% fee charged on that trade              |
| **Market owner profit share** | For a market you own                                                                           | 30% of Hest's net profit as counterparty on that market |
| **Bonus**                     | When Hest grants one                                                                           | As announced                                            |

All amounts are in **WETH**, shown with their dollar value at the live ETH price. A closed position's remaining collateral is not part of Earnings: it returns to your Trading Wallet at once.

## Lifecycle of an Amount

1. **Credited.** The amount appears in the Earnings tab with its type, market, amount and unlock time.
2. **Locked for 7 days.** Each amount has its own 7-day lock from the moment it is credited, with a countdown. Status: **Locked**.
3. **Reviewed.** When the lock ends the status becomes **Awaiting review**. Hest reviews the trades behind it; an amount cleared for payment can show **Approved** until it is sent.
4. **Paid.** Hest sends the WETH from its treasury to your **Trading Wallet** on Robinhood Chain. The status becomes **Paid**, with a **View** link to the transaction on robin.etherscan.io. From there it is ordinary WETH that you can trade or [withdraw](withdraw.md).

An amount that fails review is marked **Rejected**. Open a ticket on [Discord](https://discord.gg/hest) if you want to know why.

## Example

You close a Hest Pools long with a profit of 0.06 WETH on 1 March at 14:00 your time. Your remaining collateral returns to your Trading Wallet at 14:00. The 0.06 WETH is credited to Earnings at the same moment and unlocks on 8 March at 14:00. After Hest's review it is paid to your Trading Wallet and the Earnings tab shows **Paid** with the transaction link.

## Why the Lock and Review

Hest Pools markets trade young memecoins against Hest, priced on DEX pools. The 7-day lock and the review are the last line of defence against manipulation. Profits that come from a pushed pool, from linked accounts trading against each other, from a breach of the [Terms](../legal/terms.md) or from a faulty price can be withheld. Everything else is paid.

## What It Is Not

* **Not in your Trading Wallet yet.** Your deposits and the collateral of closed positions are in your Trading Wallet and can be withdrawn at any time. Earnings arrive there only when paid.
* **Not on Order Book markets.** Profit on Order Book markets is settled by Hyperliquid in your Trading Wallet's Hyperliquid account straight away. Nothing is locked.
* **Not interest.** Earnings are not a yield on deposits, and nothing in them is guaranteed.
