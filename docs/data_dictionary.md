# Data Dictionary – Retail Sales Analytics Dashboard

Use this document to describe the dataset structure, important columns, derived metrics, and data quality considerations used in the Retail Sales Analytics Capstone Project.

---

# Dataset Summary

| Item | Details |
|------|---------|
| Dataset Name | Retail Sales Transaction Dataset |
| Source | Public Retail Sales Dataset / CSV Source |
| Raw File Name | final_dashboard.csv |
| Last Updated | April 2026 |
| Granularity | One row per order line item / transaction record |
| Total Rows | 5000+ |
| Total Columns | 10+ |

---

# Column Definitions

| Column Name | Data Type | Description | Example Value | Used In | Cleaning Notes |
|------------|----------|-------------|--------------|---------|----------------|
| Order ID | String | Unique identifier for each order | CA-2019-152156 | KPI / Tableau | Removed blanks, standardized text |
| Order Date | Date | Date when order was placed | 2020-03-15 | Trend Analysis / Tableau | Converted to datetime format |
| Ship Date | Date | Date when order was shipped | 2020-03-18 | EDA | Converted to datetime format |
| Customer Name | String | Full customer name | John Smith | Customer Analysis | Removed extra spaces |
| Segment | String | Customer segment type | Consumer | Tableau Filter | Standardized labels |
| Region | String | Sales region | West | KPI / Dashboard Filter | Fixed inconsistent spelling |
| State | String | State where sale occurred | California | Map / Regional Analysis | Standardized names |
| Category | String | Main product category | Furniture | KPI / Tableau | Fixed category casing |
| Sub-Category | String | Product subgroup | Chairs | Heatmap / EDA | Standardized text |
| Product Name | String | Name of sold product | Office Chair | Top Products | Cleaned special characters |
| Sales | Float | Revenue from transaction | 245.67 | KPI / Charts | Converted to numeric |
| Quantity | Integer | Number of units sold | 3 | KPI / EDA | Checked invalid values |
| Discount | Float | Discount percentage applied | 0.20 | Profitability Analysis | Converted to decimal |
| Profit | Float | Net profit earned | 54.20 | KPI / Heatmap | Converted to numeric |

---

# Derived Columns

| Derived Column | Logic | Business Meaning |
|---------------|------|------------------|
| Profit Margin % | Profit / Sales * 100 | Measures profitability efficiency |
| Month | Extract Month from Order Date | Used for monthly trend charts |
| Year | Extract Year from Order Date | Used for yearly filtering |
| Total Orders | Count(Order ID) | Measures business volume |
| Avg Order Value | Total Sales / Total Orders | Indicates customer spending |
| Loss Flag | Profit < 0 | Detects loss-making transactions |

---

# KPI Fields Used in Dashboard

| KPI Name | Formula | Purpose |
|---------|---------|---------|
| Total Sales | SUM(Sales) | Total revenue generated |
| Total Profit | SUM(Profit) | Total earnings after costs |
| Total Orders | COUNT(Order ID) | Total number of orders |
| Profit Margin | SUM(Profit)/SUM(Sales) | Overall business profitability |

---

# Data Quality Notes

1. Missing values were found in selected customer and shipping fields.
2. Duplicate transaction rows were checked and removed.
3. Some category labels had inconsistent capitalization.
4. Date fields required conversion to standard date format.
5. Numeric columns contained text formatting issues in some rows.
6. Outlier sales values were retained as valid business transactions.
7. Discount-heavy transactions impacted profit negatively.

---

# Cleaning Actions Performed

- Removed duplicate rows  
- Converted dates to datetime format  
- Standardized category and region names  
- Trimmed spaces from text columns  
- Converted Sales, Profit, Discount to numeric types  
- Created derived KPI fields for dashboarding  
- Exported cleaned dataset for Tableau Public  

---

# Usage in Project

This dataset was used for:

- Python ETL & Data Cleaning  
- Exploratory Data Analysis  
- KPI Computation  
- Tableau Dashboard Creation  
- Final Business Recommendations  

---

# Maintained By

Retail Sales Analytics Project Team  
Capstone Submission – 2026