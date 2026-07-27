# Zepto E-commerce SQL Data Analysis

An end-to-end SQL data analytics project using PostgreSQL to analyze Zepto's e-commerce inventory data through data cleaning, exploratory data analysis (EDA), and business-focused SQL queries.

---
## 📌 Project Overview

The goal is to simulate how actual data analysts in the e-commerce or retail industries work behind the scenes to use SQL to:

✅ Set up a messy, real-world e-commerce inventory **database**

✅ Perform **Exploratory Data Analysis (EDA)** to explore product categories, availability, and pricing inconsistencies

✅ Implement **Data Cleaning** to handle null values, remove invalid entries, and convert pricing from paise to rupees

✅ Write **business-driven SQL queries** to derive insights around **pricing, inventory, stock availability, revenue** and more

## 📁 Dataset Overview
The dataset was sourced from [Kaggle](https://www.kaggle.com/datasets/palvinder2006/zepto-inventory-dataset/data?select=zepto_v2.csv) and was originally scraped from Zepto’s official product listings. It mimics what you’d typically encounter in a real-world e-commerce inventory system.

Each row represents a unique SKU (Stock Keeping Unit) for a product. Duplicate product names exist because the same product may appear multiple times in different package sizes, weights, discounts, or categories to improve visibility – exactly how real catalog data looks.

🧾 Columns:
- **sku_id:** Unique identifier for each product entry (Synthetic Primary Key)

- **name:** Product name as it appears on the app

- **category:** Product category like Fruits, Snacks, Beverages, etc.

- **mrp:** Maximum Retail Price (originally in paise, converted to ₹)

- **discountPercent:** Discount applied on MRP

- **discountedSellingPrice:** Final price after discount (also converted to ₹)

- **availableQuantity:** Units available in inventory

- **weightInGms:** Product weight in grams

- **outOfStock:** Boolean flag indicating stock availability

- **quantity:** Number of units per package (mixed with grams for loose produce)

## 🔧 Project Workflow

Here’s a step-by-step breakdown of what we do in this project:

### 1. Database & Table Creation
We start by creating a SQL table with appropriate data types:

```sql
CREATE TABLE zepto (
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);
```

### 2. Data Import
- Imported the CSV dataset into PostgreSQL using pgAdmin.

### 3. 🔍 Data Exploration
- Counted the total number of records in the dataset

- Viewed a sample of the dataset to understand structure and content

- Checked for null values across all columns

- Identified distinct product categories available in the dataset

- Compared in-stock vs out-of-stock product counts

- Detected products present multiple times, representing different SKUs

### 4. 🧹 Data Cleaning
- Identified and removed rows where MRP or discounted selling price was zero

- Converted mrp and discountedSellingPrice from paise to rupees for consistency and readability
  
### 5. 📊 Business Insights
- Found top 10 best-value products based on discount percentage

- Identified high-MRP products that are currently out of stock

- Estimated potential revenue for each product category

- Filtered expensive products (MRP > ₹500) with minimal discount

- Ranked top 5 categories offering highest average discounts

- Calculated price per gram to identify value-for-money products

- Grouped products based on weight into Low, Medium, and Bulk categories

- Measured total inventory weight per product category

# 🛠️ Tools & Technologies

- PostgreSQL
- SQL
- GitHub

# 📊 Analysis Performed

- Product Analysis
- Category Analysis
- Pricing Analysis
- Discount Analysis
- Inventory Analysis
- Business Performance Analysis

---

# 📈 Results & Key Outcomes

The analysis helped identify meaningful patterns within Zepto's e-commerce product data.

### Key Outcomes

- Cleaned and prepared product data for analysis.
- Used SQL to answer business questions.
- Analyzed pricing and discount patterns.
- Explored product categories and inventory.
- Generated actionable insights to support data-driven business decisions.

---

# ▶️ How to Run

### PostgreSQL

1. Create a PostgreSQL database.
2. Import the dataset into PostgreSQL.
3. Open the SQL script.
4. Execute the SQL queries.
5. Review the generated business insights.

---

# 📂 Project Structure

```text
Zepto-Ecommerce-SQL-Analysis/
│
├── Dataset/
│   └── zepto.csv
│
├── SQL/
│   └── zepto_sql_data_analysis.sql
│
└── README.md
```

---

# 🎯 Skills Demonstrated

- SQL
- PostgreSQL
- Data Cleaning
- Exploratory Data Analysis (EDA)
- Data Analysis
- Business Intelligence
- Business Problem Solving
- Data-Driven Decision Making

---

# 👩‍💻 Author

**Somya Singhal**

This project demonstrates my ability to import, clean, analyze, and interpret e-commerce data using PostgreSQL and SQL to generate meaningful business insights and support data-driven decision-making.
