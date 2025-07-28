# SQL-Project-1---eCommerce

## 📚 Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Database](#database)
- [Data Processing](#data-processing)
- [Project Includes](#project-includes)
- [Tools Used](#tools-used)
- [Conclusion](#conclusion)
- [Contact Me](#contact-me)

---

## 🔍 Overview
This project is a hands-on SQL analysis of the **Olist Brazilian E-commerce** dataset — a real marketplace operating in Brazil with multiple sellers and thousands of customers. The idea is to treat this like a real data analyst case: dive into the raw data, write exploratory and KPI-driven queries, and surface insights that could actually help a business.

Everything is documented as a step-by-step journal. I walk through what questions I’m trying to answer, what SQL I’m writing to get there, and what I’m learning along the way.

---

## 🛠️ Tools Used

- **SQL:** For data cleaning, transformation, and analytical querying  
- **SMSS:** Used as the database engine to store and manage the relational dataset   
- **Tableau:** For visualization of results and reporting

---


## 📦 Dataset

The dataset used in this project comes from **Olist**, a real Brazilian e-commerce marketplace that connects multiple sellers to customers across Brazil. It contains detailed historical data on thousands of orders placed between 2016 and 2018. The dataset is publicly available on [Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) and is known for its completeness and authenticity.

It includes information such as:

- Order and delivery timestamps  
- Customer and seller location data  
- Product details and categories  
- Payment methods and amounts  
- Customer reviews and ratings  

This rich structure allows for in-depth analysis of customer behavior, product performance, logistics, and satisfaction trends.

---

## 🗄️ Database

To manage and explore the dataset effectively, a **relational SQL database** has been created. PostgreSQL is used to store and query the data. The schema has been designed to reflect the natural relationships between orders, customers, sellers, and products.

Key relationships include:

- Customers placing multiple orders  
- Each order containing one or more products  
- Sellers fulfilling different items across various orders  
- Reviews linked to each order for quality assessment  

This structure supports complex queries and enables robust data slicing for KPIs, trends, and insight generation.

---




 ## Schema structure




<img width="2486" height="1496" alt="schema" src="https://github.com/user-attachments/assets/4c025686-043d-4f7f-b99d-4f5a9a02d3b8" />



---

## 🧹 Data Processing

The raw CSV files from the Kaggle dataset required some initial cleaning and preparation. SQL scripts were written to:




- Import and load the data into SQL Server Management Studio

  The raw dataset files (CSV format) were uploaded directly into SQL Server Management Studio (SSMS) using the "Import Flat File..." wizard. This allowed me to create all tables easily with their respective columns and data types, without (mostly) changing the type.



<img width="825" height="750" alt="image" src="https://github.com/user-attachments/assets/c8dd8fd6-91d2-4500-ac07-cb98c58cc20e" />
<img width="826" height="753" alt="image" src="https://github.com/user-attachments/assets/2415d635-8f7e-451b-9809-b7b79d18999f" />



  
- Handle missing or null values

I’m checking for blank and NULL values across all key tables in the Olist dataset. This helps identify any data quality issues that could affect the accuracy of the analysis. For each table, I count how many rows are missing critical fields like IDs, timestamps, payment values, or location data.

Example:

<pre> 
 
 SELECT 
    COUNT(*) AS total_rows,
    SUM(CASE WHEN order_id IS NULL THEN 1 ELSE 0 END) AS missing_order_id,
    SUM(CASE WHEN order_item_id IS NULL THEN 1 ELSE 0 END) AS missing_order_item_id,
    SUM(CASE WHEN product_id IS NULL THEN 1 ELSE 0 END) AS missing_product_id,
    SUM(CASE WHEN seller_id IS NULL THEN 1 ELSE 0 END) AS missing_seller_id,
    SUM(CASE WHEN shipping_limit_date IS NULL THEN 1 ELSE 0 END) AS missing_shipping_limit_date,
    SUM(CASE WHEN price IS NULL THEN 1 ELSE 0 END) AS missing_price,
    SUM(CASE WHEN freight_value IS NULL THEN 1 ELSE 0 END) AS missing_freight_value
FROM olist_order_items_dataset;
 
  </pre>

I then run the equivalent code for each table, confirming the number of rows containing NULL values and excluding them.

  
- Normalize formats (e.g., dates)

Here the scope is to check the formats of key fields such as dates or costs. If in a wrong format change that.  

Example:
<img width="1381" height="133" alt="image" src="https://github.com/user-attachments/assets/f9358cc4-165b-4eb8-baa0-cd76b8bb93b4" />


Here we change the date using the CAST function, we are not going to do an analysis that requires the precise moment.

<pre> 
 
 ALTER TABLE olist_orders_dataset
ALTER COLUMN order_purchase_timestamp DATE;

ALTER TABLE olist_orders_dataset
ALTER COLUMN order_approved_at DATE;

ALTER TABLE olist_orders_dataset
ALTER COLUMN order_delivered_carrier_date DATE;

ALTER TABLE olist_orders_dataset
ALTER COLUMN order_delivered_customer_date DATE;

ALTER TABLE olist_orders_dataset
ALTER COLUMN order_estimated_delivery_date DATE;

 
 </pre>
  
Result: ![Uploading image.png…]()

  
- Join tables to build a unified view of customer journeys




  



---

## 📈 Project Includes

- **Overview:** A high-level summary of key performance indicators (KPIs), such as total revenue, average delivery time, top product categories, and review score distribution.

- **Sales by Product Category:** SQL queries and visual summaries identifying top-performing product categories based on total revenue and number of orders.

- **Customer Analysis:** Exploration of customer behavior by region (state and city), including purchase frequency, order value, and retention trends.

- **Geographical Analysis:** Insights into how sales and delivery performance vary across Brazil using customer and seller location data.

- **Time-Based Analysis:** Monthly trends in order volume, revenue, and review scores to identify seasonal patterns and market shifts over time.

- **Review & Satisfaction Metrics:** Analysis of customer reviews to understand sentiment, delivery experience, and seller performance.

- **Planned Dashboard:** A Tableau dashboard (coming soon) will allow interactive filtering by category, region, delivery status, review score, and more.

---


