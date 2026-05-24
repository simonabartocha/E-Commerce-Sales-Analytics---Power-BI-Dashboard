# 📊 E-Commerce Sales Analytics — Power BI Dashboard

A comprehensive business intelligence report built in Power BI,
analyzing e-commerce sales performance across multiple dimensions
including revenue trends, product portfolio, customer segmentation,
and AI-powered forecasting.

---

## 📁 Project Overview

This project delivers a multi-page interactive Power BI dashboard
designed to provide actionable insights for an e-commerce business.
The report covers sales data from **2016 to 2021** across
**8 countries** and **8 product categories**.

---

## 📌 Key Metrics

| Metric | Value |
|---|---|
| Total Revenue | $21.84M |
| Total Orders | 10K |
| Total Customers | 7K |
| Average Order Value | $2.16K |
| Units Sold | 77K |
| YoY Growth | 2.13% |

---

## 📄 Report Pages

### 1. Executive Overview
High-level summary of business performance.
- KPI cards: Total Revenue, Orders, Customers, Avg Order Value,
  Units Sold, YoY Growth %
- Revenue by Year (bar chart)
- Revenue by Country (bar chart)
- Revenue by Category (bar chart)
- Revenue by Product Name (bar chart)
- Slicers: Country, Year, Brand, Category

### 2. Sales Performance
Deep dive into revenue trends over time.
- Revenue by Year Quarter (line chart)
- Revenue by Month — multi-year comparison (line chart)
- Revenue & YoY Growth % by Year (combo chart)
- Revenue by Year with range slicer
- Slicers: Year range, Category, Country

### 3. Product Portfolio Analysis
Product and brand-level performance analysis.
- Top products by Total Revenue (bar chart)
- Top products by Units Sold (bar chart)
- Revenue by Category (bar chart)
- Revenue by Brand (bar chart)
- Top 50 Products by Revenue — scatter plot
  (colored by Category, X axis: Units Sold)
- Slicers: Year range, Category, Brand, Country

### 4. Customer & Market Intelligence
Customer segmentation and geographic analysis.
- Revenue by Geography (map visual)
- Customer Segments by Revenue — RFM Analysis (treemap)
  - Segments: Champions, Loyal, Potential Loyalist,
    At Risk, Lost
- Customer Value vs Purchase Frequency (scatter plot)
- Top Countries by Revenue (bar chart)
- Revenue Split by Gender (donut chart)
- Slicers: Year range, Country, Customer Segment

### 5. AI Forecasting & Anomaly Detection
Forward-looking analysis using Power BI AI visuals.
- Revenue Trend with Anomaly Detection & Forecast
  (line chart with built-in AI)
- Actual vs Projected Revenue by Year (combo chart)
- What Influences Total Revenue? (Key Influencers AI visual)
- AI-Generated Insights (Smart Narrative)
- Slicers: Year range, Category, Growth Assumption

---

## 🗂️ Data Model

The report is built on the following tables:

| Table | Description |
|---|---|
| Sales | Core transaction data |
| Customers | Customer demographics & RFM scores |
| Products | Product catalog with categories & brands |
| Calendar | Date dimension table |
| Stores | Store location data |
| Exchange_Rates | Multi-currency support |
| Growth Assumption | Parameter table for forecasting |

---

## 🧮 Key DAX Measures

```dax
-- Year over Year Growth
YoY Growth % =
DIVIDE([Total Revenue] - [Revenue LY], [Revenue LY])

-- Revenue Last Year
Revenue LY =
CALCULATE([Total Revenue], SAMEPERIODLASTYEAR('Calendar'[Date]))

-- Revenue Year to Date
Revenue YTD =
TOTALYTD([Total Revenue], 'Calendar'[Date])

-- 3 Month Rolling Average
Revenue 3M Avg =
AVERAGEX(
    DATESINPERIOD('Calendar'[Date], LASTDATE('Calendar'[Date]), -3, MONTH),
    [Total Revenue]
)

-- Projected Revenue
Projected Revenue =
[Total Revenue] * (1 + SELECTEDVALUE('Growth Assumption'[Growth Assumption], 0.05))
```

---

## 🤖 AI Features Used

- **Anomaly Detection** — automatically flags unusual spikes
  and drops in revenue
- **Forecasting** — 12-month revenue forecast with 95%
  confidence interval
- **Key Influencers** — identifies what factors increase
  or decrease Total Revenue
- **Smart Narrative** — auto-generated natural language
  summary of key insights
- **Decomposition Tree** — interactive drill-down revenue
  breakdown

---

## 🌍 Data Scope

**Countries:** United States, United Kingdom, Germany,
Canada, Australia, Italy, Netherlands, France

**Categories:** Computers, Home Appliances,
Cameras & Camcorders, Cell Phones, TV and Video,
Music/Movies, Audio, Games and Toys

**Brands:** Adventure Works, Contoso, Wide World Importers,
Fabrikam, The Phone Company, Proseware, Litware,
Southridge Video, A. Datum, Northwind Traders, Tailspin Toys

**Time Period:** 2016 — 2021

---

## 🛠️ Tools & Technologies

- **Power BI Desktop**
- **DAX** (Data Analysis Expressions)
- **Power Query (M language)**
- **Microsoft Azure Maps** (geography visual)

---

## 🚀 How to Open

1. Download the `.pbix` file from this repository
2. Open with **Power BI Desktop**
   (free download at microsoft.com/power-bi)
3. Use slicers to filter by Year, Country, Category or Brand
4. Navigate between pages using tabs at the bottom

---

## 👩💼 Author

Built as a portfolio project to demonstrate skills in:
- Business Intelligence & Data Visualization
- DAX calculations & Data Modeling
- AI-powered analytics in Power BI
- E-commerce KPI analysis & RFM customer segmentation
