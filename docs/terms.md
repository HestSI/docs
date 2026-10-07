---
description: The terms that govern your use of the Hest interface, the Hest Trading Wallet, Hest Pools and Super Intelligence.
---

# Terms of Service

**Last updated:** October 2026

Please read these Terms of Service (the "Terms") carefully. They are a binding agreement between you and Hest Super Intelligence ("Hest", "we", "us") and govern your access to and use of hest.si, its subdomains, the Hest web application, the Hest Trading Wallet, Hest Pools, Super Intelligence and every related service (together, the "Services"). By connecting a wallet, signing a message or transaction, or otherwise using the Services, you agree to these Terms. If you do not agree, do not use the Services.

## 1. Definitions

**Interface** means the hest.si website and web application that Hest operates.

**Connected Wallet** means the wallet you connect to the Interface and sign in with. It identifies you, and withdrawals are sent only to it.

**Trading Wallet** means the wallet Hest creates for you after you sign in, which holds your deposits and from which your trades are placed. Hest keeps a copy of its private key, as described in section 2.1.

**Order Book Markets** means perpetual markets traded on the Hyperliquid protocol's order book from the Hyperliquid account of your Trading Wallet, and executed, margined and settled by Hyperliquid under Hyperliquid's own terms.

**Hest Pool Markets** means perpetual markets on Robinhood Chain tokens in which Hest is the counterparty, priced from the token's Uniswap pools on Robinhood Chain and collateralised in WETH.

**Market Opener** means a user whose application to open a Hest Pool Market has been accepted by Hest and who has provided the market's seed.

**Earnings** means amounts credited to you for profits on Hest Pool Markets, a Market Opener's share of fees and profit, and any bonuses, which are locked and paid as described in section 5.

**Super Intelligence** or **SI** means Hest's automated market analysis, including the SI Score, Risk Shield and Copilot.

**Digital Assets** means USDC, ETH, WETH and any other token supported by the Services.

## 2. Nature of the Services

2.1 **Trading Wallet and custody.** When you sign in, Hest creates a Trading Wallet for you. Its private key is shown to you at creation and again on a request signed with your Connected Wallet. Hest keeps a copy of the key and uses it to sign transactions on your instructions given through the Interface, including orders, transfers of collateral and withdrawals to your Connected Wallet. Hest is therefore not non-custodial for the Trading Wallet: you and Hest can both control it. Hest does not hold the keys of your Connected Wallet. Hest cannot reverse an on-chain transaction once it has been broadcast.

2.2 **Counterparties.** In Order Book Markets, Hest is not a party to your trades: your counterparty is another participant in the Hyperliquid order book. In Hest Pool Markets, Hest is your counterparty.

2.3 **Hyperliquid.** When you trade an Order Book Market, Hest signs the order with your Trading Wallet's key on your instruction and it is submitted to the Hyperliquid protocol. The resulting positions, margin and collateral exist in the Hyperliquid account of your Trading Wallet, are governed by Hyperliquid's terms, and can be managed directly on Hyperliquid using your Trading Wallet key. Hest collects a builder fee on these orders through Hyperliquid's builder code mechanism, approved once for your Trading Wallet.

2.4 **No advice.** Nothing on the Services is investment, financial, legal, tax or trading advice. Hest does not recommend any trade, market, leverage or market seed. See section 8 for Super Intelligence.

2.5 **No brokerage.** Hest is not a licensed broker, dealer, exchange, custodian, money transmitter or investment adviser, and does not act as your fiduciary.

## 3. Eligibility and Restricted Persons

3.1 You may use the Services only if you are at least 18 years old (or the age of majority where you live, if higher) and have the legal capacity to enter into these Terms.

3.2 You may not use the Services if doing so is prohibited by the laws that apply to you, including where trading leveraged digital-asset derivatives is not permitted. You are responsible for determining whether your use of the Services is lawful where you live and where you access them from.

3.3 You may not use the Services if you are, or act for, a person on any sanctions list maintained by the United Nations, the European Union, the United Kingdom, the United States or any other competent authority, or if you are otherwise prohibited by applicable law from using them.

3.4 You may not use a VPN, proxy or any other method to disguise your location in order to evade this section. Hest may use geolocation and on-chain screening to enforce this section and may restrict the Interface for addresses or regions without notice.

3.5 By using the Services you represent and warrant, on every use, that you meet the requirements of this section.

## 4. Your Wallets, Your Keys, Your Orders

4.1 You are solely responsible for your Connected Wallet, its seed phrase and private keys, your copy of the Trading Wallet key, and the security of the device and software you use. Anyone with the Trading Wallet key can control the Trading Wallet. Hest will never ask for your seed phrase or for your Trading Wallet key.

4.2 Every order, deposit, withdrawal and other action you submit through the Interface is your own instruction, whether you sign it with your Connected Wallet or Hest signs it with your Trading Wallet on your behalf. Review the confirmation shown by the Interface before you confirm. Confirmed transactions are final.

4.3 You are responsible for maintaining enough margin on your positions. Positions that fall to maintenance margin are liquidated automatically, as described in [Leverage and Liquidation](leverage-and-liquidation.md). Liquidation can happen at any time, including while the Interface is unavailable.

4.4 Blockchain networks, Relay and the Hyperliquid protocol may be congested, paused or forked. Transactions may fail, be delayed or be included at a different price. Hest is not responsible for these events.

4.5 **Deposits.** Deposits are routed to your Trading Wallet by Relay, a third-party service, through a deposit address shown in the Interface. The Interface shows the Hest deposit fee, Relay's fee and network fees before you send. You must send only the token and network shown for that deposit address; Hest cannot recover tokens that are not supported or that are sent on the wrong network.

4.6 **Withdrawals.** Withdrawals from your Trading Wallet are sent only to your Connected Wallet. Withdrawals from Order Book Markets are subject to Hyperliquid's withdrawal fee and minimum. Bridged withdrawals are routed by Relay.

## 5. Hest Pool Markets

5.1 **Hest as counterparty.** When you open a position on a Hest Pool Market, Hest takes the other side. Every open and close is priced at the less favourable to you of the token's spot price and its 15-minute time-weighted average price (TWAP) on its Uniswap pools on Robinhood Chain. Hest does not guarantee that this price reflects any price at which you could trade elsewhere.

5.2 **Settlement.** When a position closes at a loss, the loss is retained and the remaining collateral is returned to your Trading Wallet. When a position closes at a profit, the collateral is returned to your Trading Wallet and the profit is credited to your Earnings.

5.3 **Earnings.** Each amount credited to Earnings is locked for 7 days. After the lock, Hest reviews the activity that gave rise to it and pays it to you. Hest may withhold or reverse Earnings that Hest reasonably determines result from a breach of section 9, from linked accounts trading against each other, or from a faulty or manipulated price.

5.4 **Limits and parameters.** Each Hest Pool Market has a capacity. Position size and open interest are capped as described in [How Hest Pools Work](how-hest-pools-work.md). Hest may change market parameters (maximum leverage, capacity, caps, fees, maintenance margin, price sources), a market may pause automatically on abnormal price moves, and Hest may pause or close a market whose token no longer meets the listing criteria, whose price source fails, or where Hest reasonably suspects manipulation.

5.5 **Opening a market.** You may apply to open a Hest Pool Market for a token that meets the criteria published in [Open a Market](open-a-market.md) by paying the listing fee and providing a seed in WETH. Hest reviews every application and may reject any application; if it does, the listing fee and the seed are refunded.

5.6 **Market Opener terms.** The seed bears the market's losses first. In return the Market Opener receives a share of the market's trading fees and of its profit, as described in [Open a Market](open-a-market.md), credited to Earnings and paid under section 5.3. The seed is locked for 7 days; its value at withdrawal includes the unrealised profit and loss of open positions; and withdrawing the seed ends the Market Opener's shares. The fee and profit shares are not a guarantee of income and may be suspended if the Market Opener breaches these Terms.

## 6. Fees

6.1 Fees are shown in the Interface before you confirm and are described in [Fees](fees.md). Hest may change fees with notice on the official channels. Fees on Order Book Markets consist of Hyperliquid's own fees plus Hest's builder fee. Hest charges a deposit fee and no withdrawal fee.

6.2 You are responsible for network (gas) fees, including ETH for transactions from your Trading Wallet on Robinhood Chain, and for Relay's fees.

6.3 Trading fees are collected in the collateral of the market (USDC on Order Book Markets, WETH on Hest Pool Markets) and are non-refundable once an order is executed, except as stated in section 5.5.

## 7. Taxes

You are solely responsible for determining and paying any taxes that apply to your use of the Services, including taxes on trading gains, Earnings and Market Opener income. Hest does not provide tax reporting or withhold tax.

## 8. Super Intelligence

8.1 SI Scores, Risk Shield verdicts, Copilot answers and any other Super Intelligence output are informational outputs of automated analysis. They are generated from market data and statistical models that can be incomplete, delayed, manipulated or wrong.

8.2 Super Intelligence output is not investment advice, is not a recommendation to trade, and does not predict prices. A high SI Score does not mean a market is safe; a Risk Shield "ok" verdict does not mean a position cannot be liquidated.

8.3 Copilot is an automated assistant. It can make mistakes, misread numbers and produce confident but incorrect statements. Verify anything that matters before acting on it.

8.4 Hest may change the scoring methodology at any time and does not guarantee any level of accuracy, availability or latency for Super Intelligence.

## 9. Prohibited Conduct

You agree not to, and not to help anyone else to:

* violate any law, regulation or sanctions program, or use the Services where doing so is prohibited;
* engage in market manipulation of any kind, including wash trading, spoofing, layering, manipulation of the price sources of Hest Pool Markets, pump-and-dump schemes, trading between linked accounts or coordinated trading against Hest Pool Markets;
* exploit a bug, vulnerability or unintended behaviour of the Interface, Hest Pool Markets, Hyperliquid or any price source, or fail to report one you discover;
* attack, overload, scrape at scale, reverse engineer or interfere with the Services or their infrastructure;
* use the Services to launder money, finance terrorism or move the proceeds of crime;
* apply to open markets for tokens you know to be fraudulent, or trade on a market you opened using information not available to other users;
* impersonate Hest, its team or another user, or misrepresent your affiliation with Hest;
* circumvent any limit, restriction or suspension that Hest has applied.

Hest may restrict, suspend or terminate access to the Interface for any address or person it reasonably believes has breached this section, and may report unlawful conduct to the relevant authorities.

## 10. Intellectual Property

10.1 The Interface, the Hest name and logo, the Hest mascot, Super Intelligence and all related content are owned by Hest or its licensors and are protected by intellectual-property laws. Open-source components are licensed under their own licenses, as published in the relevant repositories.

10.2 Hest grants you a limited, revocable, non-exclusive, non-transferable licence to use the Interface for its intended purpose in accordance with these Terms. You may not copy, modify, distribute, sell or lease any part of the Services except as permitted by an open-source licence.

10.3 Third-party names and logos, including Hyperliquid and Robinhood, belong to their owners. Their appearance on the Interface describes integration and does not imply endorsement or partnership.

## 11. Third-Party Services

The Services depend on third parties that Hest does not control, including Hyperliquid, Robinhood Chain and the other supported networks, Relay, wallet providers, Uniswap and other DEX price sources, data providers, hosting and infrastructure providers. Your use of those services is governed by their own terms. Hest is not responsible for their availability, accuracy, security or conduct, and does not endorse any token that can be traded through the Services.

## 12. Beta Status and Availability

12.1 The Services are in Beta. Features, parameters, fees, markets and documentation can change, and the Services may be modified, suspended or discontinued, in whole or in part, at any time with notice on the official channels where practical.

12.2 Hest does not guarantee that the Interface will be available, uninterrupted, secure or free of errors. Outages may prevent you from opening, managing or closing positions, including during liquidation. Keep enough margin to withstand periods when the Interface is unavailable. Order Book Market positions can also be managed directly on Hyperliquid using your Trading Wallet key.

## 13. Disclaimer of Warranties

THE SERVICES ARE PROVIDED "AS IS" AND "AS AVAILABLE" WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, TITLE AND NON-INFRINGEMENT. HEST DOES NOT WARRANT THAT THE SERVICES, THE PRICE SOURCES, RELAY, HYPERLIQUID OR ANY THIRD-PARTY SERVICE WILL BE ACCURATE, RELIABLE, SECURE, UNINTERRUPTED OR FREE OF ERRORS, OR THAT ANY SUPER INTELLIGENCE OUTPUT WILL BE CORRECT. YOU USE THE SERVICES AT YOUR OWN RISK. SOME JURISDICTIONS DO NOT ALLOW THE EXCLUSION OF IMPLIED WARRANTIES, SO SOME OF THESE EXCLUSIONS MAY NOT APPLY TO YOU.

## 14. Assumption of Risk

You acknowledge that you have read and understood the [Risk Disclosure](risk-disclosure.md), that trading leveraged perpetual contracts and providing a market seed carry a high risk of total loss, that Hest holds a copy of your Trading Wallet key, that digital-asset markets are volatile and lightly regulated, that software and blockchain networks can contain bugs, that price sources can fail, and that the regulatory treatment of digital assets is uncertain and may change. You assume all of these risks.

## 15. Limitation of Liability

TO THE MAXIMUM EXTENT PERMITTED BY LAW, HEST AND ITS AFFILIATES, CONTRIBUTORS, OFFICERS, EMPLOYEES AND AGENTS WILL NOT BE LIABLE FOR ANY INDIRECT, INCIDENTAL, SPECIAL, CONSEQUENTIAL, EXEMPLARY OR PUNITIVE DAMAGES, OR FOR ANY LOSS OF PROFITS, REVENUE, DATA, DIGITAL ASSETS OR GOODWILL, ARISING OUT OF OR RELATED TO THE SERVICES, HOWEVER CAUSED AND UNDER ANY THEORY OF LIABILITY, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGES. THIS INCLUDES LOSSES FROM TRADING, LIQUIDATION, THE PERFORMANCE OF A MARKET YOU OPENED, SPOT OR TWAP PRICING, SOFTWARE BUGS OR EXPLOITS, HYPERLIQUID OR NETWORK FAILURES, WALLET COMPROMISE, PHISHING, OR RELIANCE ON SUPER INTELLIGENCE OUTPUT. IN NO EVENT WILL HEST'S TOTAL LIABILITY TO YOU FOR ALL CLAIMS EXCEED THE GREATER OF (A) THE FEES YOU PAID TO HEST IN THE TWELVE MONTHS BEFORE THE EVENT GIVING RISE TO THE CLAIM AND (B) ONE HUNDRED US DOLLARS (USD 100).

## 16. Indemnification

You agree to defend, indemnify and hold harmless Hest and its affiliates, contributors, officers, employees and agents from and against any claim, demand, loss, liability, damage, cost or expense (including reasonable legal fees) arising out of or related to your use of the Services, your breach of these Terms, your violation of any law or the rights of a third party, or any market you open.

## 17. Suspension and Termination

Hest may suspend or terminate your access to the Interface at any time, with or without notice, if it reasonably believes you have breached these Terms, if required by law, or to protect the Services or other users. Termination of Interface access does not affect assets in your Connected Wallet. Assets in your Trading Wallet remain yours: you can withdraw them to your Connected Wallet, unless the law requires otherwise, or use your Trading Wallet key to manage them, including positions on Hyperliquid, directly. Sections 7, 8, 10 and 13 to 20 survive termination.

## 18. Governing Law and Dispute Resolution

18.1 These Terms are governed by the laws of England and Wales, without regard to its conflict-of-laws rules.

18.2 Any dispute arising out of or relating to these Terms or the Services will be resolved by binding arbitration administered by the London Court of International Arbitration (LCIA) under the LCIA Arbitration Rules in force when the request for arbitration is filed, seated in London, England, in the English language, before a single arbitrator. You and Hest waive any right to a jury trial and to participate in a class action, to the extent permitted by law.

18.3 Before starting arbitration, a party must send a written description of the dispute to the other party and allow 30 days for good-faith resolution. For Hest, the notice address is legal@hest.si.

18.4 Nothing in this section limits any mandatory consumer-protection rights you have under the laws of the country where you live, including any right to bring a claim before your local courts where that law does not allow it to be waived.

## 19. Changes to These Terms

Hest may update these Terms from time to time. The "Last updated" date at the top of this page shows the current version. Material changes will be announced on the official channels (hest.si, @HestSI on X, discord.gg/hest) at least 7 days before they take effect where practical. Continued use of the Services after a change takes effect means you accept the updated Terms.

## 20. General

20.1 These Terms, together with the [Privacy Policy](privacy.md) and the [Risk Disclosure](risk-disclosure.md), are the entire agreement between you and Hest regarding the Services.

20.2 If any provision of these Terms is held unenforceable, the remaining provisions remain in force and the unenforceable provision is modified to the minimum extent necessary.

20.3 Hest's failure to enforce a provision is not a waiver of its right to do so later.

20.4 You may not assign these Terms. Hest may assign them to an affiliate or a successor.

20.5 Hest is not liable for any failure or delay caused by events beyond its reasonable control, including network or protocol failures, acts of government, war, pandemic or natural disaster.

20.6 Notices to you may be given through the Interface or the official channels. Notices to Hest go to legal@hest.si.

## 21. Contact

Legal: legal@hest.si · Support and security: tickets on [discord.gg/hest](https://discord.gg/hest), marked with the topic.
