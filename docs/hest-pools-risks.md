---
description: What can go wrong on a Hest Pools market, for traders and for market openers.
---

# Hest Pools Risks

Hest Pools markets trade the youngest and most volatile tokens on Hest. Read this before you trade one or apply to open one.

## For Traders

### Memecoins Move Violently

A Robinhood Chain memecoin can halve or double in an hour, and many go to zero. At 5x, a 20% move against you is the whole margin, and in practice liquidation comes before that because of maintenance margin. Risk Shield shows how your liquidation distance compares with the worst hour of the past week; use it.

### The Price Comes From a DEX Pool

The mark comes from the token's Uniswap pools on Robinhood Chain. Taking the worse of spot and the 15-minute TWAP protects the market from short manipulation, but it also means:

* your entry and exit are worse than either price alone, so a round trip costs more than the 0.30% + 0.30% fee;
* after a fast move the TWAP lags, and the price you get can be far from what you see on a chart elsewhere;
* if the pool is drained, abandoned or rugged, the price can collapse faster than positions can be closed.

### Profits Are Paid After Review

Profits are credited to your Earnings balance, locked for 7 days, then reviewed and paid by Hest. Until they are paid they are not in your wallet. Profits that come from manipulation, linked accounts or a broken price can be withheld. Losses, by contrast, are settled immediately.

### Hest Is the Counterparty

On Hest Pools you trade against Hest, not against other traders. Payment of profits depends on Hest. Markets can pause automatically on abnormal moves, and Hest can change market parameters or stop a market.

### Collateral Is WETH

Your margin is WETH. Its dollar value moves with the price of ETH, independently of the memecoin you trade. You also need a little ETH for network fees on Robinhood Chain; without it, transactions from your Trading Wallet cannot be sent.

## For Market Openers

### The Seed Is First-Loss

When traders on your market win, the loss comes out of your seed first. A strong one-way move on a hyped token can take a large part of the seed, or all of it. The 15% fee share and the 30% profit share are paid for carrying that risk; they do not remove it.

### Locked and Marked to Market

The seed is locked for 7 days. When you withdraw it, its value includes the unrealised profit and loss of open positions, so withdrawing while traders are winning locks in their gains against you. Withdrawing ends your shares in the market.

### One Token, No Diversification

A seed backs one market on one token. Nothing inside a market spreads the risk.

{% hint style="danger" %}
Only trade or seed with funds you can afford to lose entirely.
{% endhint %}
