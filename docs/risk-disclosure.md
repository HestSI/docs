---
description: The risks of trading leveraged perpetuals and funding vaults on Hest, stated plainly.
---

# Risk Disclosure

{% hint style="danger" %}
Trading perpetual contracts with leverage can result in the loss of your entire margin within minutes. Depositing into a Hest Pool Vault can result in the loss of your entire deposit. Read this page in full before using Hest, and do not trade with funds you cannot afford to lose.
{% endhint %}

**Last updated:** October 2026

This disclosure is part of the [Terms of Service](terms.md). It does not list every risk; it describes the ones Hest considers most important. Markets, technology and regulation change, and new risks appear.

## 1. Leverage and Liquidation

Leverage multiplies both gains and losses. At 10x, a 10% move against you wipes out your margin; at 40x, 2.5% does. Hest liquidates a position when its margin falls to the maintenance level, and the liquidation price is shown before you sign. Liquidation is automatic, happens at any hour, and cannot be undone. Ordinary intraday volatility is enough to liquidate a highly leveraged position: Risk Shield shows the worst one-hour candle of the past week precisely because such candles are common.

With cross margin, one losing position draws on your whole balance and can liquidate your other positions. With isolated margin, the loss is limited to the margin on that position.

Your loss is capped at the margin backing the position (or your balance, with cross margin). You cannot owe more than you deposited. Hest does not operate an insurance fund for Order Book Markets; Hyperliquid's mechanisms apply there.

## 2. Volatility and Memecoins

Digital assets are among the most volatile assets in the world, and memecoins are the most volatile digital assets. A memecoin can lose most of its value in hours, and many go to zero permanently. Prices move on social-media activity, coordinated buying and selling, dev-wallet actions and rumours, none of which is predictable. Historical behaviour, holder counts and SI Scores do not predict future prices.

## 3. Liquidity, Slippage and Gaps

Thin markets have wide spreads and little depth. A market order can fill far from the displayed price, and a large order can move the price against you. Prices can gap through your stop-loss or liquidation level, so a stop does not guarantee an exit price. Liquidity can disappear completely during stress, and a market that was deep yesterday can be empty today.

## 4. Order Book Markets and Hyperliquid

Order Book Markets are executed, margined and settled by the Hyperliquid protocol, a third party. Your positions and collateral in those markets live on Hyperliquid, under Hyperliquid's rules for margin, liquidation, funding, auto-deleveraging, delisting and downtime. Hyperliquid can pause or delist a market, change parameters, or suffer outages, bugs or exploits that Hest cannot prevent or remedy. If the Hest Interface is unavailable, you can manage these positions directly on Hyperliquid.

## 5. Hest Pool Markets, TWAP and Vaults

Hest Pool Markets are priced on a 15-minute time-weighted average of a token's DEX price. TWAP pricing lags the live price by design. During fast moves the mark can differ materially from spot, which affects entry, exit, PnL and liquidation. The reference DEX pool can be manipulated, drained or abandoned, and the oracle can fail or report stale prices.

Hest Pool Markets settle against a Vault, not an order book. Position size is capped relative to the Vault, and large or fast moves can affect the Vault's ability to pay winning traders in full. A Vault can be paused, and a market can be delisted, at which point you can close but not open positions.

## 6. Vault Deposits

Depositing into a Vault means becoming the counterparty to every trader in that market. When traders win, the Vault loses. The value of vault shares can fall sharply and can fall to zero. Fees paid to LPs are a share of fees actually collected and do not guarantee a positive return. Withdrawals are subject to a withdrawal window and may be limited while open interest is high, so you may not be able to exit when you want. The token behind a market can collapse faster than positions can be closed.

## 7. Smart-Contract, Oracle and Technology Risk

Hest relies on smart contracts (Hest Pools), oracles and DEX price sources, the Hyperliquid protocol, Robinhood Chain, wallet software, and ordinary web infrastructure. Any of these can contain bugs, be exploited, be congested, fork or go offline. Audits reduce but do not eliminate smart-contract risk. A failure can cause delayed or failed transactions, incorrect prices, unexpected liquidations, locked funds or permanent loss. Hest cannot reverse on-chain transactions.

## 8. Interface Availability

The Interface can be unavailable because of maintenance, bugs, hosting or network failures, attacks, or restrictions Hest applies. Liquidation and funding continue while the Interface is down. Keep enough margin to survive periods when you cannot act.

## 9. Wallet Security

You control your wallet and keys. Seed-phrase theft, malware, malicious browser extensions, phishing sites that imitate Hest, and signing requests you do not understand can lead to total loss of your assets. Hest never asks for your seed phrase. Check that you are on hest.si and read every wallet prompt before approving it.

## 10. Super Intelligence

SI Scores, Risk Shield verdicts, Copilot answers and project notes are automated outputs built from on-chain data, public social data, market data and statistical models. They can be late, incomplete, manipulated or wrong. They are not investment advice and do not predict prices. A high score does not make a market safe, and an "ok" Risk Shield verdict does not make a position safe. Copilot is a language model and can state incorrect numbers with confidence. Treat every output as one input to your own judgement, never as a decision.

## 11. Funding Payments

Perpetual contracts carry hourly funding between longs and shorts. Funding can be large and can change sign quickly. Over time funding can consume a significant part of your margin even when the price does not move against you.

## 12. Regulatory and Legal Risk

The legal treatment of digital assets, perpetual contracts and decentralised protocols is uncertain and differs between countries. Laws can change, and regulators can take action that restricts or ends access to the Services, to Hyperliquid, to Robinhood Chain or to particular tokens. You are responsible for knowing and complying with the laws that apply to you, including tax laws. Hest may restrict access from certain jurisdictions at any time.

## 13. Counterparty and Stablecoin Risk

Hest is non-custodial, but the Services depend on third parties. USDC is issued by a third party and can lose its peg, be frozen or be subject to issuer actions. Bridges used to move USDC to Robinhood Chain carry their own risk of delay, failure and exploit.

## 14. Beta Status

Hest is in Beta. Features, parameters, fees, markets and documentation can change, and services can be interrupted or discontinued. Beta software is more likely to contain defects than mature software.

## 15. Your Responsibility

You are responsible for every order and transaction you sign, for the security of your wallet, for your margin and leverage choices, for your tax obligations and for complying with the laws of your jurisdiction. Hest provides software and information, not advice, and cannot reverse your transactions.

If you do not understand or do not accept these risks, do not use Hest.
