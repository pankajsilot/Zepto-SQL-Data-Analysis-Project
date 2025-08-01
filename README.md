# 🏥 Zepto SQL Data Analysis Project 📊

Welcome to my end-to-end Data Analyst portfolio project, where I perform real-world SQL data analysis on Zepto's e-commerce inventory dataset using **PostgreSQL**.

This project simulates real-life business scenarios in the e-commerce space, including database design, data cleaning, and deriving insights to support inventory and pricing decisions.

---

## 🎓 Objective
To showcase SQL skills through a complete data analytics workflow using PostgreSQL and a real dataset scraped from Zepto – a fast-growing Indian quick-commerce startup. The project includes:
- Schema creation
- Data import & cleaning
- Exploratory data analysis (EDA)
- Business insights extraction using SQL

---

## 📁 Dataset Overview
The dataset consists of inventory data from Zepto's product listings. Each row represents a unique SKU (Stock Keeping Unit) for a product, mimicking real-world catalog data.

**Columns include:**
- `sku_id`: Unique ID (Synthetic Primary Key)
- `name`: Product name
- `category`: Product category
- `mrp`: Maximum Retail Price (in rupees)
- `discountPercent`: Discount %
- `discountedSellingPrice`: Final price after discount
- `availableQuantity`: Inventory units available
- `weightInGms`: Product weight
- `outOfStock`: Boolean (in stock or not)
- `quantity`: Units per package

---

## ⚙️ Tools & Technologies Used
- **Database**: PostgreSQL
- **Interface**: pgAdmin
- **Language**: SQL
- **Platform**: Jupyter Notebook / Local PostgreSQL Client

---

## 📆 Project Steps

### 1. 📂 Table Schema Creation
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

### 2. 📂 Data Import
Imported the CSV into PostgreSQL using `\copy` command after fixing UTF-8 encoding issues.
```sql
\copy zepto(category, name, mrp, discountPercent, availableQuantity,
      discountedSellingPrice, weightInGms, outOfStock, quantity)
FROM 'data/zepto_v2.csv' WITH (FORMAT csv, HEADER true);
```

### 3. 🔍 Data Exploration
- Count of total records
- Check nulls & duplicates
- Analyze product categories
- Stock availability overview
- Duplicate entries with different weights/prices

### 4. 🧹 Data Cleaning
- Removed zero MRP/price rows
- Converted price values from paise to rupees

### 5. 📊 Business Analysis Using SQL
- Top 10 best-discounted products
- Out-of-stock expensive products
- Revenue potential per category
- Average discount by category
- Value for money using price per gram
- Weight segmentation (Low, Medium, Bulk)

---

## 🌟 Sample Insights
- **97% of inventory** priced under ₹500
- **"Fruits & Vegetables"** have highest total inventory weight
- **Top 5 discount categories**: Bakery, Snacks, Beverages...
- Revenue potential highest in **Snacks** and **Dairy** categories

---

## 🌐 How to Run This Project
1. Clone this repository
```bash
git clone https://github.com/pankajsilot/zepto-sql-data-analysis-project.git
cd zepto-sql-data-analysis-project
```
2. Open `zepto_SQL_data_analysis.sql`
3. Create a PostgreSQL database
4. Import the dataset into pgAdmin
5. Run SQL script step by step

---

## 🏆 Outcomes & Skills Gained
- Structured a normalized e-commerce inventory database
- Applied real-life SQL queries for business KPIs
- Gained experience with messy data wrangling
- Practiced data-driven decision-making through SQL

---

## 📘 References
- [Dataset on Kaggle](https://www.kaggle.com/datasets/palvikg/zepto-inventory-dataset)

---

## 📚 License
This project is licensed under the MIT License.

---

> ✨ If you found this helpful, feel free to give a star and check out my other portfolio projects!
