# Amazon E-Commerce Sales Performance Analytics

## 📌 Project Overview
This project demonstrates an end-to-end data analytics workflow on Amazon Sales Data. It covers data cleaning in Excel, interactive dashboard design in Power BI, relational database querying using SQL, and programmatic data visualization with Python.

## 🛠️ Tech Stack Used
- *Excel:* Initial data exploration and verification.
- *Power BI:* Built dynamic dashboards with KPI cards, combo charts, and donut charts.
- *SQL (SQLite):* Managed database schema and performed complex aggregate queries.
- *Python (Pandas, Matplotlib, Seaborn):* Automated data pipelines and generated advanced analytical plots.

## 📊 Key Metrics Extracted
- *Total Orders:* 200
- *Total Revenue:* 8.40M
- *Total Profit:* 1.45M
- *Profit Margin:* 17.26%

## 💻 SQL Queries Implemented
```sql
-- 1. Main Business KPIs Table
SELECT 
    COUNT(DISTINCT Order_ID) AS Total_Orders,
    SUM(Sales_Amount) AS Total_Sales,
    SUM(Profit_Amount) AS Total_Profit,
    (SUM(Profit_Amount) / SUM(Sales_Amount)) * 100 AS Profit_Margin_Percent
FROM Amazon_Sales_FreshTable;

-- 2. Category Wise Performance
SELECT 
    Category,
    SUM(Sales_Amount) AS Category_Sales,
    SUM(Profit_Amount) AS Category_Profit
FROM Amazon_Sales_FreshTable
GROUP BY Category
ORDER BY Category_Sales DESC;
