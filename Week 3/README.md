# Week 3 Assignment: Shopify Stock Analysis

## 1. Dataset Overview
This report analyzes Shopify's historical daily stock data (`SHOP_2015-05-21_2025-03-16`):
* **date:** Trading date
* **open / close:** Market opening and closing stock prices
* **high / low:** Highest and lowest prices during the day
* **adj_close:** Adjusted closing price for splits/dividends
* **volume:** Total number of shares traded

---

## 2. Data Architecture
* **Fact Table:** `SHOP_2015-05-21_2025-03-16` (contains price & volume transactions)
* **Dimension Table:** `Dim_Date` (supports Time Intelligence)
* **Relationship:** 1-to-many (`1:*`) single-direction join from `Dim_Date[Date]` to `SHOP[date]`
* **Measure Table:** Dedicated central table hosting all DAX calculations

---

## 3. DAX Measures
1. **Close Price:** `AVERAGE('SHOP_2015-05-21_2025-03-16'[close])`
2. **Open Price:** `AVERAGE('SHOP_2015-05-21_2025-03-16'[open])`
3. **Low Price:** `MIN('SHOP_2015-05-21_2025-03-16'[low])`
4. **High Price:** `MAX('SHOP_2015-05-21_2025-03-16'[high])`
5. **Previous Close:** `CALCULATE([Close Price], DATEADD('Dim_Date'[Date], -1, DAY))`
6. **Trading Volume:** `SUM('SHOP_2015-05-21_2025-03-16'[volume])`
7. **Daily Return %:** `DIVIDE([Close Price] - [Previous Close], [Previous Close], 0)`
8. **Close Price PY:** `CALCULATE([Close Price], SAMEPERIODLASTYEAR('Dim_Date'[Date]))`
9. **Close Price YoY %:** `DIVIDE([Close Price] - [Close Price PY], [Close Price PY], 0)`
10. **Trading Volume YTD:** `TOTALYTD([Trading Volume], 'Dim_Date'[Date])`

---

## 4. Visual Dashboard Summary
* **KPI Cards:** Show key metrics (`Close Price`, `Trading Volume`, `Daily Return %`, `Close Price YoY %`).
* **Line Chart:** Displays price movements over time (`Close`, `Open`, `High`, `Low`).
* **Column Chart:** Tracks annual `Trading Volume YTD`.
* **Slicer:** Filters dashboard visual data by custom date ranges.

---

## 5. Summary Findings
The Power BI report shows sustained stock growth peaking around 2021 before market stabilization into 2024–2025, with trading volume spiking during major price movements.
