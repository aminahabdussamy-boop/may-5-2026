# Inventory Replenishment Agent

This submission contains a working multi-SKU inventory replenishment simulation.

## Files

- `InventoryReplenishmentAgent.ipynb` — runnable notebook
- `sales.csv` — 120 days of daily demand for 3 SKUs
- `inventory.csv` — opening stock by SKU
- `params.csv` — cost, lead-time, minimum-order, and service-level inputs
- `kpi_results.csv` — baseline and agent results
- `agent_daily_log.csv` — full daily action log with rationales

## Run

Open `InventoryReplenishmentAgent.ipynb` in Jupyter or Google Colab and run all cells. If the three input CSV files are in the same folder, the notebook loads them. Otherwise, it generates reproducible demonstration data with a fixed random seed.

## Approach

The agent uses an EWMA demand forecast, forecast-error safety stock, lead-time-plus-review-period demand, and inventory position. It orders to a projected target when the position is below target and waits when the position is sufficient. It respects each SKU's minimum order quantity and logs the reason for every decision. A fixed reorder-point baseline is evaluated over the same test horizon.

The notebook reports stockout units, fill rate, holding cost, stockout cost, purchase cost, total cost, order count, and a daily rationale log. It also includes the required ethics/trust discussion, trade-off reflection, and production scaling note.
