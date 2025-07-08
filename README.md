# RETAILS  SALES  ANALYSIS SQL PROJECT:-
# Project Overview:-
**Project Title**:- Retails  Sales Analysis
**Database**:-SQL - Retails  Sales Analysis_utf
**Skills**:-(SQL)explore,clean and analyze
<br>


# OBJECTIVES:- 
•	Set up a retail sales database.<br>
• **Data Cleaning**: Identify and remove any records with missing or null values.<br>
•	**Exploratory Data Analysis (EDA)**: Perform basic exploratory data analysis to understand the dataset.<br>
•	**Business Analysis**: Use SQL to answer specific business questions and derive insights from the sales data.<br>
<br>

# PROJECT STRUCTURE:-
1.**database setup**:- use create database for creating the table retails_sales<br>
2.**Table Creation**:-use create  table in which we will write all the columns and store the data.<br>
3.**Columns**:-transaction ID, sale date, sale time, customer ID, gender, age, product category, quantity sold, price per unit, cost of goods sold (COGS), and total sale amount.<br>
```sql
CREATE DATABASE p1_retail_db;

CREATE TABLE retail_sales
(
    transactions_id INT PRIMARY KEY,
    sale_date DATE,
    sale_time TIME,
    customer_id INT,
    gender VARCHAR(10),
    age INT,
    category VARCHAR(35),
    quantity INT,
    price_per_unit FLOAT,
    cogs FLOAT,
    total_sale FLOAT
);
```
# DATA EXPLORATION AND CLEANING:
-**Record count**:- check total number of rows in table.<br>
-**NULL value**:-Check the null value in the table and Delete those data.<br>
-**Customer Count**:-find how many unique customer id in dataset.<br>
-**Category Count**:-Indetify all unique products in dataset.<br>

```sql
SELECT COUNT(*) FROM retail_sales;
SELECT COUNT(DISTINCT customer_id) FROM retail_sales;
SELECT DISTINCT  category FROM retail_sales;
SELECT * FROM  retail_sales
WHERE 
 sale_date IS NULL OR sale_time IS NULL OR customer_id  IS NULL OR  gender IS NULL OR 
  age IS NULL OR  category IS NULL OR  quantity IS NULL OR price_per_unit IS NULL OR cogs IS NULL OR total_sale IS NULL
DELETE from retail_sales
WHERE 
 sale_date IS NULL OR sale_time IS NULL OR customer_id  IS NULL OR  gender IS NULL OR 
  age IS NULL OR  category IS NULL OR  quantity IS NULL OR price_per_unit IS NULL OR cogs IS NULL OR total_sale IS NULL;
;
```
**Exploring**<br>
-Find total sales<br>
-Identify unique customer<br>- total category<br>
  ```sql SELECT COUNT(*) AS total_sales FROM retail_sales;
  SELECT COUNT( DISTINCT customer_id) AS total_customer FROM retail_sales;
  SELECT DISTINCT category FROM retail_sales;
```
##  Business Problems and Solutions
The following SQL queries were developed to answer specific business questions:<br>
1.**Write a SQL query to retrieve all the columns of sales made on '2022-11-05**?
```sql
SELECT * FROM  retail_sales WHERE sale_date='2022-11-05';
```
2.**Write a SQL query to retrieve all the transcations  where the category is 'Clothing' and quantity sold is more than 4 in a month of Nov-2022**?
```sql
SELECT * FROM retail_sales
  WHERE category='Clothing'  AND to_char(sale_date,'YYYY-MM')='2022-11' AND quantity >= 4;
```
3.**Write a SQL query  to calculate the total sales for each category**?
```sql
SELECT  category,SUM(total_sale),COUNT(*) AS net_sale from retail_sales GROUP BY 1;
```
4.**Write a SQL query to find the average age of customers who purchased itmes from 'Beauty' category**?
```sql
SELECT ROUND(AVG(age),2) FROM retail_sales WHERE category='Beauty';
```
5.**Write a SQL query  to find all transactions  where the total sales is greater than 1000**?
```sql
SELECT * FROM  retail_sales WHERE total_sale >'1000';
```
6.**Write a SQL query to find the total number of transactions(transaction_id) made by each gender in each category?**
```sql
SELECT  gender ,category,COUNT(*) AS total_Transactions FROM retail_sales
GROUP BY  gender,category ORDER BY 2;
```








