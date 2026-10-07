# Vault risks

Depositing into a Hest Pool vault is **leveraged exposure to the traders of one memecoin**, not yield farming. Read this before you deposit.

## You lose when traders win

If the market trends hard in one direction and most traders are on the right side, the vault pays them. A vault can lose a large share of its value in a day on a token that doubles. Fees soften this; they do not remove it.

## Concentration

Each vault backs **one** token. There is no diversification inside a vault. Spread deposits across markets if you want it.

## The protections, and their limits

* **30% position cap** – no single position can exceed 30% of the vault, so one trade cannot drain it. Many positions on the same side can still add up to a bad day.
* **TWAP pricing** – the mark is a 15-minute average, so a single wick or a single large DEX buy cannot be used to liquidate the vault's counterparties unfairly or to mark positions at a fake price. A sustained move still moves the TWAP.
* **SI Score gate and leverage caps** – tokens below 45 do not list; weak tokens open at 2x. This limits how fast the vault can bleed, not whether it can.

## Liquidity of your deposit

Withdrawals settle after the next TWAP window (up to 15 minutes). If the vault is near its position cap, your withdrawal may be queued until open interest falls, so that open positions stay backed.

## Smart contract risk

Hest Pool contracts are new. They will be published and verified on-chain, and audited before the Beta label comes off, but no audit removes the risk of a bug.

## Beta

Limits, fee splits and the TWAP window can change during the Beta with notice on Discord and X.

{% hint style="danger" %}
Only deposit what you can afford to lose entirely. Vault PnL can be negative for long stretches.
{% endhint %}
