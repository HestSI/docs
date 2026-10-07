# Order Types

On Order Book markets the order panel offers **Market** and **Limit** directly, and four more under the **Pro** menu.

| Type | What it does | Use it when |
| --- | --- | --- |
| **Market** | Fills immediately at the best available prices. The panel shows estimated slippage from the live book. | You want in or out now. |
| **Limit** | Rests in the book at your price or better. Click a price in the order book to fill it in; **Mid** sets the midpoint. | You want a specific price and can wait. |
| **Stop Market** | Sends a market order when the price crosses your **trigger price**. | Protecting a position or entering on a breakout. |
| **Stop Limit** | Sends a limit order at your limit price when the trigger is crossed. | Same as above, but you refuse to fill through a gap. |
| **Scale** | Places several limit orders between a **start** and an **end** price. | Laddering into a range. |
| **TWAP** | Splits the order into slices over a **running time**. Slices appear in the **TWAP** tab and in Trade History as they fill. | Large size on a thin market without moving it. |

The minimum order value is **$10**, a Hyperliquid rule.

## Options on Every Order

* **Reduce Only**: the order can only shrink an existing position, never open or flip one.
* **Take Profit / Stop Loss**: attach TP and SL prices to the position when it opens. Enter a price or a percentage gain or loss; the other field fills in.
* **Cross / Isolated**: cross margin shares your whole Order Book balance across positions; isolated locks a fixed margin to this position.

## Size

Enter size in **USDC** or in the coin (toggle next to the Size field), or drag the slider for a share of your available balance at the chosen leverage. Before you confirm, the panel shows the liquidation price, order value, margin required, estimated slippage, fees and the route.

## Hest Pools

Hest Pools markets have no order book: every open and close fills at the worse of the token's spot price and its 15-minute TWAP. See [How Hest Pools Work](how-hest-pools-work.md).
