# 🧠 Advanced SQL Project for Data Analysis | AtliQ Hardware (Codebasics Case Study)

![SQL Logo](https://img.shields.io/badge/SQL-MySQL-blue?style=flat-square)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## 📌 Project Overview

I completed a comprehensive **SQL case study project** from [Codebasics](https://www.codebasics.io/), simulating the role of an analyst at **AtliQ Hardware**, a company operating in the consumer electronics industry. The project focused on solving real business problems using advanced SQL and delivering insights for various stakeholders such as Sales, Marketing, and Finance.

🔍 The project covered:
- Business-oriented data modeling
- Advanced SQL concepts like **CTEs, Views, Procedures, Window Functions**
- Query optimization & indexing
- Data extraction & transformation for reporting
- Output visualization in **Excel (bar, pie charts)**

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **MySQL** | Query execution, data modeling, procedures, and indexing |
| **DBeaver / MySQL Workbench** | SQL IDE |
| **Excel** | Visualizing query outputs using charts |
| **Codebasics Case Study** | Project framework and dataset |

## 🧱 Database Design & Concepts Learned

- **Star schema**: Fact and dimension tables used to simulate real business scenarios
- **Database normalization**
- **ERD** (Entity Relationship Diagram) & schema planning
- **Backfilling data**
- **Agile methodology**: Implemented tasks using Kanban principles (WIP limits)
- **Data Governance in MySQL**: User privileges and access control

## 💡 Key SQL Features Used

| Feature | Description |
|--------|-------------|
| ✅ CTEs (Common Table Expressions) | Layered query design |
| ✅ Window Functions | `OVER()`, `RANK()`, `DENSE_RANK()`, `ROW_NUMBER()` |
| ✅ Stored Procedures | Parametrized reporting logic |
| ✅ Temporary Tables | For intermediate processing |
| ✅ Views | Modular queries for reuse |
| ✅ Subqueries | Dynamic filtering & calculations |
| ✅ Indexing | Used B-Tree, composite indexes, full-text search (`MATCH()` / `AGAINST()`) |
| ✅ Triggers & Events | To handle data insertion rules and scheduled data cleaning |

## 📊 Real-World Use Cases Simulated

> Each task below replicates real analytics reporting needs.

### 🧾 Task 1: Monthly Sales Report for Amazon India (FY 2021)

- Created functions to derive fiscal year and quarter
- Aggregated product-wise sales with gross price
- Output visualized in Excel bar chart

```sql
SELECT 
    s.date, p.product, p.variant,
    SUM(s.sold_quantity) AS total_quantity_sold,
    MIN(g.gross_price) AS gross_price_per_item,
    SUM(g.gross_price * s.sold_quantity) AS gross_price_total
FROM fact_sales_monthly s
JOIN gross_price g ON ...
...
```

### 📆 Task 2: Monthly Sales Report for Croma

- Focused on one customer (`90002002`)
- Grouped and sorted data by month for trend analysis

### 🔁 Task 3: Top Products, Customers, Markets by Net Sales

- Built a **view** pipeline: `pre_invoice ➡ post_invoice ➡ net_sales`
- Created reusable **stored procedures**

### 📈 Task 4 & 5: Net Sales % Analysis

- Used **CTEs + window functions** to calculate percentage share by:
  - Customer
  - Region
- Final result exported and visualized using **bar/pie charts in Excel**

### 🏆 Task 6: Top N Products per Division by Quantity Sold

- Used `DENSE_RANK()` over each division to rank top N products
- Parameterized logic via stored procedure

### 📊 Task 7: Forecast Accuracy Report

- Compared `forecast_quantity` vs. `sold_quantity`
- Calculated metrics like:
  - Net error
  - Absolute error
  - Forecast accuracy %
- Output: Prioritized customers by accuracy for FY insights

## ⚙️ Sample Stored Procedure

```sql
CREATE PROCEDURE get_forecast_accuracy(
	in_fiscal_year INT
)
BEGIN
	WITH forecast_err_table AS (
		SELECT ...
	)
	SELECT c.market, c.customer, e.*,
		   IF (abs_err_pct > 100, 0, 100 - abs_err_pct) AS forecast_accuracy
	FROM forecast_err_table e
	JOIN dim_customer c USING (customer_code)
	ORDER BY forecast_accuracy DESC;
END
```

## 📁 Repository Structure

```
Advanced-SQL-Project-For-Data-Analysis--AtliQ-Hardware/
│
├── SQL/
│   └── SQL Queries Files
│   
│   
├── Output/
│   └── Excel Output Files
│   
│   
├── Images/
│   └── charts and query screenshots
│
│
└── README.md
```

## 📘 Learnings & Takeaways

- Deep understanding of **modular SQL design**
- Writing **clean, reusable, and optimized queries**
- Real-world exposure to **reporting logic**, **stored procedures**, and **query planning**
- Practiced **data extraction, cleaning, and visualization**
- Understood how SQL is used in:
  - ETL pipelines
  - BI tools
  - Ad-hoc business analysis
  - CRUD and data migration
  - Reporting dashboards

## 🔗 Connect with Me

📧 **Email**: sunnykryadav71432@gmail.com  
💼 **LinkedIn**: [Sunny Kumar Yadav](https://www.linkedin.com/in/sunnykumaryadav)  
📂 **GitHub**: [Sunny-Kumar-Yadav](https://github.com/Sunny-Kumar-Yadav)

> **⭐ If you found this project helpful or insightful, feel free to star the repo!**  
> I'm open to feedback, collaboration, and internship/full-time opportunities in data analytics.
