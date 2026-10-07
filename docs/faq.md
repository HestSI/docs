# FAQ

**Does Hest have a token?**
No. Anything claiming to be a Hest token without an official announcement on hest.si and [@HestSI](https://x.com/HestSI) is fake.

**What is the difference between Hest Pools and Order Book markets?**
Hest Pools markets are Robinhood Chain memecoins that Hyperliquid does not list: Hest is the counterparty, the price comes from the token's Uniswap pools, collateral is WETH, the fee is 0.30% to open and 0.30% to close, leverage up to 5x. Order Book markets trade on Hyperliquid's order book with USDC collateral, Hyperliquid's fee plus the 0.05% Hest fee, and leverage up to the market's maximum. The Route column in Markets shows which is which.

**Why are CASHCAT and PONS on the Order Book and not on Hest Pools?**
Hyperliquid lists them, which gives them real two-sided liquidity. Robinhood Chain tokens that Hyperliquid lists trade on its order book.

**What is the Trading Wallet?**
A separate wallet Hest creates for you when you first sign in. You deposit into it, trade from it and withdraw from it to your connected wallet. See [Hest Trading Wallet](trading-wallet.md).

**Is Hest custodial?**
Partly. Your connected wallet stays fully yours. The Trading Wallet is shared control: you get its private key, and Hest keeps a copy so it can sign your trades without a wallet pop-up on every order. Keep in it what you are trading with.

**I lost my Trading Wallet key.**
Click **Show Key** in Portfolio and sign with your connected wallet to see it again.

**Which wallets work?**
MetaMask, Phantom, Rabby, Base (formerly Coinbase Wallet), Trust Wallet, OKX Wallet, Rainbow, Zerion, and Robinhood Wallet through its in-app browser on mobile.

**Which networks can I deposit from?**
Ethereum, Arbitrum, Base, Optimism, BNB Chain, Polygon, Solana and Robinhood Chain. The tokens accepted on each are listed in [Deposit](deposit.md). Anything else sent to a deposit address cannot be recovered.

**Why do I need ETH on Robinhood Chain?**
Every Hest Pools trade and withdrawal is a Robinhood Chain transaction, and those are paid in ETH. About $1 of ETH covers hundreds of them.

**Can I withdraw to a different address?**
No. Withdrawals only go to the wallet you signed in with. Hest charges no withdrawal fee.

**Why are my Hest Pools profits locked?**
Profits on Hest Pools go to your Earnings balance, are locked for 7 days, then reviewed and paid by Hest with a transaction link. The lock protects the markets from manipulation. Losses settle immediately, and the remaining collateral returns to your Trading Wallet at once. See [Earnings](earnings.md).

**What does the SI Score mean?**
How the market can hurt you right now, 0 to 100, higher is safer. It is computed live from funding skew, crowding, volatility, liquidity depth and the worst 1-hour candle of the week. See [SI Score](si-score.md).

**What is "Max Wick 7D" in Risk Shield?**
The largest 1-hour drop in the last 7 days. If your liquidation distance is smaller than that, a normal bad hour liquidates you.

**What is the minimum order on Order Book markets?**
$10, a Hyperliquid rule.

**Can I lose more than my margin?**
On a single isolated position, your loss is limited to its margin. With cross margin on Order Book markets, a losing position can use your whole Order Book balance before it is liquidated.

**Times on the chart look wrong.**
The app shows times in your own time zone, printed under the chart. Official dates are announced in Pacific Time.

**Where do I get help?**
Discord, [discord.gg/hest](https://discord.gg/hest): open a ticket. Security issues: open a ticket marked **Security** and the team moves it to a private channel. Legal: legal@hest.si.
