# TechNex-1BRC-Round-2

A scalable data processing and machine learning pipeline built using **Apache Spark**, designed to handle large-scale agricultural datasets efficiently. This project focuses on data cleaning, statistical analysis, anomaly detection, and predictive modeling using distributed computing — with optional GPU acceleration.

---

## Project Overview

This repository contains a Spark-based data processing pipeline that:

- Efficiently handles **large CSV datasets**
- Performs **data cleaning, filtering, and statistical analysis**
- Builds a **machine learning model** using Spark ML
- Supports **GPU acceleration** (via RAPIDS, if available)
- Generates **visual insights** through plotting

> **Note:**  
> The original `data.csv` file is **not included** in this repository due to its large size.

---

## Features

### System & Environment Setup
- Detects availability of **CUDA-enabled GPUs**
- Configures Spark to use:
  - **6 CPU cores**
  - **~10 GB total memory** (5 GB each for driver and executor)
- Applies **GPU-specific Spark configurations** if RAPIDS support is detected

---

### Data Processing Pipeline
- Loads a **large CSV file** using an explicitly defined schema  
- Filters anomalous values:
  - Keeps rows where `soil_moisture` is within **±3 standard deviations**
- Sorts data using multiple relevant columns  
- Applies additional logical filtering  

---

### Statistical Analysis
Computes descriptive statistics for:
- `carbon_percent`
- `nitrogen_percent`

Statistics include:
- Mean  
- Median  
- Standard Deviation  
- Q1 (25th percentile)  
- Q3 (75th percentile)  

---

### Data Imputation
- Interpolates missing values:

