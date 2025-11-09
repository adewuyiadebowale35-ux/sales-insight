
 
# 🧠 Sales & Customer Insights Dashboard  
*A Business Intelligence project using SQL and Power BI*
 
![Dashboard Overview](/sales_insights.png)
 
---
 
## 📘 Project Overview
 
This project demonstrates end-to-end **data analysis and visualization** using **SQL** for data processing and **Power BI** for reporting.  
It simulates a retail company's dataset, covering **customers**, **products**, and **sales transactions**, and delivers insights into revenue, customer behavior, and product performance.
 
---
 
## 🧱 Tech Stack
 
| Tool | Purpose |
|------|----------|
| 🐘 **PostgreSQL** | Database for storing and querying data |
| 💾 **SQL** | Data cleaning, aggregation, and transformation |
| 📊 **Power BI Desktop** | Interactive dashboards and KPI reports |
| 📁 **CSV Files** | Source data for import and sharing |
| 💻 **GitHub** | Project version control and documentation |
 
---
 
## 🧩 Data Model
 

 
The data model follows a **Star Schema** design:
 
- **Fact Table:** `sales`
- **Dimension Tables:** `customers`, `products`
 
**Relationships:**
- `sales.customer_id → customers.customer_id`
- `sales.product_id → products.product_id`
 
---
 
## 🧾 Dataset Description
 
### 🧍‍♀️ `customers.csv`
| Column | Description |
|---------|-------------|
| `customer_id` | Unique ID for each customer |
| `first_name`, `last_name` | Customer names |
| `gender`, `age` | Demographics |
| `region` | Sales region (North, South, East, West) |
| `join_date` | Date the customer joined |
 
### 🛒 `products.csv`
| Column | Description |
|---------|-------------|
| `product_id` | Unique product ID |
| `product_name` | Product name |
| `category`, `subcategory` | Product classification |
| `price` | Unit price of the product |
 
### 💰 `sales.csv`
| Column | Description |
|---------|-------------|
| `sale_id` | Transaction ID |
| `customer_id` | Links to customer |
| `product_id` | Links to product |
| `sale_date` | Date of sale |
| `quantity` | Quantity sold |
| `discount` | Discount applied to sale |
 
---
 
## 🧮 SQL Highlights
 

 
**Example 1 — Total Revenue**
```sql
SELECT 
    SUM(s.quantity * p.price * (1 - s.discount)) AS total_revenue
FROM sales s
JOIN products p ON s.product_id = p.product_id;
 
  
