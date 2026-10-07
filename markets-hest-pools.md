# Hest Pools

Hest Pools are how a brand-new Robinhood Chain memecoin gets a perpetual market before any order book would list it.

## How a pool market works

* **The vault is the counterparty.** Depositors put USDC into the market's vault. Every trader on that market trades against the vault: when traders lose, the vault gains, and the reverse.
* **TWAP pricing.** The mark price is the 15-minute time-weighted average of the token's price on the Robinhood Chain DEX. A single wick cannot liquidate you, and a single buyer cannot move the mark. The strip shows the current TWAP and the countdown to the next window.
* **Position cap.** No single position can exceed 30% of the vault, so one trade can never drain it.
* **Leverage.** Up to 5x, set per market by Super Intelligence based on the token's volatility and liquidity. Markets with an SI Score under 60 open at 2x.
* **Maintenance margin** 6%.
* **Fees.** 0.30% of position size, split 70% to vault depositors, 20% to the market owner, 10% to Hest.

## Why not just an order book?

A fresh memecoin has no market makers. A book would be empty on one side and every market order would gap. A vault gives instant two-sided liquidity from day one, priced on something that cannot be manipulated in a single block.

When a token grows deep enough for a real order book, Hest routes it there and the vault winds down.

## During the Beta

Hest does not seed vaults. Every pool market is **opened by its community**: whoever seeds the vault (from $500) owns the market and keeps 20% of its fees. See [Open a Market](markets-open-a-market.md).

After launch, bonded tokens that reach $50k of DEX liquidity get a vault and a market automatically.
