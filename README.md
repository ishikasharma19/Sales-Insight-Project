# Sales-Insight-Project
This project involves performing data analysis on customer transaction records using SQL and Tableau. The goal is to analyze sales, revenue, and profit metrics for different markets, with a specific focus on Chennai. SQL queries are used for data extraction and analysis, while Tableau is used for creating dashboards to visualize insights.

Technologies Used
SQL: Querying and analyzing customer and transaction data.
Tableau: Visualizing data and creating insightful dashboards.
Database: MySQL (connected with Tableau for visualization).
SQL Queries for Data Analysis:

Show all customer records:
SELECT * FROM customers;
This query retrieves all customer information from the customers table.



Show the total number of customers:
SELECT COUNT(*) FROM customers;
This query returns the total count of customers in the dataset.



Show transactions for the Chennai market:
SELECT * FROM transactions WHERE market_code = 'Mark001';
This query fetches all transactions from the Chennai market (market code: 'Mark001').



Show distinct product codes sold in Chennai:
SELECT DISTINCT product_code FROM transactions WHERE market_code = 'Mark001';
This query displays all the unique product codes sold in the Chennai market.



Show transactions where the currency is US dollars:
SELECT * FROM transactions WHERE currency = 'USD';
This query lists all transactions conducted in USD.



Show transactions in the year 2020:
SELECT transactions.*, date.*
FROM transactions
INNER JOIN date ON transactions.order_date = date.date
WHERE date.year = 2020;
This query joins the transactions table with the date table to retrieve all transactions made in 2020.



Show total revenue in 2020:
SELECT SUM(transactions.sales_amount)
FROM transactions
INNER JOIN date ON transactions.order_date = date.date
WHERE date.year = 2020 
AND (transactions.currency = 'INR' OR transactions.currency = 'USD');
This query calculates the total revenue generated in 2020, considering transactions in both INR and USD.



Show total revenue for January 2020:
SELECT SUM(transactions.sales_amount)
FROM transactions
INNER JOIN date ON transactions.order_date = date.date
WHERE date.year = 2020 
AND date.month_name = 'January'
AND (transactions.currency = 'INR' OR transactions.currency = 'USD');
This query shows the total revenue for January 2020, filtered by month and currency.



Show total revenue in Chennai for 2020:
SELECT SUM(transactions.sales_amount)
FROM transactions
INNER JOIN date ON transactions.order_date = date.date
WHERE date.year = 2020
AND transactions.market_code = 'Mark001';
This query calculates the total revenue generated in the Chennai market in 2020.



Customer with the highest purchase:
SELECT CustomerID, SUM(Quantity * UnitPrice) AS TotalSpent
FROM SalesTransactions
GROUP BY CustomerID
ORDER BY TotalSpent DESC
LIMIT 1;
This query identifies the customer who spent the most by summing the total purchases for each customer and returning the highest value.



Tableau Dashboard:
In this project, Tableau was used for visualizing the sales, revenue, and profit analysis. The following key insights were visualized:
Revenue Analysis Dashboard:
Visualization Focus: Total revenue generated by different markets over time, with a special emphasis on Chennai.
Key Metrics: Revenue by month/year, revenue by market, and revenue trends.
Profit Analysis Dashboard:

Visualization Focus: Profitability across different products and regions.
Key Metrics: Profit margins by product category, region-wise profit distribution, and comparison of revenue vs. cost.
Sales Insight Dashboard:

Visualization Focus: Overall sales performance and market segmentation.
Key Metrics: Sales volume by region, product performance, and sales trends over different time periods.
Each dashboard provides a comprehensive view of the sales and profitability across different regions and time frames, helping stakeholders make data-driven decisions.

