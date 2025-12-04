# 📘 SQL Joins & Aggregations — Practice Guide

## 📌 Summary of the Case Study
This case study demonstrates how SQL queries can be applied to combine tables and calculate metrics using **joins and aggregations**. The project explored practical scenarios with INNER JOIN, LEFT JOIN, FULL OUTER JOIN, CASE statements, GROUP BY, SUM, COUNT, and ORDER BY. The goal was to show how relational data can be connected and transformed into **business insights** across domains such as education, HR, sales, customer management, and project tracking.

---

## 🔍 How the Case Study Was Done
1. **Dataset Exploration**
   - Tables used:  
     `students`, `grades`, `employees`, `departments`, `products`, `sales`,  
     `orders`, `customers`, `regions`, `attendance`, `projects`, `tasks`,  
     `returns`, `users`, `logins`, `teachers`, `subjects`.

2. **SQL Query Development**
   - **INNER JOIN** → Linked students with grades, and projects with tasks.  
   - **LEFT JOIN** → Retrieved employees with or without departments, customers with orders, students with attendance, users with logins, and teachers with subjects.  
   - **FULL OUTER JOIN** → Combined products with sales and orders with returns, ensuring unmatched records were included.  
   - **CASE Statements** → Classified customers as New/Returning, attendance as Excellent/Needs Improvement/Poor, and return status as Returned/No Return.  
   - **GROUP BY & Aggregations** → Summed sales per region, counted tasks per project, and calculated login counts per user.  
   - **ORDER BY** → Sorted results by salary, login count, or teacher names for clarity.  

3. **Techniques Applied**
   - **Joins** → INNER, LEFT, FULL OUTER to combine related tables.  
   - **Conditional Logic** → CASE statements for classification.  
   - **Aggregations** → SUM, COUNT for grouped metrics.  
   - **Sorting** → ORDER BY for ranking and readability.  
   - **Null Handling** → COALESCE to replace NULLs with meaningful defaults.  

---

## 📊 Insights Found
- INNER JOIN queries revealed **students with grades** and **projects with tasks**, excluding incomplete records.  
- LEFT JOIN queries highlighted **employees without departments**, **customers without prior records**, and **teachers without subjects assigned**.  
- FULL OUTER JOIN queries ensured **all products and sales** were captured, including unmatched entries.  
- CASE logic provided **customer segmentation** (New vs. Returning), **attendance classification**, and **return status tracking**.  
- Aggregations showed **sales totals per region**, **task counts per project**, and **login activity per user**, supporting operational insights.  
- Sorting improved readability, e.g., ranking users by login count or listing teachers alphabetically.  

---

## 🎯 Summary of Findings
By applying SQL joins and aggregations, the project uncovered:  
- How to **connect related tables** for complete analysis.  
- Methods to **classify and segment records** using CASE logic.  
- Aggregated insights into **sales, attendance, tasks, and logins**.  
- Practical techniques for handling **NULL values** and ensuring comprehensive reporting.  

This demonstrates how SQL joins and aggregations can deliver **business intelligence** across multiple domains, supporting **education analytics, HR management, sales tracking, and customer engagement**.

---

## 🛠️ Tools Used
- **SQL-compatible environments** (PostgreSQL, MySQL, Snowflake, SQL Server, Oracle)  
- **SQL functions** (INNER JOIN, LEFT JOIN, FULL OUTER JOIN, CASE, SUM, COUNT, GROUP BY, ORDER BY, COALESCE)  
- **Optional Visualization Tools**: Power BI, Excel (pivot tables, dashboards)  

