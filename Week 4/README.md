# Week 4 – Power BI : Time Series Visualization & Financial Dashboard

**Submitted by:** Preethi Pal D
**Roll No:** E25DA046
**Department:** BSc Data Science and AI

## 📊 Dataset

`SHOP_2015-05-21_2025-03-16` – daily Shopify stock data (continued from Week 3), with a `Dim_Date` table already set up.

## 🎯 Objectives

- Calculate the 20-day and 50-day Simple Moving Average (SMA) of trading volume using DAX
- Create a Moving Average Crossover Signal to show a bullish or bearish trend (Golden Cross / Death Cross)
- Build an interactive price trend line chart with Close Price, 20 SMA and 50 SMA, with a zoom slider
- Build a trading volume chart with a conditional colour measure to highlight volume spikes
- Add a date range slicer, a relative date slicer, and a parameter to switch between price metrics
- Create a custom tooltip page that shows full trade details on hover

## 🛠️ What I Did

1. **Volume SMA measures** – used `DATESINPERIOD` to calculate 20-day and 50-day average trading volume
2. **MA Crossover Signal** – an `IF` measure comparing 20 SMA vs 50 SMA to flag Bullish/Bearish trend
3. **Price trend line chart** – Close Price, 20 SMA, 50 SMA on a continuous date axis, with a zoom slider
4. **Volume chart with conditional colour** – a `Volume Color` measure that turns bars red on volume spikes (> 1.5× the 20 SMA)
5. **Slicers & parameter** – date range slicer, relative date slicer (1M/3M/6M/YTD/1Y), and a field parameter to switch between Close/High/Low/Open Price
6. **Custom tooltip page** – a `Stock_Tooltip` page set as a tooltip, showing Open, High, Low, Close, Volume and Daily Return % on hover

## 🧮 Key DAX Measures

```dax
Volume 20 SMA =
VAR CurrentDate = MAX(Dim_Date[Date])
VAR PeriodDays = 20
VAR DateInPeriod = DATESINPERIOD(Dim_Date[Date], CurrentDate, -PeriodDays, DAY)
RETURN CALCULATE(AVERAGE('SHOP_2015-05-21_2025-03-16'[volume]), DateInPeriod)

MA Crossover Signal =
IF(ISBLANK([20 SMA]) || ISBLANK([50 SMA]), BLANK(),
  IF([20 SMA] > [50 SMA], "Bullish (20 > 50)", "Bearish (20 < 50)"))

Volume Color = IF([Total Volume] > [20 SMA] * 1.5, "#FF4D4D", "#26A69A")
```

## 🛠️ Tools Used

- Power BI Desktop
- Power Query
- DAX (Data Analysis Expressions)

## 📄 Report

Full step-by-step report with screenshots: `Week4_PowerBI_Report.docx`
