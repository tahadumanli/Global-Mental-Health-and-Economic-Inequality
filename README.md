1. Motivation

Mental health issues such as depression and anxiety have become major global concerns, yet their relationship with economic inequality remains insufficiently quantified.
This project aims to uncover how socio-economic factors—such as income inequality, GDP per capita, and regional disparities—correlate with mental health disorder prevalence worldwide.
By combining two large-scale open datasets, this study seeks to reveal patterns that highlight how economic well-being influences psychological health outcomes across countries.

2. Data Sources
(a) Mental Health Dataset
Source: Uncover Global Trends in Mental Health Disorder – Kaggle
Contains data on global mental health disorder prevalence rates across multiple years.
Includes variables such as country, disorder type, percentage affected, and year.

(b) Economic Inequality Dataset
Source: Global Economic Inequality – Kaggle
Provides global income and wealth inequality indicators.
Features include Gini coefficient, top 10% income share, GDP per capita, and region.

(c) Enrichment Plan
To strengthen analysis:
Optionally add education, unemployment, or internet access data from the World Bank or Our World in Data.
Use ISO country codes to merge datasets.

3. Data Collection and Preparation
Download CSVs from both Kaggle datasets.
Inspect and clean missing or inconsistent entries.
Merge datasets by country and year.
Normalize numeric fields (e.g., GDP per capita, Gini index) for comparison.
Save reduced versions for faster processing (filtering by year ≥ 2000 or selected regions).

4. Analysis Plan
Exploratory Data Analysis (EDA)
Compute descriptive statistics for mental health indicators and economic measures.
Visualize distributions and trends across regions and years.
Detect outliers and correlations between inequality and mental disorder rates.
Hypothesis Testing
H₀: Economic inequality has no relationship with mental health disorder rates.
H₁: Economic inequality positively correlates with mental health disorder rates.
Perform correlation and ANOVA tests.
Machine Learning Stage
Regression models (Linear, Ridge, Random Forest) to predict disorder prevalence based on GDP, inequality, and region.
Clustering (K-means) to group countries by socio-economic and mental health profiles.
Visualization: Heatmaps, scatter plots, and choropleth world maps with Plotly.

5. Expected Findings
Countries with higher Gini coefficients and lower GDP per capita will likely show higher mental disorder prevalence.
Economic inequality and unemployment may act as stronger predictors than income level alone.
Clusters will distinguish high-income, low-inequality nations from economically strained, high-stress regions.

6. Limitations and Future Work
Missing data for some countries and years.
Correlation does not imply causation; results will be interpreted accordingly.
Future extensions: time-series forecasting and inclusion of healthcare spending or education indices.

7. Tools and Environment
Languages: Python 3.x
Libraries: pandas, numpy, matplotlib, seaborn, plotly, scikit-learn
Environment: Jupyter Notebook / VSCode
Version Control: Git & GitHub
Dependencies: defined in requirements.txt

8. Project Timeline
Date	Milestone
31 Oct	Submit project proposal (GitHub repo with README.md)
28 Nov	Complete data collection, cleaning, EDA, and hypothesis testing
02 Jan	Apply ML models and produce analytical visuals
09 Jan (23:59)	Final submission (report, visuals, and documentation)
