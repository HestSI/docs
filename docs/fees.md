# Fees

Fees are charged on the **position size** (order value), not on your margin, and are shown in the order panel before you confirm.

## Order Book Markets

| Fee | Rate | Who receives it |
| --- | --- | --- |
| Taker | 0.045% | Hyperliquid |
| Maker | 0.015% | Hyperliquid |
| Hest builder fee | 0.030% | Hest |

Total for a market order: **0.075%** of position size. On a $1,000 position, $0.75.

The builder fee is how Hest earns on order book markets. It uses Hyperliquid's **builder code** mechanism: on your first order your wallet asks you to approve a maximum builder fee for Hest (the signature says Hyperliquid, because that is where the order settles). After that it is applied automatically and itemised in the confirmation dialog and in Trade history. Hyperliquid caps builder fees at 0.1%; Hest charges 0.03%.

## Hest Pool Markets

| Fee | Rate | Split |
| --- | --- | --- |
| Trading fee | 0.30% | 70% vault depositors · 20% market owner · 10% Hest |

Pool fees are higher because the vault is taking the other side of your trade and needs to be paid for that risk. There is no maker/taker distinction; every fill is at the TWAP.

## Other Costs

* **Funding**: paid or received hourly, see [Funding](funding.md). Not a fee; it flows between traders.
* **Deposits**: free on Hest; your wallet pays network gas.
* **Withdrawals**: network gas only.
* **Opening a market**: $20 listing fee plus your vault seed, see [Open a Market](open-a-market.md).

## Referrals

A referral programme for the Beta is in preparation. Fee discounts and referrer rewards will be announced on [X](https://x.com/HestSI) and [Discord](https://discord.gg/hest).
