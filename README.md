📘 SQL Joins & Aggregations — Practice Guide
📌 Overview
This project demonstrates different types of SQL joins and aggregations using practical scenarios. Each query highlights how to combine tables, classify data, and calculate metrics. The examples cover INNER JOIN, LEFT JOIN, FULL OUTER JOIN, CASE statements, GROUP BY, SUM, COUNT, and ORDER BY.

🛠️ Requirements
SQL-compatible database (e.g., PostgreSQL, MySQL, Snowflake, SQL Server, Oracle)

Tables used in examples:

students, grades, employees, departments, products, sales, orders, customers, regions, attendance, projects, tasks, returns, users, logins, teachers, subjects

📂 Queries
1. 🎓 INNER JOIN — Students with Grades Only
sql
SELECT s.student_id,
       s.student_name,
       g.grade
FROM students s
INNER JOIN grades g
  ON s.student_id = g.student_id;
Returns only students who have grades recorded.

Excludes students without grades.

2. 👩‍💼 LEFT JOIN — Employees with or without Departments
sql
SELECT e.emp_id,
       e.emp_name,
       d.dept_name
FROM employees e
LEFT JOIN departments d
  ON e.emp_id = d.emp_id;
Shows all employees.

Employees without departments will have NULL in dept_name.

3. 📦 FULL OUTER JOIN — Products and Sales
sql
SELECT COALESCE(p.product_id, s.product_id) AS product_id,
       p.product_name,
       s.quantity
FROM products p
FULL OUTER JOIN sales s
  ON p.product_id = s.product_id;
Combines all products and sales records.

Includes unmatched rows from both tables.

4. 🛒 LEFT JOIN + CASE — Customer Type Classification
sql
SELECT o.order_id,
       o.customer_id,
       o.amount,
       c.customer_name,
       CASE 
         WHEN c.customer_id IS NULL THEN 'New Customer'
         ELSE 'Returning Customer'
       END AS customer_type
FROM orders o
LEFT JOIN customers c
  ON o.customer_id = c.customer_id;
Labels customers as New if not found in customers table.

Otherwise, marks them as Returning.

5. 🌍 LEFT JOIN + GROUP BY + SUM — Sales per Region
sql
SELECT r.region_id,
       r.region_name,
       COALESCE(SUM(s.amount), 0) AS total_sales
FROM regions r
LEFT JOIN sales s
  ON r.region_id = s.region_id
GROUP BY r.region_id, r.region_name;
Aggregates total sales per region.

Regions with no sales show 0.

6. 🎓 LEFT JOIN + CASE — Attendance Classification
sql
SELECT s.student_id,
       s.name,
       a.days_present,
       CASE 
         WHEN a.days_present >= 15 THEN 'Excellent'
         WHEN a.days_present BETWEEN 6 AND 14 THEN 'Needs Improvement'
         WHEN a.days_present <= 5 THEN 'Poor Attendance'
         ELSE 'No Record'
       END AS attendance_status
FROM students s
LEFT JOIN attendance a
  ON s.student_id = a.student_id;
Classifies students based on attendance days.

Provides categories: Excellent, Needs Improvement, Poor Attendance, No Record.

7. 📋 INNER JOIN + COUNT + GROUP BY — Task Count per Project
sql
SELECT p.project_id,
       p.name,
       COUNT(t.task_id) AS task_count
FROM projects p
INNER JOIN tasks t
  ON p.project_id = t.project_id
GROUP BY p.project_id, p.name;
Counts tasks per project.

Only projects with tasks are included.

8. 🔄 FULL OUTER JOIN + CASE + WHERE — Customer Return Status
sql
SELECT COALESCE(o.cust_id, r.cust_id) AS cust_id,
       o.order_total,
       r.return_total,
       CASE 
         WHEN r.return_id IS NOT NULL THEN 'Returned'
         ELSE 'No Return'
       END AS return_status
FROM orders o
FULL OUTER JOIN returns r
  ON o.cust_id = r.cust_id
WHERE o.order_total > 100;
Classifies customers as Returned or No Return.

Filters only orders with total > 100.

9. 👤 LEFT JOIN + COUNT + ORDER BY — Login Count per User
sql
SELECT u.user_id,
       u.name,
       COUNT(l.login_date) AS login_count
FROM users u
LEFT JOIN logins l
  ON u.user_id = l.user_id
GROUP BY u.user_id, u.name
ORDER BY login_count DESC;
Counts logins per user.

Orders results by login count (highest first).

10. 👩‍🏫 LEFT JOIN + CASE + ORDER BY — Teachers with Subjects
sql
SELECT t.teacher_id,
       t.teacher_name,
       COALESCE(s.subject_name, 'No Subject Assigned') AS subject_name
FROM teachers t
LEFT JOIN subjects s
  ON t.teacher_id = s.teacher_id
ORDER BY t.teacher_name ASC;
Lists teachers with their subjects.

Labels teachers without subjects as No Subject Assigned.

Orders alphabetically by teacher name.
