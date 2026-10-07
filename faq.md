# FAQ

**Is Hest custodial?**
No. You connect your own wallet and sign every action. Hest never holds your keys.

**Which wallets work?**
Any EVM wallet: MetaMask, Rabby, Phantom, Trust Wallet, Coinbase Wallet, Robinhood Wallet. Mobile wallets over QR and email/Google login arrive with the next build.

**Which network is Hest on?**
Robinhood Chain, an Arbitrum Orbit chain. Deposits are USDC.

**What is the difference between an order book market and a Hest Pool market?**
Order book markets trade on Hyperliquid, with maker/taker fees and leverage up to 40x. Hest Pool markets trade against a community vault at a 15-minute TWAP, 0.30% fee, up to 5x. The Markets page tags each one; the Route column shows which is which.

**Why is CASHCAT on the order book and not in a pool?**
Hyperliquid lists it, which gives it real two-sided liquidity. Robinhood Chain tokens move to the book when Hyperliquid lists them.

**Why are there no Hest Pool markets yet?**
During the Beta every pool market is opened by its community, with a seed of at least $500. Nobody has opened one yet. You can be first: [Open a Market](markets-open-a-market.md).

**What does the SI Score mean?**
How the market can hurt you, 0 to 100, higher is safer. Memecoins are read on-chain and socially; majors are read on funding, crowding, volatility and depth. See [SI Score](super-intelligence-si-score.md).

**What is "Max wick 7d" in Risk Shield?**
The largest 1-hour drop in the last 7 days. If your liquidation distance is smaller than that, a normal bad hour liquidates you.

**What is funding?**
An hourly payment between longs and shorts that keeps the perpetual pinned to spot. Positive means longs pay. See [Funding](trading-funding.md).

**What is the builder fee?**
Hest's 0.03% on order book trades, collected through Hyperliquid's builder code system. You approve it once with a wallet signature (the prompt names Hyperliquid, where the order settles); it is itemised on every order.

**Can I lose more than my margin?**
No. Liquidation closes the position at the mark price; your loss is capped at the margin on that position (cross margin: at your balance).

**Times on the chart look wrong.**
Charts show your browser's local time zone; the zone is printed under the chart. Documentation videos are recorded in Pacific Time (Seattle).

**Where do I get help?**
Discord, [discord.gg/hest](https://discord.gg/hest), open a ticket. Security issues: write to security at hest.si.
