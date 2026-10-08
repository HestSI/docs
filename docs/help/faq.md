---
description: >-
  Short answers to the questions traders ask most, with links to the full
  explanation.
---

# FAQ

## General

<details>

<summary>Does Hest have a token?</summary>

No. Anything claiming to be a Hest token without an official announcement on hest.si and [@HestSI](https://x.com/HestSI) is fake.

</details>

<details>

<summary>What is the difference between Hest Pools and Order Book markets?</summary>

|              | Hest Pools                                          | Order Book                                                                 |
| ------------ | --------------------------------------------------- | -------------------------------------------------------------------------- |
| Tokens       | Robinhood Chain memecoins Hyperliquid does not list | BTC, ETH, SOL, 180+ more, and the Robinhood Chain tokens Hyperliquid lists |
| Counterparty | Hest                                                | Other traders on Hyperliquid                                               |
| Price        | Worse of the Uniswap pool's spot and 15-minute TWAP | Hyperliquid's order book                                                   |
| Collateral   | WETH on Robinhood Chain                             | USDC on Hyperliquid                                                        |
| Fees         | 0.30% to open, 0.30% to close                       | Hyperliquid's fee plus the 0.05% Hest fee                                  |
| Leverage     | Up to 5x                                            | Up to the market's maximum                                                 |
| Funding      | None                                                | Hourly                                                                     |
| Profits      | To Earnings, locked 7 days, then paid               | Settled immediately on Hyperliquid                                         |

The **Route** column in Markets shows which is which.

</details>

<details>

<summary>Why are CASHCAT and PONS on the Order Book and not on Hest Pools?</summary>

Hyperliquid lists them, which gives them real two-sided liquidity. Robinhood Chain tokens that Hyperliquid lists trade on its order book through Hest, and cannot be opened as Hest Pools markets.

</details>

<details>

<summary>Which time zone does Hest use?</summary>

The app shows times in your own time zone. Official dates are announced in Pacific Time, and the Copilot allowance resets at midnight Pacific Time.

</details>

## Account and Wallets

<details>

<summary>Which wallets work?</summary>

MetaMask, Phantom, Rabby, Base (formerly Coinbase Wallet), Trust Wallet, OKX Wallet, Rainbow, Zerion, and Robinhood Wallet through its in-app browser on mobile. Smart-contract wallets such as Safe cannot sign in. See [Connect a Wallet](../getting-started/connect-a-wallet.md).

</details>

<details>

<summary>What is the Trading Wallet?</summary>

A new wallet Hest creates for you when you first sign in. You deposit into it, trade from it and withdraw from it to your connected wallet. See [Hest Trading Wallet](../getting-started/trading-wallet.md).

</details>

<details>

<summary>Is Hest custodial?</summary>

Partly. Your connected wallet stays fully yours. The Trading Wallet is shared control: you get its private key, and Hest keeps a copy so it can sign your trades without a wallet pop-up on every order. While a Hest Pools position is open, its collateral is held by Hest. Keep in the Trading Wallet what you are trading with. See [Security](security.md).

</details>

<details>

<summary>I lost my Trading Wallet key.</summary>

Click **Show Key** in Portfolio or in the wallet menu and sign with your connected wallet to see it again. It can be shown up to 5 times per hour.

</details>

<details>

<summary>Can I use my Trading Wallet outside Hest?</summary>

Yes. Import the key into any EVM wallet that supports private-key import. You can then move its ETH and WETH on Robinhood Chain and manage its Order Book positions directly on Hyperliquid. Hest Pools positions are managed only through Hest.

</details>

## Deposits and Withdrawals

<details>

<summary>Which networks can I deposit from?</summary>

Arbitrum, Ethereum, Base, Optimism, BNB Chain, Polygon, Solana and Robinhood Chain. The tokens accepted on each are listed in [Deposit](../getting-started/deposit.md). Anything else sent to a deposit address cannot be recovered.

</details>

<details>

<summary>My deposit failed. Where is my money?</summary>

Relay refunds a failed deposit on the network you sent from: to your connected wallet address on EVM networks, or to the Solana address you entered. If you sent from an exchange, the refund still goes to your connected wallet address, not back to the exchange.

</details>

<details>

<summary>Why do I need ETH on Robinhood Chain?</summary>

Opening a Hest Pools position, applying to open a market and withdrawing from the Hest Pools side are Robinhood Chain transactions from your Trading Wallet, paid in ETH (not WETH). About $1 of ETH covers hundreds of them. Closing a Hest Pools position costs you nothing: Hest sends the refund.

</details>

<details>

<summary>Can I withdraw to a different address?</summary>

No. Withdrawals only go to the wallet you signed in with. Hest charges no withdrawal fee. See [Withdraw](../getting-started/withdraw.md).

</details>

## Hest Pools

<details>

<summary>Why did my Hest Pools position open at a different price than the chart?</summary>

Every open and close uses the worse, for you, of the pool's spot price and its 15-minute TWAP. The chart comes from GeckoTerminal and is for display. See [Hest Pools Pricing](../markets/hest-pools-pricing.md).

</details>

<details>

<summary>The market is paused. What can I do?</summary>

Close your position, if you have one: closing always works, and liquidation, take profit and stop loss keep running. You cannot open new positions until the market resumes. An automatic pause lifts by itself once spot and TWAP are within 5% of each other.

</details>

<details>

<summary>Why are my Hest Pools profits locked?</summary>

Profits on Hest Pools go to your Earnings balance, are locked for 7 days, then reviewed and paid by Hest in WETH to your Trading Wallet, with a transaction link. The lock protects the markets from manipulation. Losses settle immediately, and the remaining collateral returns to your Trading Wallet at once. See [Earnings](../getting-started/earnings.md).

</details>

<details>

<summary>My closed position shows as closing. Is my refund lost?</summary>

No. The settlement amount was fixed when you closed. If the refund transaction could not be sent at once, the engine retries every minute until it is confirmed on Robinhood Chain.

</details>

<details>

<summary>My take profit triggered at a worse price than I set.</summary>

The Hest Pools engine checks take profit, stop loss and liquidation once a minute, and closes at the price of the check that catches the position. In a fast market that can be beyond your trigger price. See [How Hest Pools Work](../markets/how-hest-pools-work.md).

</details>

<details>

<summary>Why was my order rejected as too large?</summary>

One position can use at most 10% of the market's capacity and 2% of the token's DEX liquidity, and each side of the market has an open interest limit. The message tells you the most the market can take right now.

</details>

## Trading and Risk

<details>

<summary>What does the SI Score mean?</summary>

How the market can hurt a leveraged position right now, 0 to 100, higher is safer. On Order Book markets it is computed live from funding skew, crowding, volatility, liquidity depth and the worst 1-hour candle of the week. See [SI Score](../super-intelligence/si-score.md).

</details>

<details>

<summary>What is "Max Wick 7d" in Risk Shield?</summary>

The largest 1-hour candle of the last 7 days. If your liquidation distance is smaller than that, a normal bad hour liquidates you. See [Risk Shield](../super-intelligence/risk-shield.md).

</details>

<details>

<summary>What is the minimum order?</summary>

$10 on Order Book markets, a Hyperliquid rule (reduce-only orders are exempt). On Hest Pools the minimum margin is 0.002 WETH.

</details>

<details>

<summary>My Order Book order failed with "Your Hyperliquid account is not active yet".</summary>

Your Trading Wallet's Hyperliquid account is activated by its first USDC deposit. Deposit to the **Order Book** side first. See [Deposit](../getting-started/deposit.md).

</details>

<details>

<summary>Can I lose more than my margin?</summary>

No. On a Hest Pools position or an isolated Order Book position, your loss is limited to that position's margin. With cross margin on Order Book markets, a losing position can use your whole Order Book balance before it is liquidated, but not more.

</details>

## Help

<details>

<summary>Where do I get help?</summary>

Discord, [discord.gg/hest](https://discord.gg/hest): open a ticket. Security issues: open a ticket marked **Security** and the team moves it to a private channel. Legal: legal@hest.si.

</details>
