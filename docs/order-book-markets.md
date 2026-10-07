# Order Book Markets

Most of Hest's 180+ markets trade on **Hyperliquid**, the deepest perpetuals order book in crypto: BTC, ETH, SOL, HYPE, XRP and the rest of the majors, the large memecoins (DOGE, PEPE, WIF, FARTCOIN and others), and every Robinhood Chain memecoin that has earned a Hyperliquid listing.

Hest is a front end and a brain on top of that book. Your orders are placed on Hyperliquid in your name, your positions and margin live on Hyperliquid, and Hest adds Super Intelligence, Risk Shield and Copilot on top.

## What You Get

* **Real depth.** Billions in daily volume across Hyperliquid's book. Your market order fills against resting liquidity, and the order panel shows the estimated slippage before you send it.
* **Mark and oracle prices.** Positions are valued at Hyperliquid's mark price, which tracks the oracle (an external reference) and cannot be moved by a single trade.
* **Leverage up to 40x** on the deepest markets, lower on thinner ones. The maximum for each market is shown next to its name and in the Markets table.
* **Hourly funding.** Longs and shorts pay each other every hour to keep the perpetual pinned to spot. See [Funding](funding.md).
* **Full order types.** Market, limit, stop market, stop limit, TWAP and scale orders, reduce-only, take profit and stop loss. See [Order Types](order-types.md).

## Robinhood Chain Tokens on the Book

When Hyperliquid lists a Robinhood Chain memecoin, Hest routes it there instead of a vault, and tags it **Robinhood** in the Markets table. The first one is **CASHCAT**. Order book routing gives the token real two-sided liquidity; the trade-off is that leverage is set by Hyperliquid (typically 3x for new listings).

## Fees

Hyperliquid's 0.045% taker and 0.015% maker, plus Hest's builder fee of 0.03%. Details in [Fees](fees.md).

## Settlement

Order book positions are settled in USDC by Hyperliquid's clearing engine. Hest never takes the other side of your trade on these markets and never holds your margin.
