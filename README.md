# Databricks PySpark ETL Pipeline – Store Orders Analytics

## Overview

This project implements an end-to-end ETL pipeline in Databricks using PySpark and Spark SQL to analyze e-commerce order data. The pipeline follows a bronze–silver–gold architecture to ingest raw data, apply data quality checks and business transformations, and produce analytics-ready marketing and discount metrics.

---

## Dataset

The input dataset represents online store orders and includes fields such as:

* OrderID, Date, CustomerID
* Product, Quantity, UnitPrice, TotalPrice
* CouponCode, ReferralSource
* PaymentMethod, OrderStatus, TrackingNumber

Only `CouponCode` is allowed to contain null values.

---

## ETL Architecture

**Bronze → Silver → Gold**

* **Bronze:** Raw CSV ingestion with schema inference
* **Silver:** Cleaned and enriched data with derived columns and data quality enforcement
* **Gold:** Aggregated business metrics built using Spark SQL

### Gold Layer (Business Metrics)

Built using Spark SQL on top of the silver layer:

**Coupon Usage Metrics**

* Total orders with coupons
* Coupon usage rate
* Average order value by coupon usage

**Referral & Marketing Attribution Metrics**

* Total orders per referral source
* Total revenue per referral source
* Coupon usage rate per referral source
* Average order value per referral source

---

## Technologies Used

* Databricks
* PySpark
* Spark SQL
* Python

---

## How to Run

1. Open the notebook in Databricks
2. Update the input file path if needed
3. Run cells top to bottom
4. Inspect silver-layer data and gold-layer aggregations
