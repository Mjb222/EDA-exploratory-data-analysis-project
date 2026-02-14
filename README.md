# EDA-exploratory-data-analysis-project
exploratory-data-analysis-project
# Retail Sales SQL Exploration

This project contains SQL scripts for exploring and analyzing a retail sales database using MySQL. It covers database discovery, customer and product dimensions, sales measures, and ranking analyses for products and customers.[web:60][web:71]

## Dataset Overview

- **Database schema:** `gold`
- **Fact table:** `gold.fact_sales`  
  - Example fields: `order_number`, `order_date`, `customer_key`, `product_key`, `quantity`, `price`, `sales_amount`
- **Dimension tables:**  
  - `gold.dim_customers` (customer demographics and country)  
  - `gold.dim_products` (category, subcategory, product details)[web:60]

## Folder and File Structure

- `sql/`
  - `01_exploration.sql` – database and schema exploration (tables, columns, distinct countries, categories)
  - `02_measures.sql` – key measures (total sales, quantities, orders, products, customers)
  - `03_magnitude.sql` – distributions by country, gender, category
  - `04_ranking.sql` – top/bottom products and top customers by revenue[web:60][web:72]

(You can keep a single `.sql` file if you prefer; this structure is a recommended best practice.)

## Main Analyses

- **Data exploration**
  - List all tables and inspect columns in `dim_customers`
  - Explore unique countries and product categories

- **Date exploration**
  - First and last order dates
  - Number of years of sales coverage
  - Youngest and oldest customers (birthdate and age)

- **Measures and KPIs**
  - Total quantity sold and average price
  - Total and distinct order counts
  - Total products and customers
  - One consolidated “key metrics” query returning core business KPIs

- **Magnitude and segmentation**
  - Customers by country and gender
  - Products by category
  - Average cost per category
  - Revenue by category, customer, and country

- **Ranking**
  - Top 5 products by revenue (`LIMIT 5`)
  - Bottom 5 products by revenue using `ROW_NUMBER()` window function
  - Top 10 customers by revenue[web:60]

## How to Run

1. Set up a MySQL 8.0+ instance (for window functions like `ROW_NUMBER`).[web:32][web:41]
2. Create and populate the `gold.fact_sales`, `gold.dim_customers`, and `gold.dim_products` tables.
3. Open the `.sql` script(s) in your SQL client (MySQL Workbench, DBeaver, etc.).
4. Run the queries section by section; they are grouped by purpose and documented with inline comments.

## Good Practices Followed

- Clear section headers inside the SQL file (`-- Data Exploration`, `-- Measures Exploration`, `-- RANKING`).
- Consistent naming for aliases (e.g., `total_revenue`, `total_customers`).
- Use of `LIMIT` instead of `TOP` for MySQL compatibility.
- Use of `ROW_NUMBER()` window function for ranking (requires MySQL 8.0+).
- Separate logical concerns (exploration, measures, magnitude, ranking) to make the script easy to read and reuse.[web:60][web:71]

## Possible Extensions

- Add time-series analyses (monthly or yearly revenue trends).
- Create views for common metrics (e.g., `vw_customer_revenue`, `vw_product_revenue`).
- Connect this SQL to a BI tool (Power BI, Tableau) for visual dashboards.[web:70]
