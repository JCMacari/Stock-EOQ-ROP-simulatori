# Stock Intelligence

An interactive inventory management calculator and simulator built as a single HTML file — no dependencies, no server required.

## Features

- **EOQ Calculator** — Economic Order Quantity with cost trade-off visualization
- **Reorder Point (ROP)** — Accounts for mean demand and lead time
- **Safety Stock** — Full dual-variability formula:  
  `SS = Z · √(L·σd² + d²·σL²)`  
  supporting demand σ entered as daily / weekly / monthly / annual
- **Stockout Penalty** — Expected units short per cycle via the normal loss function; derives the economically optimal service level from the critical ratio
- **Live Simulation** — Stochastic demand and lead time variability, with warehouse visualization
- **Sensitivity & Cost Curve** — Interactive charts showing EOQ and cost response to demand shifts
- **Storage Capacity Constraint** — Caps order quantity and warns when EOQ exceeds capacity
- **Print / Export** — Full summary printable as PDF

## Inputs

| Parameter | Description |
|---|---|
| Annual Demand | Mean yearly demand (units) |
| Demand σ | Std dev in daily / weekly / monthly / annual units |
| Lead Time | Mean supplier lead time (days) |
| Lead Time σ | Variability in delivery time (days) |
| Order Cost | Fixed cost per order placed |
| Unit Cost | Cost per unit purchased |
| Holding Rate | Annual inventory holding rate (%) |
| Service Level | Target fill rate (85–99%) |
| Stockout Cost | Penalty per unit short ($) |
| Storage Capacity | Maximum warehouse capacity (units) |
| Starting Stock | Initial inventory level for simulation |

## Usage

Open `Stock Intelligence.html` in any modern browser. No build step, no internet connection required after initial font load.

## Formulas

| Metric | Formula |
|---|---|
| EOQ | `√(2DS / H)` |
| Safety Stock | `Z · √(L·σd² + d²·σL²)` |
| ROP | `d̄·L + SS` |
| E[units short/cycle] | `σ_eff · L(z)` where `L(z) = φ(z) − z·(1−Φ(z))` |
| Optimal Service Level | `1 − H·Q / (p·D)` |
