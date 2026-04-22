# 🛍️ SQL Retail Sales Analysis Project

![SQL](https://img.shields.io/badge/SQL-Data%20Analysis-blue?style=for-the-badge\&logo=postgresql)
![Project](https://img.shields.io/badge/Project-Retail%20Sales-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

---

## 🚀 🔥 Tech Badges (Animated Style)

![SQL](https://img.shields.io/badge/SQL-Expert-blueviolet?style=for-the-badge\&logo=postgresql\&logoColor=white)
![Data Analysis](https://img.shields.io/badge/Data%20Analysis-Project-orange?style=for-the-badge\&logo=databricks\&logoColor=white)
![CTE](https://img.shields.io/badge/CTE-Advanced-success?style=for-the-badge)
![Queries](https://img.shields.io/badge/Queries-Business%20Insights-informational?style=for-the-badge)
![Status](https://img.shields.io/badge/Made%20With-SQL-ff69b4?style=for-the-badge\&logo=postgresql)

---

## 📌 Project Overview

This project focuses on analyzing **retail sales data using SQL** to uncover meaningful business insights.

It covers:

* Database creation
* Data cleaning
* Data exploration
* Business problem solving using SQL queries

---

## 🧰 Tech Stack

* SQL (MySQL / PostgreSQL compatible)
* Relational Database Concepts

---

## 📂 Dataset Description

The dataset contains retail transaction data with the following columns:

| Column Name    | Description                    |
| -------------- | ------------------------------ |
| transaction_id | Unique ID for each transaction |
| sale_date      | Date of sale                   |
| sale_time      | Time of sale                   |
| customer_id    | Unique customer ID             |
| gender         | Customer gender                |
| age            | Customer age                   |
| category       | Product category               |
| quantity       | Quantity purchased             |
| price_per_unit | Price per unit                 |
| cogs           | Cost of goods sold             |
| total_sale     | Total transaction value        |

---

## ⚙️ Database Setup

```sql
CREATE DATABASE sql_project;
```

### Table Creation

```sql
CREATE TABLE retail_sales (
    transaction_id INT PRIMARY KEY,
    sale_date DATE,
    sale_time TIME,
    customer_id INT,
    gender VARCHAR(15),
    age INT,
    category VARCHAR(15),
    quantity INT,
    price_per_unit FLOAT,
    cogs FLOAT,
    total_sale FLOAT
);
```

---

## 🧹 Data Cleaning

Handled missing/null values:

```sql
DELETE FROM retail_sales
WHERE 
    transaction_id IS NULL OR
    sale_date IS NULL OR
    sale_time IS NULL OR
    gender IS NULL OR
    category IS NULL OR
    quantity IS NULL OR
    cogs IS NULL OR
    total_sale IS NULL;
```

---

## 🔍 Data Exploration

* Total number of sales
* Unique customers
* Product categories

```sql
SELECT COUNT(*) FROM retail_sales;
SELECT COUNT(DISTINCT customer_id) FROM retail_sales;
SELECT DISTINCT category FROM retail_sales;
```

---

## 📊 Business Questions & Analysis

### 🧠 Key Insights Solved

✔️ Sales on a specific date
✔️ High-volume clothing transactions
✔️ Total sales per category
✔️ Average customer age (Beauty category)
✔️ High-value transactions

---

## ⏰ Time-Based Sales Analysis

Segmented sales into shifts:

* 🌅 Morning
* 🌤️ Afternoon
* 🌙 Evening

```sql
WITH hourly_sale AS (
    SELECT *,
        CASE
            WHEN EXTRACT(HOUR FROM sale_time) < 12 THEN 'Morning'
            WHEN EXTRACT(HOUR FROM sale_time) BETWEEN 12 AND 17 THEN 'Afternoon'
            ELSE 'Evening'
        END AS shift
    FROM retail_sales
)

SELECT shift, COUNT(*) 
FROM hourly_sale
GROUP BY shift;
```

---

## 📈 Key Learnings

* Writing efficient SQL queries
* Using CTEs (`WITH` clause)
* Data cleaning techniques
* Aggregation & grouping
* Business-driven analysis

---

## 🚀 How to Run

1. Clone the repository

```bash
git clone https://github.com/your-username/sql-retail-sales-analysis.git
```

2. Open your SQL environment
3. Run the SQL file step by step

---

## 🔗 GitHub Repository

👉 https://github.com/your-username/sql-retail-sales-analysis

---

## 💡 Future Improvements

* Add dashboards (Power BI / Tableau)
* Perform advanced analytics
* Add stored procedures
* Automate reporting

---

## 🙌 Acknowledgment

This project is part of hands-on practice to strengthen SQL skills for **data analysis roles**.

---

⭐ If you found this useful, consider giving it a star!

