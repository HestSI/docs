---
description: The terms that govern your use of the Hest interface, Hest Pools and Super Intelligence.
---

# Terms of Service

{% hint style="warning" %}
Beta draft. These terms apply during the Beta and will be reviewed by counsel before public launch. Bracketed items are completed at that time. Using Hest after an update means you accept the updated terms.
{% endhint %}

**Last updated:** October 2026

Please read these Terms of Service (the "Terms") carefully. They are a binding agreement between you and [Hest entity] ("Hest", "we", "us") and govern your access to and use of hest.si, its subdomains, the Hest web application, the Hest Pools smart contracts, Super Intelligence and every related service (together, the "Services"). By connecting a wallet, signing a message or transaction, or otherwise using the Services, you agree to these Terms. If you do not agree, do not use the Services.

## 1. Definitions

**Interface** means the hest.si website and web application that Hest operates.

**Order Book Markets** means perpetual markets that the Interface routes to the Hyperliquid protocol. Orders in these markets are signed by your wallet and executed, margined and settled by Hyperliquid under Hyperliquid's own terms.

**Hest Pool Markets** means perpetual markets created through the Hest Pools smart contracts, priced on a time-weighted average price (TWAP) and settled against a Vault.

**Vault** means the USDC pool that is the counterparty to a Hest Pool Market, funded by depositors ("LPs") who receive vault shares.

**Market Owner** means the user who created a Hest Pool Market by paying the listing fee and seeding its Vault.

**Super Intelligence** or **SI** means Hest's automated market analysis, including the SI Score, Risk Shield, Copilot and project notes.

**Digital Assets** means USDC and any other token supported by the Services.

## 2. Nature of the Services

2.1 **Non-custodial.** Hest never holds, controls or has access to your Digital Assets or private keys. Every deposit, order, withdrawal and vault action is a transaction or message that you sign with your own wallet. Hest cannot reverse, cancel or recover a transaction after you sign it.

2.2 **Interface, not counterparty.** The Interface is software that helps you interact with third-party protocols (Hyperliquid, Robinhood Chain, token contracts) and with the Hest Pools smart contracts. Hest is not a party to any trade. In Order Book Markets your counterparty is another participant in the Hyperliquid order book; in Hest Pool Markets your counterparty is the Vault.

2.3 **Routing to Hyperliquid.** When you trade an Order Book Market, the Interface prepares an order for the Hyperliquid protocol and asks your wallet to sign it. The positions, margin and collateral that result exist on Hyperliquid, are governed by Hyperliquid's terms, and can be managed directly on Hyperliquid without Hest. Hest collects a builder fee on these orders through Hyperliquid's builder code mechanism, which you approve once with a wallet signature and can revoke on Hyperliquid at any time.

2.4 **No advice.** Nothing on the Services is investment, financial, legal, tax or trading advice. Hest does not recommend any trade, market, leverage or vault. See section 8 for Super Intelligence.

2.5 **No brokerage.** Hest is not a broker, dealer, exchange, custodian, money transmitter or investment adviser, and does not act as your agent or fiduciary.

## 3. Eligibility and Restricted Persons

3.1 You may use the Services only if you are at least 18 years old (or the age of majority where you live, if higher) and have the legal capacity to enter into these Terms.

3.2 You may not use the Services if you are located in, incorporated in, or a resident of a jurisdiction where trading leveraged digital-asset derivatives is prohibited or where Hest has chosen not to offer the Services ("Restricted Jurisdiction"). The list of Restricted Jurisdictions is published at [restricted-jurisdictions page] and may change. It includes, at a minimum, the United States of America, and any country or territory subject to comprehensive sanctions.

3.3 You may not use the Services if you are, or act for, a person on any sanctions list maintained by the United Nations, the European Union, the United Kingdom, the United States or [applicable authority], or if you are otherwise prohibited by applicable law from using them.

3.4 You may not use a VPN, proxy or any other method to disguise your location in order to access the Services from a Restricted Jurisdiction. Hest may use geolocation and on-chain screening to enforce this section and may restrict the Interface for addresses or regions without notice.

3.5 By using the Services you represent and warrant, on every use, that you meet the requirements of this section.

## 4. Your Wallet, Your Keys, Your Orders

4.1 You are solely responsible for the wallet you connect, its seed phrase and private keys, and the security of the device and software you use. Hest will never ask for your seed phrase or private key.

4.2 Every order, deposit, withdrawal, approval and vault transaction that you sign is your own instruction. Review the confirmation screen and your wallet prompt before signing. Signed transactions are final.

4.3 You are responsible for maintaining enough margin on your positions. Positions that fall to maintenance margin are liquidated automatically, as described in [Leverage and Liquidation](trading-leverage-and-liquidation.md). Liquidation can happen at any time, including while the Interface is unavailable.

4.4 Blockchain networks and the Hyperliquid protocol may be congested, paused or forked. Transactions may fail, be delayed or be included at a different price. Hest is not responsible for these events.

## 5. Hest Pool Markets and Vaults

5.1 **Creating a market.** A Market Owner may create a Hest Pool Market for a token that meets the eligibility criteria published in [Open a Market](markets-open-a-market.md). The listing fee is non-refundable. The seed deposit becomes vault shares like any other deposit.

5.2 **Vault deposits.** Depositing USDC into a Vault means taking the opposite side of the traders in that market. The value of vault shares rises when traders lose and falls when traders win, and can fall to zero. Fees paid to LPs do not guarantee a positive return. Withdrawals may be delayed by the withdrawal window described in [How Vaults Earn](pools-how-vaults-earn.md) and may be limited while open interest is high.

5.3 **Pricing.** Hest Pool Markets are marked at the 15-minute TWAP of the token's reference DEX price. TWAP pricing lags spot by design. Hest does not guarantee that the mark reflects any price at which you could trade elsewhere.

5.4 **Parameters.** Hest may change market parameters (maximum leverage, position caps, fees, maintenance margin, oracle sources) and may pause or delist a market whose token no longer meets the criteria, whose oracle fails, or where Hest reasonably suspects manipulation. Open positions in a delisted market can be closed; new positions cannot be opened.

5.5 **Market Owner fee share.** The Market Owner's share of fees is paid as described in [Open a Market](markets-open-a-market.md). It is a share of fees actually collected and is not a guarantee of income. It may be suspended if the Market Owner breaches these Terms.

## 6. Fees

6.1 Fees are shown on the order confirmation before you sign and are described in [Fees](trading-fees.md). Hest may change fees with notice on the official channels. Fees on Order Book Markets consist of Hyperliquid's own fees plus Hest's builder fee.

6.2 You are responsible for network (gas) fees on Robinhood Chain and any bridge fees.

6.3 Fees are collected in USDC and are non-refundable once an order is executed.

## 7. Taxes

You are solely responsible for determining and paying any taxes that apply to your use of the Services, including taxes on trading gains, vault income and fee income. Hest does not provide tax reporting or withhold tax.

## 8. Super Intelligence

8.1 SI Scores, Risk Shield verdicts, Copilot answers, project notes and any other Super Intelligence output are informational outputs of automated analysis. They are generated from on-chain data, public social data, market data and statistical models that can be incomplete, delayed, manipulated or wrong.

8.2 Super Intelligence output is not investment advice, is not a recommendation to trade, and does not predict prices. A high SI Score does not mean a market is safe; a Risk Shield "ok" verdict does not mean a position cannot be liquidated.

8.3 Copilot is a language-model assistant. It can make mistakes, misread numbers and produce confident but incorrect statements. Verify anything that matters before acting on it.

8.4 Hest may change the scoring methodology at any time and does not guarantee any level of accuracy, availability or latency for Super Intelligence.

## 9. Prohibited Conduct

You agree not to, and not to help anyone else to:

* violate any law, regulation or sanctions program, or use the Services from a Restricted Jurisdiction;
* engage in market manipulation of any kind, including wash trading, spoofing, layering, oracle manipulation, pump-and-dump schemes or coordinated trading against a Vault;
* exploit a bug, vulnerability or unintended behaviour of the Interface, the Hest Pools contracts, Hyperliquid or any oracle, or fail to report one you discover;
* attack, overload, scrape at scale, reverse engineer or interfere with the Services or their infrastructure;
* use the Services to launder money, finance terrorism or move the proceeds of crime;
* create markets for tokens you know to be fraudulent, or act as Market Owner while trading against your own market's Vault with information not available to other users;
* impersonate Hest, its team or another user, or misrepresent your affiliation with Hest;
* circumvent any limit, restriction or suspension that Hest has applied.

Hest may restrict, suspend or terminate access to the Interface for any address or person it reasonably believes has breached this section, and may report unlawful conduct to the relevant authorities.

## 10. Intellectual Property

10.1 The Interface, the Hest name and logo, the Hest mascot, Super Intelligence and all related content are owned by Hest or its licensors and are protected by intellectual-property laws. Open-source components are licensed under their own licenses, as published in the relevant repositories.

10.2 Hest grants you a limited, revocable, non-exclusive, non-transferable licence to use the Interface for its intended purpose in accordance with these Terms. You may not copy, modify, distribute, sell or lease any part of the Services except as permitted by an open-source licence.

10.3 Third-party names and logos, including Hyperliquid and Robinhood, belong to their owners. Their appearance on the Interface describes integration and does not imply endorsement or partnership.

## 11. Third-Party Services

The Services depend on third parties that Hest does not control, including Hyperliquid, Robinhood Chain, wallet providers, oracles, DEX price sources, data providers, hosting and infrastructure providers. Your use of those services is governed by their own terms. Hest is not responsible for their availability, accuracy, security or conduct, and does not endorse any token that can be traded through the Services.

## 12. Beta Status and Availability

12.1 The Services are in Beta. Features, parameters, fees, markets and documentation can change, and the Services may be modified, suspended or discontinued, in whole or in part, at any time with notice on the official channels where practical.

12.2 Hest does not guarantee that the Interface will be available, uninterrupted, secure or free of errors. Outages may prevent you from opening, managing or closing positions, including during liquidation. Keep enough margin to withstand periods when the Interface is unavailable. Order Book Market positions can also be managed directly on Hyperliquid.

## 13. Disclaimer of Warranties

THE SERVICES ARE PROVIDED "AS IS" AND "AS AVAILABLE" WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, TITLE AND NON-INFRINGEMENT. HEST DOES NOT WARRANT THAT THE SERVICES, THE SMART CONTRACTS, THE ORACLES, HYPERLIQUID OR ANY THIRD-PARTY SERVICE WILL BE ACCURATE, RELIABLE, SECURE, UNINTERRUPTED OR FREE OF ERRORS, OR THAT ANY SUPER INTELLIGENCE OUTPUT WILL BE CORRECT. YOU USE THE SERVICES AT YOUR OWN RISK. SOME JURISDICTIONS DO NOT ALLOW THE EXCLUSION OF IMPLIED WARRANTIES, SO SOME OF THESE EXCLUSIONS MAY NOT APPLY TO YOU.

## 14. Assumption of Risk

You acknowledge that you have read and understood the [Risk Disclosure](legal-risk-disclosure.md), that trading leveraged perpetual contracts and depositing into vaults carries a high risk of total loss, that digital-asset markets are volatile and lightly regulated, that smart contracts can contain bugs, that oracles can fail, and that the regulatory treatment of digital assets is uncertain and may change. You assume all of these risks.

## 15. Limitation of Liability

TO THE MAXIMUM EXTENT PERMITTED BY LAW, HEST AND ITS AFFILIATES, CONTRIBUTORS, OFFICERS, EMPLOYEES AND AGENTS WILL NOT BE LIABLE FOR ANY INDIRECT, INCIDENTAL, SPECIAL, CONSEQUENTIAL, EXEMPLARY OR PUNITIVE DAMAGES, OR FOR ANY LOSS OF PROFITS, REVENUE, DATA, DIGITAL ASSETS OR GOODWILL, ARISING OUT OF OR RELATED TO THE SERVICES, HOWEVER CAUSED AND UNDER ANY THEORY OF LIABILITY, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGES. THIS INCLUDES LOSSES FROM TRADING, LIQUIDATION, VAULT PERFORMANCE, ORACLE OR TWAP PRICING, SMART-CONTRACT BUGS OR EXPLOITS, HYPERLIQUID OR NETWORK FAILURES, WALLET COMPROMISE, PHISHING, OR RELIANCE ON SUPER INTELLIGENCE OUTPUT. IN NO EVENT WILL HEST'S TOTAL LIABILITY TO YOU FOR ALL CLAIMS EXCEED THE GREATER OF (A) THE FEES YOU PAID TO HEST IN THE TWELVE MONTHS BEFORE THE EVENT GIVING RISE TO THE CLAIM AND (B) ONE HUNDRED US DOLLARS (USD 100).

## 16. Indemnification

You agree to defend, indemnify and hold harmless Hest and its affiliates, contributors, officers, employees and agents from and against any claim, demand, loss, liability, damage, cost or expense (including reasonable legal fees) arising out of or related to your use of the Services, your breach of these Terms, your violation of any law or the rights of a third party, or any market you create or vault you fund.

## 17. Suspension and Termination

Hest may suspend or terminate your access to the Interface at any time, with or without notice, if it reasonably believes you have breached these Terms, if required by law, or to protect the Services or other users. Because the Services are non-custodial, termination of Interface access does not affect assets in your wallet, positions on Hyperliquid (which remain manageable on Hyperliquid) or vault shares you hold on-chain. Sections 7, 8, 10 and 13 to 20 survive termination.

## 18. Governing Law and Dispute Resolution

18.1 These Terms are governed by the laws of [governing jurisdiction], without regard to its conflict-of-laws rules.

18.2 Any dispute arising out of or relating to these Terms or the Services will be resolved by binding arbitration administered by [arbitral institution] under its rules, seated in [seat], in the English language, before a single arbitrator. You and Hest waive any right to a jury trial and to participate in a class action, to the extent permitted by law.

18.3 Before starting arbitration, a party must send a written description of the dispute to the other party and allow 30 days for good-faith resolution. For Hest, notice is given by opening a ticket marked **Legal** on [discord.gg/hest](https://discord.gg/hest) until an email address for legal notices is published.

## 19. Changes to These Terms

Hest may update these Terms from time to time. The "Last updated" date at the top of this page shows the current version. Material changes will be announced on the official channels (hest.si, @HestSI on X, discord.gg/hest) at least 7 days before they take effect where practical. Continued use of the Services after a change takes effect means you accept the updated Terms.

## 20. General

20.1 These Terms, together with the [Privacy Policy](legal-privacy.md) and the [Risk Disclosure](legal-risk-disclosure.md), are the entire agreement between you and Hest regarding the Services.

20.2 If any provision of these Terms is held unenforceable, the remaining provisions remain in force and the unenforceable provision is modified to the minimum extent necessary.

20.3 Hest's failure to enforce a provision is not a waiver of its right to do so later.

20.4 You may not assign these Terms. Hest may assign them to an affiliate or a successor.

20.5 Hest is not liable for any failure or delay caused by events beyond its reasonable control, including network or protocol failures, acts of government, war, pandemic or natural disaster.

20.6 Notices to you may be given through the Interface or the official channels. Notices to Hest are given through a ticket marked **Legal** on [discord.gg/hest](https://discord.gg/hest).

## 21. Contact

All requests (support, legal, security) go through tickets on [discord.gg/hest](https://discord.gg/hest). Mark the ticket with the topic and the team routes it.
