
# Exploratory Data Analysis (EDA) Using SQL

## Project Overview

This project performs **Exploratory Data Analysis (EDA)** directly in SQL on a relational database using a **star schema**.
The objective is to understand the **structure, quality, distribution, and business behavior** of sales, customer, and product data before reporting or advanced analytics.

The analysis follows a **systematic EDA workflow**: schema exploration, dimension analysis, date analysis, measure exploration, segmentation, and ranking.

---

## Database Structure

The project uses the `gold` schema with the following core tables:

* `gold.fact_sales` – transactional sales data
* `gold.dim_customers` – customer demographic information
* `gold.dim_products` – product and category details

Metadata tables from `INFORMATION_SCHEMA` are also used to inspect database objects.

---

## Analysis Breakdown

### 1. Database & Schema Exploration

* Lists all tables in the database using `INFORMATION_SCHEMA.TABLES`
* Inspects column-level metadata using `INFORMATION_SCHEMA.COLUMNS`
* Helps understand table structure, column names, and data types before querying business data

Purpose: **schema familiarity and data discovery**

---

### 2. Dimension Exploration

**Customer Dimension**

* Identifies all countries customers belong to
* Analyzes customer distribution by geography

**Product Dimension**

* Explores product hierarchy using category, subcategory, and product name
* Validates the product hierarchy structure (category → subcategory → product)

Purpose: **understand categorical dimensions and hierarchies**

---

### 3. Date Exploration

* Identifies the first and last order dates from `fact_sales`
* Calculates the total number of years covered by the dataset
* Determines age range of customers using birthdates

Purpose: **validate data coverage and time span**

---

### 4. Measure Exploration (Key Metrics)

Computes core business measures:

* Total sales revenue
* Total quantity sold
* Average selling price
* Total number of distinct orders
* Total number of customers placing orders

A consolidated **key metrics report** is generated using `UNION ALL` to present all major KPIs in a single result set.

Purpose: **high-level business health check**

---

### 5. Measures by Dimensions

Analyzes metrics across key dimensions:

* Customers by country
* Customers by gender
* Products by category
* Revenue by product category
* Revenue contribution per customer
* Quantity sold distribution across countries

Purpose: **identify dominant segments and revenue drivers**

---

### 6. Ranking Analysis

Performs ranking-based insights:

* Top 5 products by revenue
* Bottom 5 products by revenue
* Top 10 customers by total revenue generated

Purpose: **identify best-performing and underperforming entities**

---

## SQL Concepts Used

* Metadata queries (`INFORMATION_SCHEMA`)
* Aggregate functions (`SUM`, `AVG`, `COUNT`, `MIN`, `MAX`)
* Joins between fact and dimension tables
* Date functions (`DATEDIFF`)
* Sorting and ranking (`ORDER BY`, `TOP`)
* Data consolidation using `UNION ALL`

---

## How to Run

1. Ensure the `gold` schema and required tables exist
2. Execute queries sequentially in a SQL environment
3. Review outputs at each stage to interpret insights

---

## Business Value

This project demonstrates how SQL can be used to:

* Perform complete exploratory analysis without external tools
* Validate data quality and coverage
* Identify revenue drivers and customer concentration
* Prepare datasets for dashboards, reporting, or modeling

---

## Use Cases

* Data Analyst portfolio project
* SQL interview preparation
* Pre-dashboard exploratory analysis
* Business performance assessment

---

## Author

Aditya Singh


