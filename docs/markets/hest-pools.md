---
description: >-
  Perpetual markets on the Robinhood Chain memecoins Hyperliquid does not list,
  priced on their own Uniswap pools, with Hest as the counterparty.
---

# Hest Pools

Hest Pools are perpetual markets on **Robinhood Chain memecoins that Hyperliquid does not list**. They are where Hest starts: a token with real DEX liquidity on Robinhood Chain can get a leveraged market long before any order book would list it.

On a Hest Pools market **Hest is your counterparty**. There is no order book and no other trader on the other side of your order. You open a position against Hest, at a price read on-chain from the token's own Uniswap v3 pool, and Hest settles it when you close.

## At a Glance

|                     |                                                                                                                                                                    |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Tokens              | Robinhood Chain memecoins with a Uniswap v3 WETH pool, not listed on Hyperliquid                                                                                   |
| Counterparty        | Hest                                                                                                                                                               |
| Price               | Spot and the 15-minute TWAP of the token's Uniswap v3 pool. Every open and close uses whichever is worse for you. See [Hest Pools Pricing](hest-pools-pricing.md). |
| Collateral          | WETH on Robinhood Chain (chain ID 4663), shown with its live dollar value                                                                                          |
| Network fees        | ETH on Robinhood Chain, paid from your Trading Wallet when you open. Closing costs you no network fee.                                                             |
| Leverage            | 1x to 5x (a market can have a lower maximum)                                                                                                                       |
| Trading fee         | 0.30% of the order value to open, 0.30% of the position value to close                                                                                             |
| Maintenance margin  | 6%                                                                                                                                                                 |
| Liquidation fee     | 1% of the position value at entry                                                                                                                                  |
| Funding             | None                                                                                                                                                               |
| Position limit      | 10% of the market's capacity and 2% of the token's DEX liquidity, whichever is lower                                                                               |
| Open interest limit | Per side: 50% of capacity and 10% of DEX liquidity, whichever is lower                                                                                             |
| Order types         | Market, with optional take profit and stop loss                                                                                                                    |
| Losses              | Settled at close. The remaining collateral returns to your Trading Wallet immediately.                                                                             |
| Profits             | Credited to [Earnings](../getting-started/earnings.md), locked for 7 days, then reviewed and paid by Hest in WETH                                                  |
| Automatic pause     | New positions stop when spot and TWAP are more than 10% apart; trading resumes below 5%. Closing always works.                                                     |

## How a Trade Settles

1. **Open.** Your margin plus the 0.30% opening fee moves in WETH from your Trading Wallet to the Hest Pools collateral wallet, a Hest wallet used only for Hest Pools.
2. **Monitor.** Every minute the Hest Pools engine reads each pool and checks every open position for liquidation, take profit and stop loss.
3. **Close.** The position is settled at the worse of spot and TWAP. What is left of your collateral after any loss and the closing fee is sent back to your Trading Wallet at once. A profit is credited to your Earnings balance.

The full mechanics, with a worked example, are in [How Hest Pools Work](how-hest-pools-work.md).

## Where to Find Them

* **Pools** in the top menu lists every Hest Pools market with its price, 24h change, 24h volume, capacity and how much of it is used.
* **Markets** with the **Hest Pools** filter shows them alongside every other market, with the SI Score and route.
* Every Hest Pools market shows its token contract address next to its name, with a copy button, so you can check you are trading the token you think you are.

Risk Shield checks your order before you click buy on Hest Pools markets as on any other, with the worst 1-hour candle of the past week read from the pool's own price history.

New markets are added through [Open a Market](open-a-market.md). Anyone can apply when a token meets the requirements.

## Before You Trade

1. [Connect a wallet](../getting-started/connect-a-wallet.md) and sign in. Create your [Trading Wallet](../getting-started/trading-wallet.md) and confirm that you saved its key.
2. [Deposit](../getting-started/deposit.md) to the **Hest Pools** side. Your deposit arrives as ETH on Robinhood Chain. ETH is wrapped to WETH automatically when you open a position.
3. Keep a little ETH unwrapped for network fees. The wallet menu at the top right shows roughly how many Robinhood Chain transactions your ETH still covers.

If something is missing, the order button opens a **Not Ready to Trade** checklist that takes you to the next step.

## Read Next

* [How Hest Pools Work](how-hest-pools-work.md): sizing, liquidation and settlement, with numbers.
* [Hest Pools Pricing](hest-pools-pricing.md): spot, TWAP, the fill rule and the automatic pause.
* [Open a Market](open-a-market.md): requirements, the seed and what the opener earns.
* [Hest Pools Risks](hest-pools-risks.md): read this before you trade or open a market.
* [Earnings](../getting-started/earnings.md): how profits are locked, reviewed and paid.
