# How vaults earn

A Hest Pool vault is a pot of USDC that takes the other side of every trade on one memecoin market. Depositing into it is called being an **LP** (liquidity provider).

## Income

* **Trading fees**: 70% of the 0.30% fee on every fill goes to the vault, pro rata to depositors. A market doing $200k of volume a day pays its vault about $420 a day.
* **Trader losses**: when traders on the market lose, the vault gains. Liquidations settle against the vault.
* **Funding**: the vault receives funding from the crowded side.

## Costs

* **Trader profits**: when traders win, the vault pays. This is the risk you are being paid for.
* Nothing else. No management fee, no performance fee; Hest's 10% comes out of the trading fee, not out of the vault.

## The numbers on the Pools page

* **TVL** – USDC in the vault.
* **APR 30d** – fee income over the last 30 days, annualised, divided by TVL.
* **Vault PnL 30d** – fees plus trader losses minus trader profits, over 30 days, as a percentage of TVL. This is the real return and it can be negative.
* **Open interest of cap** – positions open against the vault, out of the 30% cap. A vault near its cap is busy; a vault at zero is idle and earns nothing.
* **Your share** – your deposit and your percentage of the vault.

## Deposits and withdrawals

Deposit any amount from the Pools page. Withdrawals settle after the next 15-minute TWAP window so that the vault's value is marked fairly when you leave; you receive USDC including accrued fees. During the Beta a vault needs a community seed of $500 to exist; see [Open a market](markets-open-a-market.md).
