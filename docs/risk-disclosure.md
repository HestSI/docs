---
description: The risks of trading leveraged perpetuals and opening Hest Pools markets on Hest, stated plainly.
---

# Risk Disclosure

{% hint style="danger" %}
Trading perpetual contracts with leverage can result in the loss of your entire margin within minutes. Providing the seed for a Hest Pools market can result in the loss of the entire seed. Funds in your Trading Wallet are exposed to the security of Hest's systems. Read this page in full before using Hest, and do not trade with funds you cannot afford to lose.
{% endhint %}

**Last updated:** October 2026

This disclosure is part of the [Terms of Service](terms.md). It does not list every risk; it describes the ones Hest considers most important. Markets, technology and regulation change, and new risks appear.

## 1. Leverage and Liquidation

Leverage multiplies both gains and losses. At 10x, a 10% move against you wipes out your margin; at 40x, 2.5% does. A position is liquidated when its margin falls to the maintenance level, and the liquidation price is shown before you confirm. Liquidation is automatic, happens at any hour, and cannot be undone. Ordinary intraday volatility is enough to liquidate a highly leveraged position: Risk Shield shows the worst one-hour candle of the past week precisely because such candles are common.

With cross margin, one losing position draws on your whole balance and can liquidate your other positions. With isolated margin, the loss is limited to the margin on that position.

Your loss is capped at the margin backing the position (or your Order Book balance, with cross margin). You cannot owe more than you deposited. Hest does not operate an insurance fund for Order Book Markets; Hyperliquid's mechanisms apply there.

## 2. Volatility and Memecoins

Digital assets are among the most volatile assets in the world, and memecoins are the most volatile digital assets. A memecoin can lose most of its value in hours, and many go to zero permanently. Prices move on social-media activity, coordinated buying and selling, dev-wallet actions and rumours, none of which is predictable. Historical behaviour, holder counts and SI Scores do not predict future prices.

## 3. Liquidity, Slippage and Gaps

Thin markets have wide spreads and little depth. A market order can fill far from the displayed price, and a large order can move the price against you. Prices can gap through your stop-loss or liquidation level, so a stop does not guarantee an exit price. Liquidity can disappear completely during stress, and a market that was deep yesterday can be empty today.

## 4. Order Book Markets and Hyperliquid

Order Book Markets are executed, margined and settled by the Hyperliquid protocol, a third party. Your positions and collateral in those markets live in the Hyperliquid account of your Trading Wallet, under Hyperliquid's rules for margin, liquidation, funding, auto-deleveraging, delisting and downtime. Hyperliquid can pause or delist a market, change parameters, or suffer outages, bugs or exploits that Hest cannot prevent or remedy. If the Hest Interface is unavailable, you can manage these positions directly on Hyperliquid by importing your Trading Wallet key into another wallet.

## 5. Hest Pools Markets

On Hest Pools Markets, Hest is your counterparty. Prices come from the token's Uniswap pools on Robinhood Chain: every open and close uses the worse, for you, of the spot price and the 15-minute time-weighted average price (TWAP). Your entry and exit are therefore worse than either price alone, and after fast moves the price you receive can differ materially from prices shown elsewhere. The reference pools can be manipulated, drained or abandoned, and a token can lose most of its value faster than positions can be closed.

Collateral is WETH, whose dollar value moves with the price of ETH. Network fees on Robinhood Chain are paid in ETH; without enough ETH in your Trading Wallet, transactions cannot be sent.

Position size and open interest are capped. A market can pause automatically on abnormal price moves, during which you cannot open new positions, and Hest can change parameters or stop a market.

Profits on Hest Pools Markets are credited to your Earnings balance, locked for 7 days, and paid only after Hest has reviewed them. Payment depends on Hest. Profits that Hest determines result from manipulation, linked accounts, a breach of the Terms or a faulty price can be withheld. Losses are settled immediately.

## 6. Opening a Market and the Seed

A market opener's seed is first-loss capital: when traders on the market win, the loss is taken from the seed first. The seed can fall sharply in value and can be lost entirely. It is locked for 7 days, and its value at withdrawal includes the unrealised profit and loss of open positions, so you may not be able to exit when you want or at the value you expect. Fee and profit shares are paid only from fees and profit actually earned and do not guarantee a positive return.

## 7. Trading Wallet and Custody

Hest creates a Trading Wallet for you and keeps a copy of its private key so that it can sign your trades. Hest is therefore not non-custodial for the Trading Wallet: funds in it can be lost if Hest's systems are compromised, misused or unavailable, as well as if your own copy of the key is stolen. Anyone with the key controls the wallet. Keep in the Trading Wallet only what you are trading with, and withdraw the rest to your connected wallet.

## 8. Technology and Third Parties

Hest relies on Robinhood Chain, Arbitrum and the other networks it supports, Uniswap pools as price sources, the Hyperliquid protocol, Relay for deposits and bridged withdrawals, wallet software and ordinary web infrastructure. Any of these can contain bugs, be exploited, be congested, fork or go offline. A failure can cause delayed or failed transactions, incorrect prices, unexpected liquidations, locked funds or permanent loss. Hest cannot reverse on-chain transactions.

## 9. Interface Availability

The Interface can be unavailable because of maintenance, bugs, hosting or network failures, attacks, or restrictions Hest applies. Liquidation and funding continue while the Interface is down. Keep enough margin to survive periods when you cannot act.

## 10. Wallet Security

You control your connected wallet and its keys, and you hold a copy of your Trading Wallet key. Seed-phrase or key theft, malware, malicious browser extensions, phishing sites that imitate Hest, and signing requests you do not understand can lead to total loss of your assets. Hest never asks for your seed phrase or for your Trading Wallet key. Check that you are on hest.si and read every wallet prompt before approving it.

## 11. Super Intelligence

SI Scores, Risk Shield verdicts and Copilot answers are automated outputs built from market data and statistical models. They can be late, incomplete, manipulated or wrong. They are not investment advice and do not predict prices. A high score does not make a market safe, and an "ok" Risk Shield verdict does not make a position safe. Copilot is automated and can state incorrect numbers with confidence. Treat every output as one input to your own judgement, never as a decision.

## 12. Funding Payments

Order Book perpetual contracts carry hourly funding between longs and shorts. Funding can be large and can change sign quickly. Over time funding can consume a significant part of your margin even when the price does not move against you.

## 13. Regulatory and Legal Risk

The legal treatment of digital assets, perpetual contracts and decentralised protocols is uncertain and differs between countries. Laws can change, and regulators can take action that restricts or ends access to the Services, to Hyperliquid, to Robinhood Chain or to particular tokens. You are responsible for knowing and complying with the laws that apply to you, including tax laws. Hest may restrict access from certain jurisdictions at any time.

## 14. Deposits, Withdrawals and Stablecoins

Deposits are routed to your Trading Wallet through Relay, a third party. Deposits and bridged withdrawals carry the risk of delay, failure, refund or exploit. A token that is not supported, or a token sent on the wrong network, cannot be recovered. Withdrawals go only to your connected wallet. USDC and other stablecoins are issued by third parties and can lose their peg, be frozen or be subject to issuer actions. WETH is a wrapped form of ETH and depends on its token contract.

## 15. Beta Status

Hest is in Beta. Features, parameters, fees, markets and documentation can change, and services can be interrupted or discontinued. Beta software is more likely to contain defects than mature software.

## 16. Your Responsibility

You are responsible for every order and transaction you sign or instruct Hest to sign, for the security of your wallets and of your copy of the Trading Wallet key, for your margin and leverage choices, for your tax obligations and for complying with the laws of your jurisdiction. Hest provides software, the execution of your instructions and information, not advice, and cannot reverse on-chain transactions.

If you do not understand or do not accept these risks, do not use Hest.
