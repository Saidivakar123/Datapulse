# DataPulse — Sales Performance Dashboard

A Power BI dashboard built to analyze sales performance, 
profitability, and regional trends using the Sample Superstore 
dataset. Modeled after real-world performance reporting patterns 
used in operations and analytics roles — KPI scorecards, time 
trend analysis, and a stack-rank table with conditional formatting 
to surface underperforming regions instantly.

![Dashboard Preview](dashboard-preview.png)

## What This Project Demonstrates

- **End-to-end build** — raw Excel data to interactive dashboard 
from scratch, no pre-built templates
- **Data cleaning** using Power Query (null checks, type 
validation, column pruning)
- **DAX measures** including aggregations, safe division, and 
time intelligence (DATEADD, CALCULATE)
- **Interactive date slicer** — filters all visuals simultaneously 
by date range
- **KPI scorecards** for Total Sales, Total Profit, Profit 
Margin %, and Total Orders
- **Trend analysis** — year-over-year sales growth line chart
- **Stack-rank scorecard** — region-level performance table with 
red/yellow/green conditional formatting, directly modeled after 
weekly performance review patterns used in accountability reporting

## Dashboard Visuals

| Visual | Purpose |
|---|---|
| KPI Cards | Instant snapshot of key metrics |
| Date Slicer | Filter entire dashboard by date range |
| Sales Trend Line | Year-over-year growth story |
| Category Bar Chart | Sales distribution across product lines |
| Stack-Rank Table | Regional performance with conditional formatting |

## DAX Measures Written

```dax
Total Sales = SUM(Orders[Sales])

Total Profit = SUM(Orders[Profit])

Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)

Total Orders = DISTINCTCOUNT(Orders[Order ID])

Sales Last Month = 
    CALCULATE(
        [Total Sales], 
        DATEADD(Orders[Order Date], -1, MONTH)
    )

MoM Growth % = 
    DIVIDE(
        [Total Sales] - [Sales Last Month], 
        [Sales Last Month], 
        0
    )
```

## Key Findings

- **West region** leads in both revenue ($725K) and profitability 
(14.9% margin)
- **Central region** underperforms significantly at 7.9% margin 
— less than half of West's margin despite $501K in sales
- **Technology** is the highest revenue category ($836K), 
followed by Furniture and Office Supplies
- Overall sales grew consistently from 2014 to 2017, with the 
strongest growth between 2016 and 2017

## Tools Used

| Tool | Purpose |
|---|---|
| Power BI Desktop | Dashboard development |
| Power Query | Data cleaning & transformation |
| DAX | Measures & time intelligence |
| Excel / CSV | Source data |

## Dataset

Sample Superstore — 9,994 rows of retail transaction data 
covering Category, Region, Sales, Profit, Quantity, and Order 
Date (2014–2017). Widely used benchmark dataset for analytics 
practice and portfolio projects.

## Author

**Ankem Sai Divakar**  
Full-Stack Software Engineer & Data Analyst  
[LinkedIn](https://linkedin.com/in/ankem-sai-divakar) | 
[GitHub](https://github.com/Saidivakar123)
