# 🏦 Atliqo Bank – Credit Card Targeting & A/B Testing Strategy

## 📌 Problem Statement

Atliqo Bank, a new entrant in the Indian banking sector, is preparing to launch a credit card in a competitive market dominated by players like HDFC, ICICI, and Axis Bank. To ensure a successful launch, the project is divided into two critical phases:

- **Phase 1**: Identify the target segment for the credit card using customer transaction and profile data.
- **Phase 2**: Conduct A/B testing to evaluate the impact of the new credit card on customer spending behavior.

---

## 🧰 Technologies Used

- **Python**
- **Pandas, NumPy** – Data Cleaning & Manipulation  
- **Matplotlib, Seaborn** – Data Visualization  
- **Statsmodels, Scipy** – Statistical Testing  
- **Jupyter Notebook** – Analysis Environment  

---

## 📊 Phase 1 – Target Market Identification

### 🔧 Data Cleaning

- Handled null values using **median imputation**.
- Removed duplicate records across all tables.
- Detected and treated outliers using:
  - **±3 Standard Deviation Method**
  - **IQR Method**
  - **Boxplot Visualization**
- Replaced outliers with **median** (preferred over mean due to outlier sensitivity).

### 📈 Exploratory Data Analysis (EDA)

- Performed univariate and bivariate analysis on key features.
- Analyzed relationships between **categorical variables** and **income**.
- Visualized correlations using:
  - **Bar charts**
  - **Scatter plots**
  - **Box plots**
  - **Heatmaps**

### 💡 Final Insights

- **Target Segment Identified**: Customers aged **18–25**
  - Represent ~26% of total customer base.
  - Have **low annual income** (less than ₹50,000).
  - Show **limited credit history** with low scores and limits.
  - Exhibit **low credit card usage** compared to other segments.
  - Most frequent purchases are in:
    - **Electronics**
    - **Fashion & Apparel**
    - **Beauty & Personal Care**

---

## 🔬 Phase 2 – A/B Testing of New Credit Card Campaign

In this phase, we evaluated whether the newly designed credit card had a statistically significant effect on transaction behavior using A/B testing.

### ✅ What Was Done

1. **Sample Size Estimation**:
   - Used the `statsmodels` power analysis tool to calculate the required sample size for detecting different effect sizes (0.1 to 1.0) with 80% power and 5% significance level.

2. **Data Loading**:
   - Loaded a CSV file `avg_transactions_after_campaign.csv` containing average transaction amounts for:
     - **Control Group** (did not receive the new card)
     - **Test Group** (received the new card)

3. **Distribution Analysis**:
   - Plotted histograms with KDE for both control and test group average transaction amounts to visually inspect distribution shapes.

4. **Descriptive Statistics**:
   - Calculated mean and standard deviation for both groups.

5. **Manual Z-Score Calculation**:
   - Computed the Z-score for difference in means.
   - Compared it to the critical Z-value (1.645 for one-tailed test at 5% significance level).
   - Calculated the corresponding p-value.

6. **Z-Test Using `statsmodels`**:
   - Performed a two-sample Z-test (`sm.stats.ztest`) to validate the results programmatically.
   - Direction: Test group > Control group (right-tailed test).

7. **Conclusion**:
   - The p-value was **less than 0.05**, so we **reject the null hypothesis**.
   - There is **statistical evidence** that the test group (who got the new card) had higher average transactions than the control group.

---

## ✅ Final Outcome

- **Phase 1** revealed a focused and data-driven target customer group aged 18–25.
- **Phase 2** validated the card offering with a statistically significant increase in transactions for the test group.
- These findings support a confident rollout of the new credit card, backed by both customer insights and experimental evidence.

---
