# Heart Disease Risk Analysis

Data validation and exploratory data analysis (EDA) on the BRFSS 2015 Heart Disease Health Indicators dataset, identifying which health and demographic factors are most strongly linked to heart disease risk.

## Dataset
- **Source:** BRFSS 2015 Heart Disease Health Indicators dataset
- **Original size:** 253,680 records, 22 variables (health indicators, lifestyle habits, and demographics)
- **After removing 23,899 duplicate rows:** 229,781 clean records used for analysis
- **Target variable:** `HeartDiseaseorAttack`

## What I did

**1. Data Validation & Cleaning**
- Checked for duplicate records — found and removed **23,899 duplicates** (253,680 → 229,781 rows)
- Validated `BMI` values for invalid/non-positive entries — found **0 invalid values**
- Converted 19 categorical variables (e.g. `HighBP`, `Smoker`, `Diabetes`, `Sex`, `Age`, `Income`) to proper categorical dtype for accurate analysis
- Reviewed summary statistics for continuous variables (`BMI`, `MentHlth`, `PhysHlth`) to check distribution and outliers

**2. Exploratory Data Analysis & Visualization**
- Overall heart disease distribution (pie chart)
- BMI distribution (histogram)
- Correlation heatmap across continuous variables
- Heart disease rate broken out by age, sex, income, and education (bar charts)
- Percentage breakdown of heart disease prevalence across 6 key health risk factors
- A combined risk-score analysis showing disease rate against number of risk factors present

## Tools & Libraries
- Python
- Pandas (data cleaning, validation, aggregation)
- Matplotlib & Seaborn (visualization)

## Key Findings

- **Overall heart disease rate: 10.3%** (23,717 of 229,781 people)
- **Stroke history is the strongest single predictor:** 38.3% of people with a prior stroke had heart disease, vs. 9.0% of those without — a 29.3 percentage-point gap, the largest of any factor tested
- **Other strong health risk factors:**
  - Difficulty walking (`DiffWalk`): 23.2% vs. 7.4%
  - High blood pressure (`HighBP`): 17.0% vs. 4.7%
  - High cholesterol (`HighChol`): 16.4% vs. 5.6%
  - Smoking: 13.7% vs. 7.3%
  - Heavy alcohol consumption: 6.1% vs. 10.6% (notably *lower* in this group — likely reflects a younger/healthier sub-population rather than a protective effect)
- **Combined risk score:** disease rate rises sharply with each additional risk factor present — from **1.7%** with 0 risk factors to **49.2%** with all 6, a roughly 29x increase
- **Age:** rate climbs steadily from 0.5% in the youngest group to **24.6%** in the oldest
- **Sex:** males had a notably higher rate than females — 13.4% vs. 7.9%
- **Income & Education:** heart disease rate falls consistently as both income and education level rise (from ~15.9-18.7% at the lowest income levels to 6.2% at the highest; from ~19.3% at lower education levels to 7.9% at the highest) — suggesting the pattern isn't purely a health/genetics story but also has a socioeconomic dimension

## Notebook
See [`heart_disease_analysis.ipynb`](./heart_disease_analysis.ipynb) for the full analysis.
