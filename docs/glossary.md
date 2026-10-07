# Glossary

**Perpetual (perp)** – a futures contract with no expiry, kept close to spot by funding payments.

**Mark price** – the price your position is valued and liquidated at. On order book markets it tracks the oracle; on Hest Pool markets it is the 15-minute TWAP.

**Oracle price** – an external reference price for the asset, used to anchor the mark.

**TWAP** – time-weighted average price. Hest Pool markets use the 15-minute TWAP of the token's DEX price so single wicks cannot move the mark.

**Wick** – the thin line above or below a candle's body: the extreme the price touched inside that period. "Max wick 7d" is the worst 1-hour drop of the week.

**Funding** – hourly payment between longs and shorts. Positive rate: longs pay shorts.

**Open interest (OI)** – the total size of all open positions in a market, in USD.

**Crowding** – open interest relative to 24h volume. High crowding means positions cannot all exit without moving the price.

**Leverage** – exposure divided by margin. 10x: $100 of margin controls a $1,000 position.

**Margin** – the USDC backing a position. Initial margin opens it; maintenance margin is the floor below which it is liquidated.

**Cross / Isolated** – whether a position shares your whole balance (cross) or only its own margin (isolated).

**Liquidation** – forced close of a position when its margin reaches the maintenance level.

**Reduce only** – an order that can only shrink an existing position.

**TP / SL** – take profit and stop loss prices attached to a position.

**Vault** – the USDC pool that is the counterparty on a Hest Pool market.

**LP** – liquidity provider; a vault depositor.

**Position cap** – no single position may exceed 30% of a vault.

**SI Score** – Super Intelligence Score, 0 to 100, higher is safer.

**Risk Shield** – the pre-trade check comparing your liquidation distance with the worst recent candle.

**Copilot** – the Super Intelligence assistant you can ask about any market or order.

**Bonded** – a launchpad token that has graduated from its bonding curve to a DEX pool.

**Sniper** – a wallet that buys in the first blocks after a launch, usually to sell into the first pump.

**Builder fee** – Hest's fee on order book trades, collected through Hyperliquid's builder code mechanism and approved once by the user.

**Hyperliquid** – the perpetuals exchange whose order book executes and margins Hest's order book markets.
