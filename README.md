# E-Commerce Retail Analytics Project

End-to-end data analytics project on the UCI Online Retail Dataset, covering data cleaning, customer segmentation, SQL analysis, exploratory data analysis, and an interactive Power BI dashboard.

## Overview

This project analyzes 541,909 transaction records from a UK-based online retailer (Dec 2010 - Dec 2011) to uncover sales trends, customer behavior patterns, and business insights. The full pipeline spans Excel, Python, SQL, and Power BI.

## Dataset

UCI Online Retail Dataset — approximately 540K transaction rows across 8 columns (InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, Country).

Due to file size, the raw and full cleaned dataset are not included in this repo. The complete cleaning process is documented in `notebook/01_data_loading_exploration.ipynb`. A sample output, `rfm_segments.csv`, is included to show the customer segmentation results.

## Tools Used

- **Excel** — initial data exploration, pivot tables, charts
- **Python** (pandas, NumPy, matplotlib, seaborn) — data cleaning, feature engineering, RFM analysis, visualizations
- **SQL** (SQLite) — business analysis queries, window functions, CTEs
- **Power BI** — interactive dashboard

## Project Structure

```
├── notebook/
│   ├── 01_data_loading_exploration.ipynb   # Data loading, cleaning, RFM analysis
│   └── 03_eda_visualizations.ipynb         # Charts and exploratory analysis
├── retail_analytics.sqbpro                 # SQLite database project (DB Browser for SQLite)
├── visuals/
│   ├── 01_monthly_revenue_trend.png
│   ├── 02_top_products.png
│   ├── 03_sales_heatmap.png
│   ├── 04_rfm_segments.png
│   ├── 05_revenue_by_country.png
│   ├── 06_cohort_analysis.png
│   ├── 07_revenue_distribution.png
│   └── 08_monthly_growth.png
├── dashboard/
│   └── RetailDashboard.pbix                # Interactive Power BI dashboard
└── data/
    └── rfm_segments.csv                    # Customer RFM scores and segments
```

## Data Cleaning Summary

- Started with 541,909 raw rows
- Removed 10,624 cancelled orders (negative quantity)
- Removed 1,181 rows with zero/negative unit price
- Removed 132,220 rows with missing CustomerID
- Removed 1,411 non-product entries (fees, manual adjustments, etc.)
- Final clean dataset: 396,473 rows, 18 columns (10 new engineered features)

## Key Findings

- **United Kingdom generates 96% of total revenue** — clear B2B market concentration
- **Repeat customer rate exceeds 65%**, indicating strong customer retention
- **Peak ordering hour is 12 PM**, with Wednesday/Thursday as the busiest days
- **84% of orders occur on weekdays**, confirming a business-to-business buying pattern
- **RFM segmentation** identified 5 customer groups: Recent Active, Average Customers, Lost Customers, High Value, and Frequent Buyers
- **Cohort analysis** showed the December 2010 cohort retained 50% of customers after 11 months

## SQL Highlights

The SQL analysis (open `retail_analytics.sqbpro` in DB Browser for SQLite) includes:
- Monthly revenue trends and customer frequency segmentation
- Window functions: `RANK()`, `DENSE_RANK()`, `ROW_NUMBER()`, `LAG()`
- CTEs for multi-step customer lifetime value tiering
- `PARTITION BY` to find top products per country

## Dashboard

The Power BI dashboard (`dashboard/RetailDashboard.pbix`) includes:
- KPI cards: Total Revenue, Total Orders, Total Customers, Avg Order Value, Repeat Customer Rate
- Revenue trend over time
- Top 10 products by revenue
- Sales heatmap by day and hour
- Customer segments (RFM) donut chart
- Sales by country map
- Interactive slicers for Country, Year, and Segment

## Author

Rakshitha
```

