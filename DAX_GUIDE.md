# DAX Learning Guide

## Basic measures
```DAX
Total Sales = SUM(Plant_FACT[Sales_USD])
Total COGS = SUM(Plant_FACT[COGS_USD])
Gross Profit = [Total Sales] - [Total COGS]
GP % = DIVIDE([Gross Profit], [Total Sales])
```

## Time intelligence concepts
Learn:
- Date table
- Mark as Date Table
- YTD
- PYTD
- YoY
- MTD
- QTD
- Rolling 12 months

## Important functions
CALCULATE()
FILTER()
ALL()
ALLSELECTED()
REMOVEFILTERS()
DATEADD()
SAMEPERIODLASTYEAR()
TOTALYTD()
SUMX()
DIVIDE()
SWITCH()

## Important concepts
- Filter context
- Row context
- Context transition
- Measures vs calculated columns
- Relationships
- Star schema
