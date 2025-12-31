-- ============================================
-- Sales Performance & Revenue Analysis
-- SQL Queries (CareerFoundry Project)
-- ============================================


-- 1. Preview sample data
SELECT *
FROM sales
LIMIT 10;


-- 2. Total revenue by product
SELECT
    Description,
    SUM(Quantity * UnitPrice) AS Total_Revenue
FROM sales
GROUP BY Description
ORDER BY Total_Revenue DESC
LIMIT 10;


-- 3. Revenue by country
SELECT
    Country,
    SUM(Quantity * UnitPrice) AS Total_Revenue
FROM sales
GROUP BY Country
ORDER BY Total_Revenue DESC;


-- 4. Monthly revenue trend
SELECT
    DATE_TRUNC('month', InvoiceDate) AS Month,
    SUM(Quantity * UnitPrice) AS Monthly_Revenue
FROM sales
GROUP BY Month
ORDER BY Month;


-- 5. Top customers by revenue
SELECT
    CustomerID,
    SUM(Quantity * UnitPrice) AS Total_Revenue
FROM sales
GROUP BY CustomerID
ORDER BY Total_Revenue DESC
LIMIT 10;
