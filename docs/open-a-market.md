---
description: Apply to list a Robinhood Chain token on Hest Pools. The on-chain checks, how capacity and the seed are calculated, the review, and what the opener earns and risks.
---

# Open a Market

Anyone can apply to open a Hest Pools market for a Robinhood Chain token that is not yet traded on Hest. The applicant pays a **$20 listing fee** and puts up a **seed** in WETH. If Hest approves the application, the market opens with the applicant as its **owner**: the owner earns a share of the market's fees and profit, and the seed absorbs the market's losses first.

## How to Apply

1. Open **Open a Market** (from the Markets or Pools page).
2. Paste the address of the token's **Uniswap v3 WETH pool** on Robinhood Chain and click **Check**. The pool address is on the token's DexScreener or GeckoTerminal page. Paste the pool address, not the token address.
3. Hest reads the pool on-chain and shows each listing rule as passed or failed, together with the market's capacity, its largest position, the seed and the listing fee in WETH and in dollars.
4. If every rule passes, click **Apply and Pay**, review the amounts and click **Pay and Apply**. The seed and the listing fee are sent in WETH from your [Trading Wallet](trading-wallet.md) to the Hest Pools collateral wallet; ETH is wrapped to WETH automatically if needed.
5. The application appears under **Your Applications** with the payment transaction link and its status: **Under Review**, **Approved**, **Rejected** or **Refunded**.

You need a signed-in account, a Trading Wallet whose key backup you confirmed, and enough ETH and WETH on the Hest Pools side to cover the payment plus network fees.

## Listing Rules Checked On-Chain

| Rule | What is checked |
| --- | --- |
| Paired with WETH on Uniswap v3 | The address is a Uniswap v3 pool on Robinhood Chain and one of its two tokens is WETH. Uniswap v4 pools are not supported. |
| Not on Hest yet | Neither the token nor the pool already has a Hest Pools market, and the token is not one Hyperliquid lists (those trade on the [Order Book](order-book-markets.md)). If it already trades on Hest, the button takes you to that market instead and there is nothing to pay. |
| No other application | Nobody else has a pending application for the token. If that application is rejected, you can apply. |
| $50k+ DEX liquidity | Twice the WETH held by the pool, at the live ETH price, is at least $50,000. |
| At least 24 hours old | The pool was created at least 24 hours ago (pool creation time from GeckoTerminal). If the age cannot be read, Hest checks it during review. |
| Calm price | Spot is within 10% of the pool's 15-minute TWAP. |
| 15-minute price history | Informational. If the pool does not yet keep the price history a TWAP needs, Hest switches it on when the market opens and trading starts about 15 minutes later. See [Hest Pools Pricing](hest-pools-pricing.md). |

Passing the automatic checks makes a token eligible to apply. It does not guarantee approval.

## Review

**Hest reviews every application by hand** before a market opens, including the token itself (for example its contract permissions and how its supply is held). Hest can reject any application.

* **Approved:** the market opens with you as its owner. Your seed is locked for 7 days from approval.
* **Rejected:** the full payment, seed and listing fee, is sent back from the collateral wallet to your Trading Wallet. The refund transaction and Hest's note appear under Your Applications.

## Capacity and Seed

**Capacity** is the amount of open interest a market can carry. It sets the market's position and open interest limits (see [How Hest Pools Work](how-hest-pools-work.md#capacity-and-caps)).

```
DEX liquidity = 2 × WETH held by the pool × ETH price
capacity      = 20% × DEX liquidity, at least $10,000 and at most $20,000
seed          = 10% × capacity, at least $1,000
listing fee   = $20
```

Capacity and seed are fixed in WETH at the ETH price of the moment you apply. Because capacity is between $10,000 and $20,000, the seed is always between $1,000 and $2,000.

| DEX liquidity | Capacity | Seed | Listing fee | You pay |
| --- | --- | --- | --- | --- |
| $50,000 | $10,000 | $1,000 | $20 | $1,020 |
| $60,000 | $12,000 | $1,200 | $20 | $1,220 |
| $100,000 | $20,000 | $2,000 | $20 | $2,020 |
| $400,000 | $20,000 (cap) | $2,000 | $20 | $2,020 |

## What the Owner Earns

* **15% of the market's trading fees.** Credited to your [Earnings](earnings.md) on every opening and every closing on your market, as 15% of the 0.30% fee charged. Each credit is locked for 7 days and then reviewed and paid.
* **30% of the market's profit as counterparty.** When traders on your market lose overall, you receive 30% of Hest's net profit on that market, credited to your Earnings. This share is what the seed's first-loss position pays for.

Example: on a market with $200,000 of trading volume in a week (each open and each close counted), fees are 0.30% × $200,000 = $600, and the owner's share is 15% = **$90**, credited trade by trade.

## The Seed Takes the First Loss

The seed backs the market:

* **When traders on your market win overall, the seed pays first.** A strong one-way move on a hyped token can take a large part of the seed, or all of it.
* **The seed is locked for 7 days** from approval.
* **After the lock, the seed's value includes the unrealised profit and loss of open positions** on the market. If traders are winning when you withdraw it, you receive less.
* **Withdrawing the seed ends your ownership** and your shares of fees and profit. The market can continue with Hest as its sole backer, or Hest can close it.

{% hint style="warning" %}
A seed can lose value, and can be lost entirely, if traders on the market win. Fee and profit shares are paid only from fees and profit actually earned. Read [Hest Pools Risks](hest-pools-risks.md) before you apply.
{% endhint %}

## FAQ

<details>

<summary>Can I apply with the token's contract address?</summary>

No. The check reads a pool, because the pool is the market's price source. Paste the address of the token's Uniswap v3 pool paired with WETH.

</details>

<details>

<summary>The token trades on Hyperliquid. Can I open a Hest Pools market for it?</summary>

No. Robinhood Chain tokens that Hyperliquid lists trade on its order book through Hest, with real two-sided liquidity. The check links you to that market instead.

</details>

<details>

<summary>What happens to my payment while the application is under review?</summary>

It sits in the Hest Pools collateral wallet. It becomes the market's seed if the application is approved, and it is returned in full to your Trading Wallet if it is rejected.

</details>

<details>

<summary>Does Hest open markets itself?</summary>

Yes. Hest also opens markets itself, without a seed, as their only backer. Those markets have no owner and pay no owner shares.

</details>
