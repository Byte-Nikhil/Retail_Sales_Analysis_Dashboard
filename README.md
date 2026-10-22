# 📊 Retail Sales Analysis Dashboard

> An interactive two-page **IBM Cognos Analytics** dashboard that turns 2,000 raw retail transactions (Jan 2022 – Dec 2023) into clear KPIs, sales trends, and customer-segment insights for product and marketing decisions.

---

## 🎯 Business Problem

A retail business has two years of transaction data but no quick way to see what drives revenue. This dashboard answers:

- How are sales and profit performing overall and over time?
- Which product categories contribute the most sales and profit?
- Which customer segments (gender, age group) generate the most revenue?
- At what time of day and in which months do customers buy the most?

## 🖼️ Dashboard Preview

### Page 1 – Sales Performance
KPI tiles, sales trend over time, and sales by time of day.

![Sales Performance](screenshots/01_sales_performance.png)

### Page 2 – Customer & Category Insights
Sales by gender and age group, category sales, and a profit treemap.

![Customer & Category Insights](screenshots/02_customer_category_insights.png)

## ✨ Key Features

- **KPI tiles:** total sales, transactions, quantity sold, average sale
- **Trend analysis:** sales over time and by time of day (Morning / Afternoon / Evening / Night)
- **Customer segmentation:** sales by gender and age group
- **Category analysis:** sales, quantity, and profit (treemap) by category
- **Interactive filters:** category, age group, and gender on both pages for drill-down analysis

## 🔍 Key Insights

*Calculated from the full, unfiltered dataset.*

| # | Insight | Evidence |
|---|---|---|
| 1 | **Sales surge in the last four months of the year** | Sep–Dec sales of ~523K make up ~57% of total sales. Monthly sales from Jan–Aug stay between 41K and 58K, then jump to 126K–142K from September. |
| 2 | **Evenings drive most revenue** | Sales between 17:00 and 22:59 total ~570K, about 62% of all sales. |
| 3 | **Ages 20–35 are the top-spending segment** | ~314K in sales, the highest of any age group (50+ follows with ~283K). Under-20 customers contribute the least (~52K). |
| 4 | **Categories are evenly matched** | Electronics (~314K), Clothing (~311K), and Beauty (~287K). |
| 5 | **Strong and consistent margins** | Profit is ~79% of sales overall, with each category between 78.6% and 79.7%. |
| 6 | **Gender split is nearly even** | Female ~465K vs Male ~446K. |

## 💡 Suggested Business Actions

- Plan inventory and promotions ahead of the September–December peak.
- Schedule campaigns and staffing for evening hours, when most sales happen.
- Target the 20–35 age group with marketing, and look for ways to grow the under-20 segment.
- Since all three categories perform similarly, use category-level promotions to balance Beauty against Electronics and Clothing.

## 🛠️ Tools & Skills

| Area | Details |
|---|---|
| BI Tool | IBM Cognos Analytics (dashboards, filters, calculated fields) |
| Data Preparation | Missing-value handling, data cleaning, data transformation |
| Visualization | KPI tiles, line/bar charts, pie chart, treemap, bubble chart |

## 🧹 Data Preparation

1. **Handled missing values:** 10 records had no age, and 3 had no quantity, price, COGS, or total sale.
2. **Created calculated fields:**
   - **Age group:** less than 20 · 20 to < 36 · 36 to < 50 · 50 and above
   - **Time-of-day group:** Morning, Afternoon, Evening, Night (from sale time)
   - **Profit:** `total_sale − cogs`
3. **Built the model and dashboards** in Cognos with shared filters across both pages.

## 📁 Dataset

File: [`data/Retail_Sales_Dataset.csv`](data/Retail_Sales_Dataset.csv) – 2,000 transactions, 1 Jan 2022 to 31 Dec 2023.

| Column | Description |
|---|---|
| `transactions_id` | Unique transaction ID |
| `sale_date`, `sale_time` | Date and time of sale |
| `customer_id` | Customer identifier |
| `gender`, `age` | Customer demographics |
| `category` | Beauty, Clothing, or Electronics |
| `quantiy` | Units sold (column name as in the source data) |
| `price_per_unit` | Price per unit |
| `cogs` | Cost of goods sold |
| `total_sale` | Total sale amount |

## 📂 Repository Structure

```
Retail_Sales_Analysis_Dashboard/
├── README.md
├── data/
│   └── Retail_Sales_Dataset.csv
└── screenshots/
    ├── 01_sales_performance.png
    └── 02_customer_category_insights.png
```

## ▶️ How to Use

1. Browse the screenshots above for a quick preview of both dashboard pages.
2. To rebuild it, upload `data/Retail_Sales_Dataset.csv` to IBM Cognos Analytics, create the calculated fields listed above, and recreate the visuals.

## 👤 Author

**P Nikhil Pavan**
[LinkedIn](https://www.linkedin.com/in/pnikhilpavan/) · [GitHub](https://github.com/Byte-Nikhil) · nikhilpavan7478000226@gmail.com
