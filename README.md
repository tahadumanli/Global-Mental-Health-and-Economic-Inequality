# Global Mental Health and Economic Inequality

## 1. Motivation
Mental health issues such as depression and anxiety have become major global concerns, yet their relationship with economic inequality remains insufficiently quantified.  
This project aims to uncover how socio-economic factors—such as income inequality, GDP per capita, and regional disparities—correlate with mental health disorder prevalence worldwide.  
By combining two large-scale open datasets, this study seeks to reveal patterns that highlight how economic well-being influences psychological health outcomes across countries.

## 2. Data Sources

### (a) Mental Health Dataset
**Source:** Uncover Global Trends in Mental Health Disorder – Kaggle  
Contains data on global mental health disorder prevalence rates across multiple years.  
Includes variables such as country, disorder type, percentage affected, and year.  
https://www.kaggle.com/datasets/thedevastator/uncover-global-trends-in-mental-health-disorder

### (b) Economic Inequality Dataset
**Source:** Global Economic Inequality – Kaggle  
Provides global income and wealth inequality indicators.  
Features include Gini coefficient, top 10% income share, GDP per capita, and region.  
https://www.kaggle.com/datasets/mathurinache/global-economic-inequality

### (c) Enrichment Plan
To strengthen analysis:  
- Optionally add education, unemployment, or internet access data from the World Bank or Our World in Data.  
- Use ISO country codes to merge datasets.

## 3. Data Collection and Preparation
- Download CSVs from both Kaggle datasets.  
- Inspect and clean missing or inconsistent entries.  
- Merge datasets by country and year.  
- Normalize numeric fields (e.g., GDP per capita, Gini index) for comparison.  
- Save reduced versions for faster processing (filtering by year ≥ 2000 or selected regions).

## 4. Analysis Plan

### Exploratory Data Analysis (EDA)
- Compute descriptive statistics for mental health indicators and economic measures.  
- Visualize distributions and trends across regions and years.  
- Detect outliers and correlations between inequality and mental disorder rates.

### Hypothesis Testing
**H₀:** Economic inequality has no relationship with mental health disorder rates.  
**H₁:** Economic inequality positively correlates with mental health disorder rates.  
Perform correlation and ANOVA tests.

### Machine Learning Stage
- Regression models (Linear, Ridge, Random Forest) to predict disorder prevalence based on GDP, inequality, and region.  
- Clustering (K-means) to group countries by socio-economic and mental health profiles.  
- Visualization: Heatmaps, scatter plots, and choropleth world maps with Plotly.

## 5. Expected Findings
- Countries with higher Gini coefficients and lower GDP per capita will likely show higher mental disorder prevalence.  
- Economic inequality and unemployment may act as stronger predictors than income level alone.  
- Clusters will distinguish high-income, low-inequality nations from economically strained, high-stress regions.

## 6. Limitations and Future Work
- Missing data for some countries and years.  
- Correlation does not imply causation; results will be interpreted accordingly.  
- Future extensions: time-series forecasting and inclusion of healthcare spending or education indices.

## 7. Tools and Environment
**Languages:** Python 3.x  
**Libraries:** pandas, numpy, matplotlib, seaborn, plotly, scikit-learn  
**Environment:** Jupyter Notebook / VSCode  
**Version Control:** Git & GitHub  
**Dependencies:** defined in requirements.txt

## 8. Project Timeline
| Date          | Milestone                                                      |
|---------------|----------------------------------------------------------------|
| 31 Oct        | Submit project proposal (GitHub repo with README.md)           |
| 28 Nov        | Complete data collection, cleaning, EDA, and hypothesis testing |
| 02 Jan        | Apply ML models and produce analytical visuals                 |
| 09 Jan (23:59)| Final submission (report, visuals, and documentation)          |



**Phase 2: Exploratory Data Analysis, Enrichment & Hypothesis Testing**
=======================================================================

This phase focuses on expanding the project beyond GDP-only analysis by introducing new datasets, improving data quality, and performing statistical tests to evaluate relationships between economic indicators and global depression prevalence.

* * * * *

**1\. What Was Added in Phase 2**
---------------------------------

In Phase 1, the project relied solely on:

-   Depression prevalence (%)

-   GDP per capita

This scope was too limited to capture the influence of economic inequality.

To address this limitation, Phase 2 enriches the dataset with two additional Kaggle sources:

### **(a) Gini Index by Country**
https://www.kaggle.com/datasets/ulrikthygepedersen/gini-index-per-country

A dataset measuring income inequality

-   Added variable: `gini_index`

### **(b) Global Income Inequality (OWID)**
https://www.kaggle.com/datasets/georgehanyfouad/global-income-inequality

A dataset providing a broader set of inequality and income distribution indicators:

-   `gini_index_owid`

-   `avg_income_usd`

-   `top10_share`

-   `bottom10_share`

-   `income_group`

**Reason for enrichment:**\
GDP alone does not reflect inequality or economic disparities. Additional socio-economic variables enable more comprehensive analysis of whether inequality influences depression.

* * * * *

**2\. What Was Done in Phase 2**
--------------------------------

Phase 2 consisted of three main tasks:

* * * * *

### **(1) Data Cleaning & Integration**

-   Numeric fields (GDP, income, Gini) were cleaned

-   Country/year formats were standardized

-   All datasets were merged using `country` + `year`

-   A full combined dataset was created:

`mental_econ_inequality_full.csv`

**Final variables include:**

-   Depression prevalence

-   GDP per capita

-   Two Gini indices

-   Income shares (top/bottom 10%)

-   Average income

-   Population

-   Income group classification

* * * * *

### **(2) Visual Exploratory Analysis**

Multiple visual analyses were performed:

#### **a) GDP vs Depression**

- This plot shows a generally negative trend between GDP per capita and depression rates, indicating that wealthier countries tend to have lower levels of depression. However, the dispersion of points implies that economic prosperity does not guarantee better mental health outcomes.

-   Displays a very weak positive trend

-   Higher wealth does not correspond to lower depression

#### **b) Gini Index vs Depression**

-  The scatter plot illustrates the relationship between income inequality (measured by the Gini Index) and depression prevalence across countries. While there is a visible upward tendency—suggesting that countries with higher income inequality tend to have higher depression rates—the relationship is not strictly linear. The spread of points indicates substantial variability, meaning that income inequality alone does not fully explain depression prevalence.

-   Both Gini datasets show no strong patterns

-   Points are widely scattered

-   No visible linear relationship

#### **c) Income Share vs Depression**

-  The visualization suggests that countries where income is more concentrated within a smaller group tend to exhibit higher depression rates. Although the relationship is not perfectly linear, the overall trend indicates that unequal income distribution is associated with worse mental health outcomes.

-   Top 10% share → no relationship

-   Bottom 10% share → no relationship

-   Average income → no relationship

**Visual Conclusion:**\
Economic inequality indicators do not exhibit meaningful visual correlation with depression levels.

* * * * *

**3\. Hypothesis Testing**
--------------------------

A set of statistical tests was conducted to evaluate associations between economic indicators and depression prevalence.

* * * * *

### **H1 --- Correlation Between GDP per Capita and Depression**


**Null Hypothesis (H₀):** GDP per capita has no statistically significant relationship with depression rate.

**Alternative Hypothesis (H₁):** GDP per capita has a statistically significant relationship with depression rate.

**Test:** Pearson correlation

**Result:**

-   r ≈ **+0.14**

-   p ≪ 0.001

**Desicion**
Since the p-value is smaller than 0.05, we reject the null hypothesis.

**Conclusion:**\
There is a statistically significant but very weak positive relationship between GDP per capita and depression prevalence. Although higher GDP is associated with slightly higher depression rates, the effect size is minimal, indicating that GDP per capita does not meaningfully predict depression prevalence on its own.
* * * * *

### **H2 --- Correlation Between Gini Index (Dataset 1) and Depression**

**Null Hypothesis (H₀):** There is no statistically significant relationship between the Gini Index and depression prevalence.

**Alternative Hypothesis (H₁):** There is a statistically significant relationship between the Gini Index and depression prevalence.

**Test:** Pearson correlation

**Result:**

-   r ≈ **--0.27**

-   p ≪ 0.001

**Decision:** Since the p-value is less than 0.05, we reject the null hypothesis.

**Conclusion:**\
There is a statistically significant but weak negative relationship between the Gini Index and depression prevalence. Although the correlation is statistically significant, its small magnitude indicates that the Gini Index does not meaningfully explain variations in depression prevalence on its own.

* * * * *

### **H3 --- Correlation Between OWID Gini Index and Depression**

**Null Hypothesis (H₀):** There is no statistically significant relationship between the OWID Gini Index and depression prevalence.

**Alternative Hypothesis (H₁):** There is a statistically significant relationship between the OWID Gini Index and depression prevalence.

**Test:** Pearson correlation

**Result:**

-   r ≈ **--0.006**

-   p ≈ 0.91

**Decision:** Since the p-value is greater than 0.05, we fail to reject the null hypothesis.

**Conclusion:**\
There is no statistically significant relationship between the OWID Gini Index and depression prevalence. The near-zero correlation coefficient indicates that this measure of income inequality does not capture any meaningful association with depression rates in the analyzed data.
* * * * *

### **H4 --- Correlation Between Income Distribution Metrics and Depression**

**Null Hypothesis (H₀):** There is no statistically significant relationship between income distribution metrics (top 10% income share, bottom 10% income share, and average income) and depression prevalence.

**Alternative Hypothesis (H₁):** At least one income distribution metric has a statistically significant relationship with depression prevalence.

**Metrics Tested:**

-   Top 10% income share

-   Bottom 10% income share

-   Average income (USD)

**Results:**

-   All correlations: |r| < **0.12**

-   p-values high

**Decision:** Since all p-values are greater than 0.05, we fail to reject the null hypothesis.


**Conclusion:**\
Income distribution metrics, including top and bottom income shares and average income, do not show a statistically significant relationship with depression prevalence. The very small correlation coefficients indicate that these variables do not meaningfully explain variations in depression rates across countries.

* * * * *

### **H5 --- Mean Difference Between Low- and High-Inequality Countries**

**Null Hypothesis (H₀):** There is no difference in mean depression prevalence between low-inequality and high-inequality countries.

**Alternative Hypothesis (H₁):** There is a statistically significant difference in mean depression prevalence between low-inequality and high-inequality countries.

**Dataset:** OWID Gini\
**Test:** Two-sample t-test

**Results:**

-   t = **0.069**

-   p = **0.944**

-   Means nearly identical

**Decision:** Since the p-value is greater than 0.05, we fail to reject the null hypothesis.

**Conclusion:**\
There is no statistically significant difference in average depression rates between low-inequality and high-inequality countries. The nearly identical group means and extremely small t-statistic indicate that inequality level, as measured here, does not lead to detectable group-level differences in depression prevalence.

* * * * *

**3\. What Was Found (Summary)**
--------------------------------

✔ Depression rates do not meaningfully correlate with:
-   GDP
-   Gini inequality
-   Top 10% income share

-   Bottom 10% income share

-   Average income

✔ Inequality levels (low vs high) show no difference in depression

✔ GDP explains almost none of the variation in depression rates\
(R² ≈ 0.01--0.02)

✔ Both visualizations and hypothesis tests confirm:\
**Economic inequality alone does not explain global depression prevalence.**

✔ Mental health patterns appear more influenced by non-economic factors such as:

-   Cultural context

-   Reporting accuracy and stigma

-   Access to healthcare

-   Social instability

-   Demographic differences

* * * * *

**4\. Phase 2 Conclusion**
--------------------------

Phase 2 shows that:

-   Economic indicators, including multiple inequality metrics, exhibit very weak or nonexistent relationships with depression.

-   The enriched socio-economic dataset does not change the overall conclusion.

-   Mental health variation cannot be understood using economic data alone.

Phase 3 will investigate whether multivariate and non-linear models capture deeper patterns.
