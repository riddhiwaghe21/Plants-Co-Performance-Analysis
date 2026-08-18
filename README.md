# Plants Co. Performance Analysis

### Power BI Dashboard | Sales & Profitability Analysis

---

## 📊 About the Project

I created this dashboard to analyze the sales performance of **Plants Co.** and understand how the business is performing across different countries, products, and customer accounts.

The main purpose of this project was to take the sales data available in Excel and turn it into an interactive Power BI dashboard where the performance can be explored instead of looking through rows of raw data.

I focused mainly on **Sales, Gross Profit, Gross Profit %, YTD Sales, Previous Year YTD Sales, and YTD vs PYTD performance**.

---

## 🎯 What I Wanted to Find

While working on the project, I wanted the dashboard to answer questions such as:

- How much sales are we generating?
- How much gross profit are we making?
- How is the current year performing compared with the previous year?
- Which countries contribute the most to sales?
- Which products and product sizes are performing well?
- Which customer accounts have high sales?
- Are high-sales accounts also generating good margins?
- Where are the major changes in performance coming from?

---

## 📁 Dataset

The project uses an Excel workbook containing three main tables.

### 1. Plant_FACT

This is the main sales transaction table.

It contains information such as:

- Sales
- Quantity
- Price
- COGS
- Product ID
- Account ID
- Date

### 2. Accounts

This table contains information about customer accounts, including:

- Account
- Country
- Country Code
- Location information

### 3. Plant_Hierarchy

This table contains product-related information such as:

- Product Family
- Product Group
- Product Name
- Product Size
- Product Type

---

## 🛠️ Tools I Used

- **Microsoft Excel** – Source data
- **Power BI** – Data modeling, DAX and dashboard development
- **Power Query** – Data preparation
- **DAX** – Calculations and performance analysis

---

## 🔄 My Approach

I followed these steps while building the project:

1. Understood the structure of the Excel dataset.
2. Checked the different tables and their columns.
3. Prepared the data using Power Query.
4. Created relationships between the tables.
5. Created measures using DAX.
6. Built KPIs for sales and profitability.
7. Added YTD and previous-year comparisons.
8. Created interactive charts, slicers and filters.
9. Analyzed the results.
10. Converted the observations into business insights.

---

## 🧮 DAX Measures

The main measures I worked with include:

```DAX
Total Sales =
SUM(Plant_FACT[Sales_USD])

Total COGS =
SUM(Plant_FACT[COGS_USD])

Gross Profit =
[Total Sales] - [Total COGS]

GP % =
DIVIDE([Gross Profit], [Total Sales])
```

### What these measures mean

**Total Sales**

Calculates the total sales generated from all transactions.

**Total COGS**

Calculates the total cost of goods sold.

**Gross Profit**

Shows the amount remaining after subtracting COGS from sales.

**GP %**

Shows gross profit as a percentage of total sales.

---

## 📅 YTD & PYTD Analysis

I also worked with **YTD (Year to Date)** and **PYTD (Previous Year to Date)** to compare the current year's performance with the corresponding period from the previous year.

For example:

```text
Current YTD
January → Selected Date

Previous Year YTD
January → Same Date in Previous Year
```

This provides a fairer comparison than comparing a partial year with a complete previous year.

The dashboard uses measures such as:

- `S_YTD`
- `S_PYTD`
- `YTD VS PYTD`
- `GP%`

---

# 📊 Dashboard

The dashboard contains different views for looking at the business from different angles.

## 1. KPI Section

The KPI section provides a quick overview of the important numbers, including:

- YTD Sales
- Previous Year YTD Sales
- YTD vs PYTD
- Gross Profit %

This allows a user to understand the overall situation before looking at the detailed charts.

---

## 2. Country Analysis

I used a treemap to compare performance across countries.

This helps identify the markets contributing most to sales and performance changes.

The analysis can then be used to ask further questions such as:

- Which countries are growing?
- Which countries are declining?
- Is a country's sales growth also profitable?
- What products are driving a particular country?

---

## 3. Monthly Performance

The monthly chart compares current YTD performance with the previous year.

This helps identify months where performance improved or declined.

Instead of only looking at the final KPI, the monthly view helps understand the movement throughout the period.

---

## 4. Waterfall Analysis

The waterfall chart allows the change to be investigated through different levels:

```text
Month
   ↓
Country
   ↓
Product Type
   ↓
Product Name
```

I used this visual because I wanted to understand not only **whether performance changed**, but also **which areas contributed to the change**.

This makes the analysis more diagnostic.

---

## 5. Account Analysis

The scatter chart compares:

**YTD Sales vs GP%**

This helps identify different types of accounts.

### High Sales + High GP%

These can be considered strong accounts because they generate both revenue and good margins.

### High Sales + Low GP%

These accounts generate significant revenue but may need profitability investigation.

### Low Sales + High GP%

These accounts may have potential for growth.

### Low Sales + Low GP%

These accounts may require further investigation.

---

# 🔎 Some Observations

From the dataset, I found that:

- **China** is one of the strongest markets by sales.
- **Outdoor** products contribute the highest sales among the product types.
- **Large-sized** products have the highest sales among the product sizes.
- The current YTD period can be compared with the previous year's corresponding period to understand performance movement.
- Some accounts generate high sales but should also be evaluated based on their profitability.

These observations would need further investigation before making business decisions. A high sales value alone does not necessarily mean that an account or product is highly profitable.

---

# 💡 Business Questions I Would Investigate Further

If this were being used by an actual business team, I would investigate:

### Sales

- Why are some countries growing faster than others?
- Which products are driving sales growth?
- Which months have the strongest performance?

### Profitability

- Which accounts have high sales but low GP%?
- Which products have the highest margins?
- Are high-sales countries also highly profitable?

### Customers

- Which accounts contribute the most revenue?
- Are the largest accounts becoming more or less profitable?
- Which accounts could have growth potential?

---

# 📚 What I Learned From This Project

This project helped me understand that creating a dashboard is not just about selecting charts.

I learned how to:

- Understand a business dataset
- Identify fact and dimension tables
- Build relationships between tables
- Prepare data using Power Query
- Create DAX measures
- Work with YTD and previous-year comparisons
- Use filters and slicers
- Select appropriate visuals for different questions
- Analyze sales and profitability together
- Turn dashboard numbers into business questions

One of the biggest things I learned was to **look beyond the KPI**.

For example, if sales decrease, the next question should be:

> **What caused the decrease?**

Then I can break it down by country, product, account, month or product type.

---

# 🚀 Future Improvements

If I continue working on this project, I would like to add:

- Monthly sales trend analysis
- Customer contribution %
- Top and bottom accounts
- Product profitability analysis
- Rolling 12-month sales
- Sales forecasting
- More detailed drill-through pages
- Dynamic KPI titles
- Row-level security
- Performance optimization

---

# 📂 Project Structure

```text
plants-co-performance-analysis/
│
├── README.md
│
├── powerbi/
│   └── Plants Co. Performance Analysis.pbix
│
├── data/
│   └── Plant_DTS.xlsx
│
├── docs/
│   ├── DAX_GUIDE.md
│   ├── INTERVIEW_GUIDE.md
│   └── data_dictionary.csv
│
└── screenshots/
    ├── 01-kpi-dashboard.png
    ├── 02-main-dashboard.png
    └── 03-analysis-view.png
```

---

# 🎓 Project Type

**Personal Data Analytics Project**

**Tools:** Power BI | DAX | Power Query 

**Focus:** Sales Analysis | Profitability Analysis | Business Performance

---

## 👩‍💻 Author

**Riddhi Waghe**

Data Analytics | Power BI | SQL | Excel | Python | Tableau
