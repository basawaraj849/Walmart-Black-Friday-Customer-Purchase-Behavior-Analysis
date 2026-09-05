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

## 7. Final Insights

*(Use this structure — fill in the exact numbers you get when you run the notebook.)*

- **Gender:** Male average spend per transaction is higher than female, and the 90/95/99% confidence intervals do not overlap — this is a statistically real difference, not noise.
- **Marital Status:** [State whether CIs overlapped and what that implies.]
- **Age:** [State which age groups are distinguishable from each other and which aren't — usually the smaller-sample groups like 0-17 and 55+ have wider, less precise intervals.]
- **Distribution shape:** Purchase amount is right-skewed with outliers above ~₹20k, but thanks to the CLT, the *sampling distribution of the mean* is approximately Normal for reasonably sized samples (n≥300ish), which is what makes the confidence-interval approach valid here despite the skew in the raw data.
- **Product mix:** Categories 1, 5, and 8 drive transaction *volume*, but Category 10 has by far the highest *average* transaction value — volume and value leaders are not the same categories.
- **Confidence width tradeoff:** Moving from 90% → 99% confidence widens every interval (more certainty requires a wider net) — but at this sample size the widening is small relative to the actual gap between male/female means, so the conclusion holds at all three levels.


