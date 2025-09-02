# 🚕 TaxiTrips: Predictive Analysis of Taxi Tipping Behavior

## 🎯 Executive Summary

This project analyzes **R's preloaded taxi dataset** to predict passenger tipping behavior and examine variations across different taxi companies. Through comprehensive exploratory data analysis and logistic regression modeling, I discovered:

- **92.1%** of passengers tip their drivers
- **Significant variation in tip rate by company**: 5.1% to 13.1% non-tip rates
- **Distance and company** are the strongest predictors of tipping behavior

## 📊 Dataset Overview

<table>
<tr>
<td><strong>📍 Source</strong></td>
<td>R's built-in taxi dataset (modeldata package)</td>
</tr>
<tr>
<td><strong>📈 Size</strong></td>
<td>10,000 taxi rides across 4 months (Jan-Apr)</td>
</tr>
<tr>
<td><strong>🌆 Location</strong></td>
<td>Chicago taxi market</td>
</tr>
</table>

### 🔍 Key Variables

| Variable | Description | Key Stats |
|----------|-------------|-----------|
| **Tip** | Binary indicator (yes/no) | 92.1% tip rate |
| **Distance** | Trip distance in miles | Median: 1.78 miles, highly right-skewed 
| **Company** | 6 taxi companies + "other" category | 7 total categories |
| **Local** | Binary indication (local/not local) | 81.2% non-local, 18.8% local |
| **Day** | Day of week | All seven days |
| **Month** | Month | January through April |
| **Hour** | Hour | Most hours of day, except for 3:00 a.m. |

---
### 🎯 Feature Importance Analysis

Used **Likelihood Ratio Chi-Square** to rank predictive power of each variable:

| Rank | Variable | Chi-Square Score | Impact |
|------|----------|------------------|-----------|
| 🥇 | **Company** | 55.5 | Strongest predictor |
| 🥈 | **Distance** | 46.6 | Second strongest |
| 🥉 | **Local Status** | 23.5 | Moderate impact |
| 4️⃣ | **Day of Week** | 8.6 | Minor impact |
| 5️⃣ | **Month** | 7.4 | Minor impact |
| 6️⃣ | **Hour** | 0.5 | Weakest predictor |

### ⚙️ Modeling Strategy
- 🎯 **Primary Method**: Logistic Regression (optimal for binary classification)
- 🔄 **Models Used**: Lasso, Ridge, and traditional OLS regression
- 🏆 **Winner**: Traditional OLS model using all variables performed best
- 📈 **Evaluation**: AUC comparison and Likelihood Ratio Chi-Square analysis

## 🏆 Key Findings

### 🚕 Company Tipping Analysis**

**Significant variation exists across taxi companies:**

<div align="center">

| 🏢 Company | ❌ Non-Tip Rate | ✅ Tip Rate | 📊 Sample Size ||
|------------|----------------|-------------|----------------|-|
| **Chicago Independents** | **5.1%** | **94.9%** | 781 rides ||
| Sun Taxi | 6.1% | 93.9% | 1,382 rides ||
| City Service | 7.3% | 92.7% | 1,187 rides ||
| Other | 7.2% | 92.8% | 2,715 rides ||
| Taxicab Insurance | 7.5% | 92.5% | 1,231 rides ||
| Taxi Affiliation Services | 9.5% | 90.5% | 1,694 rides ||
| **Flash Cab** | **13.1%** | **86.9%** | 1,010 rides ||

</div>

### 👥 Passenger & Trip Patterns

<div align="center">

| 📊 Metric | 📈 Finding ||
|-----------|------------|-------------------|
| 🌍 **Customer Base** | 81.2% non-local passengers|
| 📅 **Peak Activity** | Thursday (19.6%) |
| 🗓️ **Seasonal Trends** | March (31.4%) & April (31.8%) |
| 📏 **Trip Distance** | Bimodal: <5 miles & ~16 miles ||

</div>

---
### 🏗️ Code Structure
- 📥 **Data Loading**: R's built-in taxi dataset from modeldata package
- 🔍 **Exploratory Analysis**: Comprehensive univariate and bivariate analysis
- 📊 **Statistical Testing**: Likelihood Ratio Chi-Square for feature ranking
- 🧠 **Modeling**: Logistic regression with multiple approaches
- ✅ **Validation**: AUC-based performance evaluation
---

## 📁 Repository Structure
```
🚕 TaxiTrips/
├── README.md                 #This documentation
├── Raw Code                  #The code used to generate the report
└── Taxi Analysis.pdf         #Complete analysis report
```
