---
description: >-
  Every order type on Hest, how it is built and executed on Hyperliquid, and
  what Hest Pools markets accept.
---

# Order Types

On Order Book markets the order panel offers **Market** and **Limit** directly, and four more under the **Pro** menu: **Stop Market**, **Stop Limit**, **TWAP** and **Scale**. Every order is signed by your Trading Wallet and executed by Hyperliquid. Hest Pools markets accept market orders only, with optional take profit and stop loss.

## Order Book Markets

| Type            | How Hest builds it                                                                                                                                                                                     | Use it when                                           |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------- |
| **Market**      | An immediate-or-cancel limit order priced 8% beyond the mark (above it for a buy, below it for a sell). It fills at the best prices in the book up to that limit; anything left unfilled is cancelled. | You want in or out now.                               |
| **Limit**       | A good-till-cancelled limit order at your price. It rests in the book until filled or cancelled. Click a price in the order book to fill it in; **Mid** sets the midpoint of the spread.               | You want a specific price and can wait.               |
| **Stop Market** | A trigger order. When Hyperliquid's price crosses your **trigger price**, it executes as a market order with the same 8% price limit.                                                                  | Protecting a position or entering on a breakout.      |
| **Stop Limit**  | A trigger order that places a limit order at your **limit price** when the trigger is crossed.                                                                                                         | Same as above, when you refuse to fill through a gap. |
| **Scale**       | 2 to 20 limit orders spread evenly from a **start price** to an **end price**. **Size Skew** sets how size is distributed.                                                                             | Laddering into a range.                               |
| **TWAP**        | Hyperliquid's native TWAP order: the total size is executed in slices every 30 seconds over the **running time** you choose, from 5 to 1,440 minutes. **Randomize** varies the slices.                 | Large size on a thin market without moving it.        |

The minimum order value is **$10**, a Hyperliquid rule. Reduce-only orders are exempt.

### Scale Orders in Detail

With `n` orders between start price `a` and end price `z`, order `i` (counting from 0) is placed at:

```
price(i)  = a + (z − a) × i / (n − 1)
weight(i) = skew ^ (i / (n − 1))
size(i)   = total size × weight(i) / sum of all weights
```

A skew of 1 gives every order the same size. A skew of 2 makes the last order twice the size of the first, with the ones in between growing smoothly. Each order must be worth at least $10.

### TWAP Orders in Detail

A TWAP runs on Hyperliquid, not in your browser: closing the tab does not stop it. Each slice fills as a market order. The **TWAP** tab under the chart shows the TWAPs started from this browser, with total size, executed size, running time and progress, and **Terminate** cancels the remainder. Every slice also appears in Trade History.

## Options on Every Order

* **Reduce Only:** the order can only shrink an existing position, never open or flip one.
* **Take Profit / Stop Loss:** attach TP and SL to the position as it opens. Enter a price or a percentage gain or loss; the other field fills in. Hest sends them in the same signed batch as the entry order, as reduce-only trigger orders for the same size, each executing as a market order with the 8% price limit when triggered.
* **Cross / Isolated:** cross margin shares your whole Order Book balance across cross positions; isolated locks a fixed margin to this position. The mode and the leverage are set on Hyperliquid for that market just before the order is sent.

## Size

Enter size in **USDC** or in the coin (toggle next to the Size field), or drag the slider for a share of your available balance at the chosen leverage. Before you confirm, the panel shows:

* **Liquidation Price**, estimated from the market's maintenance margin.
* **Order Value** and **Margin Required**.
* **Slippage**, estimated from the live book, and the maximum (8%) for market orders.
* **Fees**, Hyperliquid's plus Hest's.
* **Route**: Order Book (Hyperliquid) or Hest Pool.

A confirmation dialog repeats the order and the Risk Shield verdict before anything is signed: **Place Market Order**, **Place Order**, **Place Orders** (scale) or **Start TWAP**.

## Hest Pools Markets

Hest Pools markets have no order book. They accept:

| Type                        | How it works                                                                                                                                                             |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Market**                  | Opens immediately at the worse, for you, of the pool's spot price and its 15-minute TWAP. See [Hest Pools Pricing](../markets/hest-pools-pricing.md).                    |
| **Take Profit / Stop Loss** | Set in the order panel when you open. The Hest Pools engine checks them every minute against the position's mark (the price it would close at) and closes at that price. |

Limit, stop, scale and TWAP orders are not available on Hest Pools markets. Because the engine checks once a minute, take profit and stop loss can execute beyond their trigger price in a fast market. See [How Hest Pools Work](../markets/how-hest-pools-work.md).
