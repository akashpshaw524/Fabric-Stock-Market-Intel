# Microsoft Fabric Stock Market Intelligence Platform

## Project Overview

This project demonstrates an end-to-end Data Engineering solution built using Microsoft Fabric, PySpark, Lakehouse Architecture, Semantic Models, and Power BI.

The solution ingests stock market data from Yahoo Finance, processes it through a Medallion Architecture (Bronze → Silver → Gold), orchestrates execution using Fabric Pipelines, and exposes business-ready insights through a Power BI dashboard.

---

## Business Objective

Provide a centralized market intelligence platform capable of:

* Tracking stock performance
* Monitoring sector performance
* Identifying momentum opportunities
* Detecting high-volume trading activity
* Measuring stock volatility
* Supporting analytical reporting

---

## Technology Stack

* Microsoft Fabric
* Fabric Lakehouse
* PySpark
* Delta Tables
* Fabric Pipelines
* Semantic Models
* Power BI
* Yahoo Finance API
* Python

---

## Architecture

Yahoo Finance API

↓

Bronze Layer (market_raw)

↓

Silver Layer (market_clean)

↓

Gold Layer

* daily_price_summary
* daily_stock_performance
* sector_daily_performance
* momentum_signal
* volatility_signal
* volume_leaders

↓

Semantic Model

↓

Power BI Dashboard

---

## Medallion Architecture

### Bronze Layer

Raw stock market data ingested from Yahoo Finance.

Table:

* market_raw

Features:

* Raw historical data
* Rolling 1-year retention
* Duplicate prevention

---

### Silver Layer

Cleaned and standardized dataset.

Table:

* market_clean

Transformations:

* Data quality validation
* Column standardization
* Date handling
* Business-ready schema

---

### Gold Layer

Business-focused analytical tables.

#### daily_price_summary

Daily market-wide summary metrics.

#### daily_stock_performance

Stock-level daily returns and performance indicators.

#### sector_daily_performance

Sector-wise daily return analysis.

#### momentum_signal

Momentum-based BUY / SELL signals using moving averages.

#### volatility_signal

20-day rolling volatility calculation.

#### volume_leaders

Stocks with highest trading activity.

---

## Pipeline Orchestration

Fabric Pipeline executes the notebook automatically.

Features:

* Automated execution
* Incremental processing
* Duplicate prevention
* Rolling 1-year data retention

---

## Semantic Model

Implemented a Star Schema:

Dimensions:

* dim_date
* dim_stock

Facts:

* daily_price_summary
* daily_stock_performance
* sector_daily_performance
* momentum_signal
* volatility_signal
* volume_leaders

Relationships:

* One-to-Many
* Single Direction Filtering

---

## Dashboard Features

### Market Volume Trend

Tracks market activity over time.

### Sector Performance

Compares sector returns.

### Top Volume Leaders

Highlights heavily traded stocks.

### Momentum Signals

Displays BUY and SELL opportunities.

### Volatility Analysis

Measures stock volatility using a rolling 20-day window.

---

## Key Engineering Concepts Demonstrated

* Data Ingestion
* Incremental Processing
* Lakehouse Architecture
* Medallion Architecture
* Delta Tables
* PySpark Transformations
* Pipeline Orchestration
* Data Modeling
* Semantic Models
* Power BI Reporting

---

## Author

Akash Shaw

Data Engineering | Microsoft Fabric | PySpark | Power BI
