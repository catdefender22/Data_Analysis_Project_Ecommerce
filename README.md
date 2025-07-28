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
- **PostgreSQL:** Used as the database engine to store and manage the relational dataset   
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

- Import and load the data into PostgreSQL  
- Handle missing or null values  
- Normalize formats (e.g., dates, IDs)  
- Create indexes to improve query performance  
- Join tables to build a unified view of customer journeys  

All processing steps are documented and versioned, ensuring full transparency. This cleaned and structured data now serves as the foundation for querying, analysis, and future dashboard development in Tableau.

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


