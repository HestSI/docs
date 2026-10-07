# Order Types

The order panel offers **Market** and **Limit** directly, and four more under the **Pro** menu.

| Type | What it does | Use it when |
| --- | --- | --- |
| **Market** | Fills immediately at the best available prices. The panel shows estimated slippage from the live book. | You want in or out now. |
| **Limit** | Rests in the book at your price or better. Click a price in the order book to fill it in; **Mid** sets the midpoint. | You want a specific price and can wait. |
| **Stop market** | Sends a market order when the mark price crosses your **trigger price**. | Protecting a position or entering on a breakout. |
| **Stop limit** | Sends a limit order at your limit price when the trigger is crossed. | Same as above, but you refuse to fill through a gap. |
| **TWAP** | Splits the order into equal slices over a **running time** (5 to 1440 minutes), optionally randomised. Slices show up in Trade history as they fill. | Large size on a thin market without moving it. |
| **Scale** | Places several limit orders between a **start** and **end** price, with an optional size skew toward one end. | Laddering into a range. |

## Options on every order

* **Reduce only** – the order can only shrink an existing position, never open or flip one.
* **Take profit / Stop loss** – attach TP and SL prices to the position when it opens. Enter a price or a percentage gain/loss on margin; the other field fills in.
* **Cross / Isolated** – cross margin shares your whole balance across positions; isolated locks a fixed margin to this position.

## Size

Enter size in **USDC** or in the coin (toggle next to the Size field), or drag the slider for a percentage of your available balance at the chosen leverage. The panel shows order value, margin required, liquidation price, estimated slippage and fees before you confirm.

## On Hest Pool markets

Pool markets have no order book, so there is no slippage: every order fills at the current TWAP. Market, limit, stop and TP/SL all work; TWAP and scale are available but rarely needed.
