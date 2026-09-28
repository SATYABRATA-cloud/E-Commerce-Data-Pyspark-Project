# 🛒 Olist Brazilian E-Commerce Data Engineering & Analytics

## 📌 Project Overview

This project demonstrates an end-to-end **Big Data Engineering and Analytics workflow** using the **Olist Brazilian E-Commerce dataset**.

The project is implemented using **Apache Spark / PySpark** and follows a structured data pipeline:

> **Raw Data → HDFS → Data Ingestion → Data Exploration → Data Cleaning → Data Transformation → Data Integration → Aggregation → Business Analytics → Processed Parquet Data**

The main objective is to transform multiple raw e-commerce datasets into an integrated analytical dataset and generate useful business-level insights related to:

- Customers
- Orders
- Products
- Sellers
- Payments
- Reviews
- Geolocation
- Revenue
- Customer spending
- Seller performance
- Product popularity
- Customer retention
- Order status
- Order timing
- Customer segmentation

---

# 🎯 Project Objectives

The major objectives of this project are:

1. **Ingest raw e-commerce data** into a distributed storage environment.
2. Store the datasets in **HDFS**.
3. Use **PySpark** for distributed data processing.
4. Perform **data exploration and validation**.
5. Identify:
   - Missing values
   - Duplicate records
   - Data types
   - Data inconsistencies
   - Business-level patterns
6. Clean and standardize the datasets.
7. Handle missing values using appropriate strategies.
8. Detect and remove potential outliers.
9. Transform raw columns into business-friendly features.
10. Integrate multiple datasets using Spark joins.
11. Optimize joins using **Broadcast Joins**.
12. Use **caching** for frequently accessed DataFrames.
13. Perform aggregations using Spark functions.
14. Apply **Window Functions** for ranking.
15. Generate customer, seller, product, and order-level analytical metrics.
16. Store processed data in **Parquet format**.

---

# 🏗️ Project Architecture

```text
                         ┌──────────────────────────┐
                         │   Olist E-Commerce Data  │
                         │      Kaggle Dataset      │
                         └────────────┬─────────────┘
                                      │
                                      ▼
                         ┌──────────────────────────┐
                         │       Local / Master     │
                         │       Download Area      │
                         └────────────┬─────────────┘
                                      │
                                      ▼
                         ┌──────────────────────────┐
                         │          HDFS            │
                         │       /data/olist/       │
                         └────────────┬─────────────┘
                                      │
                                      ▼
                         ┌──────────────────────────┐
                         │       PySpark Read       │
                         │     CSV + inferSchema    │
                         └────────────┬─────────────┘
                                      │
                                      ▼
                 ┌────────────────────────────────────────┐
                 │       Data Exploration & Validation    │
                 │                                        │
                 │ • Schema inspection                    │
                 │ • Row-count validation                 │
                 │ • Null-value analysis                  │
                 │ • Duplicate detection                  │
                 │ • Business-level exploration           │
                 └───────────────────┬────────────────────┘
                                     │
                                     ▼
                 ┌────────────────────────────────────────┐
                 │       Data Cleaning & Transformation   │
                 │                                        │
                 │ • Missing-value handling               │
                 │ • Date conversion                      │
                 │ • Data-type standardization            │
                 │ • Payment standardization              │
                 │ • Duplicate removal                    │
                 │ • Outlier filtering                    │
                 │ • Product-weight categorization        │
                 └───────────────────┬────────────────────┘
                                     │
                                     ▼
                 ┌────────────────────────────────────────┐
                 │          Processed Parquet Data         │
                 │                                        │
                 │ • detailed_order.parquet               │
                 │ • cleaned_products.parquet             │
                 └───────────────────┬────────────────────┘
                                     │
                                     ▼
                 ┌────────────────────────────────────────┐
                 │       Data Integration & Enrichment    │
                 │                                        │
                 │ Orders + Items + Products + Sellers    │
                 │ + Customers + Geolocation + Reviews    │
                 │ + Payments                             │
                 └───────────────────┬────────────────────┘
                                     │
                                     ▼
                 ┌────────────────────────────────────────┐
                 │       Business Analytics Layer         │
                 │                                        │
                 │ • Seller revenue                       │
                 │ • Customer orders                      │
                 │ • Review metrics                       │
                 │ • Product popularity                   │
                 │ • Customer spending                    │
                 │ • Seller performance                   │
                 │ • Customer retention                   │
                 │ • Customer segmentation                │
                 │ • Order timing analysis                │
                 └────────────────────────────────────────┘
