# Walmart-Black-Friday-Customer-Purchase-Behavior-Analysis
EDA on 550K-row retail transaction dataset — data profiling, missing value analysis, and IQR-based outlier detection with business-driven treatment decisions.
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1SabGn8d4HfQ84bWotM9Yc2Vc7HPdSP4P)

# Customer Purchase Pattern Analysis — Retail Transaction EDA

## 📌 Overview
Exploratory Data Analysis (EDA) on a retail transaction dataset (550,000+ records) 
to understand customer purchasing behavior, clean the data for downstream modeling, 
and surface business-relevant insights.

## 🎯 Problem Statement
[Add your 1-2 line business problem here — e.g., "Understand customer purchase 
patterns across demographics and product categories to support targeted marketing 
and inventory decisions."]

## 📊 Dataset
- **Rows:** 550,000+
- **Columns:** 10
- **Data types:** Mixed (categorical + numerical); categorical columns converted 
  to `category` dtype for memory optimization

## 🔍 Approach

### 1. Data Structure & Basic Metrics
- Profiled dataset shape, column types, and memory footprint
- Converted object-type categorical columns to `category` dtype
- Generated statistical summaries (`.describe()`) with business observations

### 2. Missing Value Treatment
- Checked for nulls across all columns — **zero missing values found**
- Validated using multiple methods (`.isnull().sum()`, heatmap visualization)

### 3. Outlier Detection & Treatment
- Applied IQR method to detect outliers in numerical columns
- **Age:** 36,606 outliers detected
- **Purchase:** 2,677 outliers detected (~0.49% of data)
- Visualized distributions using boxplots
- **Key decision:** Retained high-value `Purchase` outliers rather than removing 
  them — treated as legitimate high-value transactions rather than data errors, 
  preserving signal relevant to business analysis (e.g., premium customer behavior)

## 🛠️ Tools & Libraries
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Jupyter Notebook

## 📈 Key Insights
- [Add 2-3 bullet insights from your actual analysis — e.g., purchase trends by 
  age group, category, city tier, etc.]


