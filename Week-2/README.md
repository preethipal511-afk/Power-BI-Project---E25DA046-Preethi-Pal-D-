# Superstore Sales — Week 2: Data Modeling, DAX & Sales Dashboard

A Power BI project that takes the cleaned Superstore Sales dataset (from Week 1) and turns it into an interactive sales dashboard using DAX measures, KPI cards, and slicers.

## 📊 Overview

Management wants an interactive dashboard to monitor sales, profit, orders, and regional performance — without digging through raw spreadsheets. This week covers building the data model, writing the core DAX measures, and putting together the dashboard.

## 🛠️ Tools Used

- Power BI Desktop
- DAX (Data Analysis Expressions)

## ✅ What Was Done

- Built a dedicated `_Measures` table to hold all DAX calculations.
- Wrote core DAX measures: Total Sales, Total Profit, Total Orders, Total Quantity, Average Sales, and Profit Margin %.
- Built a top-line KPI summary bar (Total Profit, Total Sales, Total Orders, Profit Margin).
- Added a Total Sales by Sub-Category bar chart and a Total Sales by Year line chart.
- Built a decomposition tree to explore Total Profit by Category and Region.
- Added Region and Order Date slicers for interactive filtering.
- Delivered a fully interactive Superstore Sales Dashboard with cross-filtering and drill-down.

## 📈 Key Measures

```DAX
Total Sales = SUM(samplesuperstore[Sales])
Total Profit = SUM(samplesuperstore[Profit])
Total Orders = DISTINCTCOUNT(samplesuperstore[Order ID])
Total Quantity = SUM(samplesuperstore[Quantity])
Average Sales = AVERAGE(samplesuperstore[Sales])
Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)
```

## 👤 Author

**Preethi Pal D**
Roll No: E25DA046
BSc Data Science and AI
