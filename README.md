# Edviron_Analytics
# EDVIRON Revenue, Commission & Settlement Analytics Dashboard

## Overview

This project is an end-to-end financial analytics solution built in **Microsoft Excel (Power Query + Pivot Data Model + VBA)** to analyze payment transactions processed through Edviron’s platform.

The objective of the project is to transform raw transaction data into meaningful business insights such as revenue sharing, partner performance, settlement obligations, and operational risk exposure.
The final output is an interactive dashboard designed for finance and operations teams to monitor platform performance daily.

---

## Business Context

Edviron operates as a payment intermediary between ERP partners and educational institutions. Each transaction contains three pricing layers:

1. **Merchant Pricing** – Fee charged by ERP partner to school
2. **Partner Pricing** – Fee charged by Edviron to ERP partner
3. **Edviron Buying** – Payment gateway processing cost paid by Edviron

From these layers, revenue is generated for both ERP partners and Edviron.

### Revenue Definitions

* **ERP Revenue (ERP Commission)**
  Merchant Pricing − Partner Pricing

* **Edviron Net Revenue (Platform Margin)**
  Partner Pricing − Edviron Buying

* **Edviron Gross Revenue (Total Platform Revenue)**
  ERP Revenue + Edviron Net Revenue

---

## Features Implemented

### 1. Data Cleaning & Transformation

* Combined multiple partner sheets into a single master dataset using **Power Query**
* Standardized mixed date formats
* Removed inconsistent and blank columns
* Converted text numeric fields to decimal values
* Normalized Flat and Percentage pricing formats

### 2. Pricing Normalization

All pricing inputs were converted into **INR per transaction**:

* Flat → used directly
* Percentage → Transaction Amount × Rate / 100

This ensured consistent financial calculations.

### 3. Financial Calculations

Per-transaction computations include:

* ERP Revenue
* Edviron Net Revenue
* Edviron Gross Revenue
* ERP Payable
* Edviron Retained Amount
* Gateway Fee

### 4. Settlement & Risk Analytics

The model simulates the real payment settlement workflow:

* Gateway settles full amount to Edviron
* Edviron transfers partner share

Risk monitoring metrics:

* Unsettled Gateway Exposure
* Pending Transaction Risk
* Duplicate Order Detection
* Negative Margin Identification

### 5. Interactive Dashboard

The Excel dashboard provides dynamic filtering using slicers and timeline.

#### Key KPI Tiles

* Total Transactions
* Unique Users
* Total GMV
* ERP Commission Earned
* Edviron Net Margin
* Total Platform Revenue
* Unsettled Gateway Exposure

#### Visualizations

* Monthly Revenue Trend
* Revenue Split (ERP vs Edviron)
* Gateway Contribution
* Payment Method Distribution
* Partner Performance Analysis

### 6. VBA Automation

A macro button **“Refresh Data”** refreshes all Power Query connections and PivotTables in one click, simulating a daily operational reporting workflow.

---

## Tools & Technologies

* Microsoft Excel 365
* Power Query (ETL & Data Cleaning)
* Pivot Data Model (Data Modeling)
* GETPIVOTDATA (Dynamic KPIs)
* Slicers & Timeline (Interactivity)
* VBA (Automation)

---

## Project Structure

```
EDVIRON_Revenue_Analytics.xlsm
│
├── Raw_Data                # Original dataset (unchanged)
├── Clean_Data              # Cleaned & standardized data
├── Calc_Model              # Revenue & settlement calculations
├── Reports                 # Pivot-based analytical reports
├── Dashboard               # Interactive business dashboard
├── Exceptions              # Risk & anomaly detection
└── Assumptions_Notes       # Documentation & logic explanation
```

---

## Key Assumptions

1. Percentage pricing is applied to Transaction Amount.
2. Revenue is recognized only for successful transactions.
3. Exposure risk applies only to successful but uncaptured payments.
4. Missing pricing values are treated as zero.

---

## How to Use

1. Download the `.xlsm` file
2. Open in Microsoft Excel
3. Click **Enable Content (Macros)**
4. Press **Refresh Data** button
5. Use slicers to filter by:

   * ERP Partner
   * Payment Gateway
   * Payment Method
   * Transaction Status
   * Date Range

---

## Outcome

The dashboard converts raw transactional data into a structured financial monitoring system that helps:

* Track platform earnings
* Monitor partner performance
* Identify settlement obligations
* Detect operational risk

---

## Author

**Hemanth Mandarapu**
Data Analytics & Data Engineering Enthusiast
