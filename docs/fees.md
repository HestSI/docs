# Fees

Trading fees are charged on the **position size** (order value), not on your margin, and are shown in the order panel before you confirm.

## Hest Pools

| Fee | Rate |
| --- | --- |
| Open a position | 0.30% |
| Close a position | 0.30% |

There is no maker or taker distinction: every open and close is priced at the worse of spot and the 15-minute TWAP (see [How Hest Pools Work](how-hest-pools-work.md)). Fees on Hest Pools are paid in WETH, the collateral of those markets. On a market opened by a user, 15% of the trading fees go to the market's opener.

## Order Book

| Fee | Taker | Maker | Who receives it |
| --- | --- | --- | --- |
| Hyperliquid (base tier) | 0.045% | 0.015% | Hyperliquid |
| Hest | 0.05% | 0.05% | Hest |
| **Total** | **0.095%** | **0.065%** | |

On a $1,000 market order, that is $0.95.

The Hest fee uses Hyperliquid's **builder fee** mechanism: it is approved once for your Trading Wallet's Hyperliquid account and then added to every order automatically. It is itemised in the order panel and in Trade History. Hyperliquid caps builder fees at 0.1%; Hest charges 0.05%.

## Deposits and Withdrawals

| | Hest fee | Other costs |
| --- | --- | --- |
| Deposit | 0.8% | Relay's own fee and network gas. Everything is shown before you send. |
| Deposit of ETH already on Robinhood Chain, sent straight to your Trading Wallet | None | Network gas |
| Withdrawal | None | Network gas and, when bridged, Relay's fee. Hyperliquid charges 1 USDC on Order Book withdrawals. |
| First Order Book deposit | – | Hyperliquid keeps 1 USDC once to activate the account. |

See [Deposit](deposit.md) and [Withdraw](withdraw.md).

## Opening a Market

A $20 listing fee plus a seed in WETH. Both are refunded if the application is rejected. See [Open a Market](open-a-market.md).

## Other Costs

* **Funding** on Order Book markets is paid or received hourly between traders. See [Funding](funding.md).
* **Network fees** on Robinhood Chain are paid in ETH from your Trading Wallet. About $1 of ETH covers hundreds of transactions.
