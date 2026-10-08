---
description: The terms used across Hest and this documentation, defined precisely.
---

# Glossary

**Builder fee**: the Hest fee on Order Book trades, 0.05% of every fill, collected through Hyperliquid's builder code mechanism. Your Trading Wallet approves a maximum of 0.05% once, with its first order.

**Capacity**: the open interest a Hest Pools market can carry. For markets opened through Open a Market, 20% of the token's DEX liquidity, between $10,000 and $20,000, fixed in WETH when the market opens. Position and open interest limits are shares of it.

**Closing fee**: 0.30% of a Hest Pools position's value at exit, deducted from the collateral returned to you.

**Collateral wallet**: the Hest-controlled wallet on Robinhood Chain used only for Hest Pools. It receives position collateral and market application payments, and sends refunds when positions close or applications are rejected.

**Connected wallet**: the wallet you sign in with. It is your identity on Hest, and withdrawals always go back to it.

**Copilot**: the Super Intelligence assistant you can ask about any market or about the order you are drafting.

**Cross / Isolated**: whether an Order Book position shares your whole balance (cross) or only its own margin (isolated). Hest Pools positions are always isolated.

**Crowding**: open interest relative to 24h volume. High crowding means positions cannot all exit without moving the price.

**Deviation**: on Hest Pools, `|spot − TWAP| / TWAP`. Above 10% a market pauses for new positions; below 5% it resumes.

**DEX liquidity**: on Hest Pools, twice the WETH held by the token's Uniswap pool, valued in dollars at the live ETH price.

**Earnings**: Hest Pools profits, market owner shares and any bonuses. Each amount is locked for 7 days, then reviewed and paid by Hest in WETH to your Trading Wallet.

**Entry price**: the price a position opened at. On Hest Pools, the higher of spot and TWAP for a long and the lower for a short.

**First-loss seed**: the WETH a market owner puts up when opening a market. Losses on the market come out of it first.

**Funding**: hourly payment between longs and shorts on Order Book markets. Positive rate: longs pay shorts. Hest Pools have no funding.

**Hest Pools**: perpetual markets on Robinhood Chain memecoins that Hyperliquid does not list, priced on the token's Uniswap pool, with Hest as the counterparty.

**Hest Pools engine**: the Hest service that opens, monitors and settles Hest Pools positions. It checks liquidation, take profit and stop loss once a minute.

**Hyperliquid**: the perpetuals exchange whose order book executes, margins and settles Hest's Order Book markets.

**Immediate-or-cancel (IOC)**: an order that fills what it can at once and cancels the rest. Order Book market orders are IOC orders priced 8% beyond the mark.

**Leverage**: position value divided by margin. At 10x, $100 of margin controls a $1,000 position.

**Liquidation**: forced close of a position when its margin, including unrealised profit and loss, reaches the maintenance margin.

**Liquidation distance**: how far the price can move against a fresh position before liquidation, `100 / leverage − maintenance margin %`.

**Liquidation fee**: on Hest Pools, 1% of the position's value at entry, charged when a position is liquidated.

**Maintenance margin**: the margin floor below which a position is liquidated. Order Book: `1 / (2 × max leverage)`, set by Hyperliquid. Hest Pools: 6% of the position value at entry.

**Margin**: the collateral backing a position. Initial margin opens it; maintenance margin is the floor below which it is liquidated.

**Mark price**: the price a position is valued and liquidated at. On Order Book markets, Hyperliquid's mark price. On Hest Pools, the price the position would close at now: the lower of spot and TWAP for a long, the higher for a short.

**Market owner**: the user who opened a Hest Pools market through Open a Market and put up its seed. Earns 15% of the market's fees and 30% of its profit as counterparty.

**Max Wick 7d**: Risk Shield's name for the worst 1-hour candle of the last 7 days.

**Open interest (OI)**: the total size of all open positions in a market. On Hest Pools it is counted per side and capped.

**Opening fee**: 0.30% of the order value of a Hest Pools position, paid on top of the margin.

**Oracle price**: an external reference price that anchors the mark on Order Book markets.

**Order value**: the size of a position in dollars (or WETH), before leverage is applied to margin.

**Perpetual (perp)**: a futures contract with no expiry.

**Reduce Only**: an order that can only shrink an existing position.

**Relay**: the service that routes deposits and bridged withdrawals between networks, through one-time deposit addresses.

**Risk Shield**: the pre-trade check that compares your liquidation distance with the worst 1-hour candle of the past week.

**Robinhood Chain**: the Arbitrum Orbit network (chain ID 4663) where Hest Pools tokens, their Uniswap pools and Hest Pools collateral live.

**Safer leverage**: the highest whole leverage whose liquidation distance is at least 1.5 times the worst 1-hour candle of the week.

**SI Brief**: the short written read of a market on the Super Intelligence page, shared by all visitors and rewritten when the market moves.

**SI Score**: Super Intelligence Score, 0 to 100, higher is safer.

**Sign-In with Ethereum (SIWE)**: the standard (EIP-4361) gas-free message your wallet signs to sign in to Hest.

**Spot**: on Hest Pools, the current price in the token's Uniswap pool.

**TP / SL**: take profit and stop loss prices attached to a position.

**Trading Wallet**: the wallet Hest creates for you to trade from. You hold its key and Hest keeps a copy to sign your trades.

**Trigger price**: the price at which a stop or take profit order activates.

**TWAP (pricing)**: time-weighted average price. Hest Pools read the 15-minute TWAP from the token's Uniswap v3 pool, a time-weighted geometric mean of the pool price over the last 900 seconds.

**TWAP (order)**: on Order Book markets, an order Hyperliquid executes in slices every 30 seconds over a running time of 5 to 1,440 minutes.

**WETH**: wrapped ETH, the ERC-20 form of ETH. The collateral of Hest Pools markets.

**Wick**: the thin line above or below a candle's body: the extreme the price touched in that period.
