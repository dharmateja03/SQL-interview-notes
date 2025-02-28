# SQL Interview Preparation

A comprehensive collection of SQL concepts, techniques, and examples to help you prepare for technical interviews.

## Table of Contents

- [Basic SQL](#basic-sql)
- [Joins](#joins)
- [Aggregation Functions](#aggregation-functions)
- [Window Functions](#window-functions)
- [String Functions](#string-functions)
- [Date/Time Functions](#datetime-functions)
- [Conditional Logic](#conditional-logic)
- [Subqueries](#subqueries)
- [Common Table Expressions (CTEs)](#common-table-expressions-ctes)
- [Indexing](#indexing)
- [Transaction Management](#transaction-management)
- [Performance Optimization](#performance-optimization)
- [Interview Questions](#interview-questions)

## Template Structure

Each concept is documented using the following template:

| Keyword/Concept | Usage/Syntax | Example |
|----------------|--------------|---------|
| Specific SQL command, function, or concept | Description of what it does and syntax | Practical example with sample code |

## Basic SQL

| Keyword/Concept | Usage/Syntax | Example |
|----------------|--------------|---------|
| SELECT | Retrieves data from database tables | `SELECT first_name, last_name FROM employees` |
| INSERT | Adds new records to a table | `INSERT INTO products (name, price) VALUES ('Widget', 19.99)` |
| UPDATE | Modifies existing records | `UPDATE customers SET status = 'Active' WHERE id = 123` |
| DELETE | Removes records from a table | `DELETE FROM orders WHERE status = 'Cancelled'` |
| WHERE | Filters results based on conditions | `SELECT * FROM users WHERE signup_date > '2023-01-01'` |
| ORDER BY | Sorts results | `SELECT * FROM products ORDER BY price DESC` |
| LIMIT/TOP | Restricts the number of rows returned | `SELECT * FROM transactions LIMIT 100` |
| DISTINCT | Returns unique values | `SELECT DISTINCT department_id FROM employees` |

## Joins

| Keyword/Concept | Usage/Syntax | Example |
|----------------|--------------|---------|
| INNER JOIN | Returns records with matching values in both tables | `SELECT o.id, c.name FROM orders o INNER JOIN customers c ON o.customer_id = c.id` |
| LEFT JOIN | Returns all records from left table and matched records from right table | `SELECT d.name, COUNT(e.id) FROM departments d LEFT JOIN employees e ON d.id = e.dept_id GROUP BY d.name` |
| RIGHT JOIN | Returns all records from right table and matched records from left table | `SELECT e.name, d.name FROM employees e RIGHT JOIN departments d ON e.dept_id = d.id` |
| FULL OUTER JOIN | Returns all records when there is a match in either table | `SELECT e.name, d.name FROM employees e FULL OUTER JOIN departments d ON e.dept_id = d.id` |
| CROSS JOIN | Returns Cartesian product of both tables | `SELECT c.name, p.name FROM customers c CROSS JOIN products p` |
| SELF JOIN | Joins a table to itself | `SELECT e1.name, e2.name FROM employees e1 JOIN employees e2 ON e1.manager_id = e2.id` |

## Aggregation Functions

| Keyword/Concept | Usage/Syntax | Example |
|----------------|--------------|---------|
| COUNT | Counts rows or non-NULL values | `SELECT department_id, COUNT(*) FROM employees GROUP BY department_id` |
| SUM | Calculates sum of values | `SELECT SUM(amount) FROM transactions WHERE status = 'Completed'` |
| AVG | Calculates average of values | `SELECT AVG(salary) FROM employees WHERE department = 'Engineering'` |
| MIN/MAX | Finds minimum or maximum value | `SELECT MIN(price), MAX(price) FROM products` |
| GROUP BY | Groups rows with the same values | `SELECT category, AVG(price) FROM products GROUP BY category` |
| HAVING | Filters groups based on conditions | `SELECT department_id, AVG(salary) FROM employees GROUP BY department_id HAVING AVG(salary) > 50000` |

## Window Functions

| Keyword/Concept | Usage/Syntax | Example |
|----------------|--------------|---------|
| ROW_NUMBER | Assigns unique row number | `SELECT name, price, ROW_NUMBER() OVER (ORDER BY price DESC) AS rank FROM products` |
| RANK | Assigns rank with gaps | `SELECT name, score, RANK() OVER (ORDER BY score DESC) FROM exam_results` |
| DENSE_RANK | Assigns rank without gaps | `SELECT name, score, DENSE_RANK() OVER (ORDER BY score DESC) FROM exam_results` |
| NTILE | Divides rows into specified number of groups | `SELECT name, price, NTILE(4) OVER (ORDER BY price) AS quartile FROM products` |
| LAG/LEAD | Access previous/next row values | `SELECT date, amount, LAG(amount) OVER (ORDER BY date) AS previous_amount FROM transactions` |
| SUM OVER | Running total | `SELECT date, amount, SUM(amount) OVER (ORDER BY date) AS running_total FROM transactions` |
| PARTITION BY | Divides rows into partitions | `SELECT department, name, salary, AVG(salary) OVER (PARTITION BY department) AS dept_avg FROM employees` |

## String Functions

| Keyword/Concept | Usage/Syntax | Example |
|----------------|--------------|---------|
| CONCAT | Combines strings | `SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM users` |
| SUBSTRING | Extracts part of string | `SELECT SUBSTRING(phone, 1, 3) AS area_code FROM customers` |
| UPPER/LOWER | Converts case | `SELECT UPPER(email) FROM users` |
| LENGTH | Returns string length | `SELECT name, LENGTH(name) AS name_length FROM products` |
| REPLACE | Replaces substring | `SELECT REPLACE(description, 'old', 'new') FROM products` |
| LIKE | Pattern matching | `SELECT * FROM customers WHERE email LIKE '%@gmail.com'` |
| TRIM | Removes spaces | `SELECT TRIM(name) FROM users` |

## Date/Time Functions

| Keyword/Concept | Usage/Syntax | Example |
|----------------|--------------|---------|
| CURRENT_DATE | Returns current date | `SELECT CURRENT_DATE` |
| EXTRACT | Gets component from date/time | `SELECT EXTRACT(YEAR FROM order_date) FROM orders` |
| DATE_TRUNC | Truncates date to specified precision | `SELECT DATE_TRUNC('month
