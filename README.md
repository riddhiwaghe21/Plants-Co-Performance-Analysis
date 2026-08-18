# Plant Sales Analytics Dashboard | Power BI

## Project Overview
This project is an end-to-end Power BI sales and profitability analytics project built from a plant/product sales dataset.

Business objective:
- Analyze sales performance and profitability.
- Compare current YTD with previous-year YTD.
- Identify important countries, products and accounts.
- Diagnose contributors to performance changes.

## Tools
- Power BI Desktop
- Power Query
- DAX
- Data Modeling
- GitHub

## Dataset
### Plant_FACT — Fact Table
2,440 transaction rows containing Product_id, Sales_USD, quantity, Price_USD, COGS_USD, Date_Time and Account_id.

### Accounts — Dimension
1,744 rows containing account, country, coordinates and address attributes.

### Plant_Hierarchy — Product Dimension
1,000 rows containing product family, product group, product name, product size and product type.

## Data Quality
The supplied workbook was inspected before analysis. The fact table contains 2,440 rows, no missing values in the inspected source sheets, and no duplicate fact rows.

## Overall Dataset Metrics
| KPI | Value |
|---|---:|
| Sales | $30.08M |
| COGS | $18.11M |
| Gross Profit | $11.96M |
| Gross Profit % | 39.77% |
| Quantity | 1.24M |
| Transactions | 2,440 |

## Data Model
Logical star-schema design:

```text
                    Dim_Date
                       |
                       v
Dim_Product ------ Plant_FACT ------ Dim_Accounts
                       |
                  Sales / COGS
```

Fact table = measurable transactions.
Dimension tables = product, account and time attributes.

## Core DAX
```DAX
Total Sales = SUM(Plant_FACT[Sales_USD])

Total COGS = SUM(Plant_FACT[COGS_USD])

Gross Profit = [Total Sales] - [Total COGS]

GP % = DIVIDE([Gross Profit], [Total Sales])
```

## Time Intelligence
YTD means Year to Date. PYTD means Previous Year to Date.

The PBIX uses these measures:
- S_YTD
- S_PYTD
- YTD VS PYTD
- GP%

A typical percentage comparison is:

```DAX
YTD VS PYTD = DIVIDE([S_YTD] - [S_PYTD], [S_PYTD])
```

Always verify the exact original DAX in Power BI before quoting it as the project's exact formula.

## Dashboard Architecture
### Page 1
- KPI card using S_YTD, S_PYTD and YTD VS PYTD.
- Metric selector using Slc_Values.

### Page 2
- Metric selector.
- Country treemap using country and YTD VS PYTD.
- Monthly line/stacked-column combo using month, S_YTD, S_PYTD and Product Size.
- Hierarchical waterfall using month -> country -> product type -> product name and YTD VS PYTD.
- Scatter plot using Account, S_YTD and GP%.
- Year slicer.
- KPI card using S_YTD, YTD VS PYTD, S_PYTD and GP%.

## Actual Dataset Insights
- China is the largest sales market in the supplied data at about $9.99M.
- Outdoor is the highest-selling product type at about $10.86M.
- Large products have the highest sales among sizes at about $10.44M.
- 2024 is partial data through April 14 and should not be compared with a complete year.
- 2024 YTD sales through April 14 are about $3.57M versus about $3.71M for the comparable 2023 period, a change of about -3.67%.

## Professional Analyst Thinking
Do not stop at 'China has the highest sales.' Ask why: more customers, higher quantity, higher price, or different product mix?

Then check profitability using Gross Profit and GP%. Then check trend using YTD, PYTD and YTD vs PYTD. Finally, break the change down by country, product type, product name, account and product size.

This moves the work from reporting to diagnostic analysis.

## Analytics Levels
- Descriptive: What happened?
- Diagnostic: Why did it happen?
- Predictive: What might happen next?
- Prescriptive: What should the business do?

The current project demonstrates descriptive and diagnostic analytics.

## Advanced Topics to Learn
- CALCULATE, FILTER, ALL, ALLSELECTED, REMOVEFILTERS
- DATEADD, SAMEPERIODLASTYEAR, TOTALYTD
- SUMX, DIVIDE, SWITCH
- MTD, QTD, YTD, PYTD, YoY and rolling 12 months
- Drill-through, tooltips, bookmarks and field parameters
- Dynamic titles and conditional formatting
- Row-Level Security
- Performance optimization and incremental refresh

## Interview Answer
I developed a Power BI sales analytics dashboard using a transactional plant-sales dataset. The objective was to analyze sales performance, profitability and year-to-date performance across countries, products and accounts. I prepared the source data, structured the model using a star-schema approach, created DAX measures for YTD, previous-year YTD, YTD versus PYTD and gross profit percentage, and built KPI cards, a country treemap, monthly comparison, a hierarchical waterfall and an account-level scatter plot. An advanced part was the metric selector, which allows users to dynamically change the metric being analyzed. The goal was to move beyond reporting and help management understand performance drivers and profitability.

## GitHub Structure
```text
Plant-Sales-PowerBI-Analytics/
|-- README.md
|-- powerbi/
|   `-- Plant Sales Analytics.pbix
|-- data/
|   `-- Plant_DTS.xlsx
|-- docs/
|   `-- data_dictionary.csv
`-- screenshots/
    `-- README.md
```
