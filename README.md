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
SELECT COUNT(*) FROM retails_sale;
SELECT COUNT(DISTINCT customer_id) FROM retails_sale;
SELECT DISTINCT  category FROM retails_sale;
SELECT * FROM  retails_sale
WHERE 
 sale_date IS NULL OR sale_time IS NULL OR customer_id  IS NULL OR  gender IS NULL OR 
  age IS NULL OR  category IS NULL OR  quantiy IS NULL OR price_per_unit IS NULL OR cogs IS NULL OR total_sale IS NULL
DELETE from retails_sale
WHERE 
 sale_date IS NULL OR sale_time IS NULL OR customer_id  IS NULL OR  gender IS NULL OR 
  age IS NULL OR  category IS NULL OR  quantiy IS NULL OR price_per_unit IS NULL OR cogs IS NULL OR total_sale IS NULL;
;
```







