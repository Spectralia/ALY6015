# Final Project Proposal / Dataset Selection (Module 2)

**Course:** ALY6015 Intermediate Analytics  
**Dataset:** `BankChurners.csv`  
**Group members:**  
- Ishu  
- Qiduo  
- Wen   

## 1) Project goal (what we want to solve)
Customer churn is expensive for banks. The goal of this project is to understand **which customer behaviors and account features are linked to attrition** and to build a simple, interpretable model to **predict the chance that a customer will churn**.

## 2) Dataset description (why this data works)
`BankChurners.csv` includes customer demographics (age, gender, income group, education, marital status), account details (credit limit, utilization ratio), and behavior measures (transactions, inactivity, contacts). It also includes the churn label:

- **Target variable:** `Attrition_Flag` (existing customer vs. attrited customer)

This dataset is a good fit because it has a clear outcome, many reasonable predictors, and enough rows to support modeling and validation.

**Important note on data use:** The file contains two columns that look like model outputs:  
`Naive_Bayes_Classifier_..._1` and `Naive_Bayes_Classifier_..._2`.  
We will **remove these columns** to avoid information leakage. We will also treat `CLIENTNUM` as an ID and **not use it as a predictor**.

## 3) Questions we plan to answer
1. Which features are most related to churn? For example: inactivity, number of contacts, transaction count/amount, credit utilization, and relationship count.
2. How well can we predict churn using a small set of variables that are easy to explain?
3. Are there clear customer segments (by age, income group, card type, activity level) with higher churn risk?
4. If churn risk is high, what practical actions could the bank take based on the drivers we find?

## 4) Methods we will use (minimum of 2)
We will use at least two methods taught in the course:

1. **Exploratory Data Analysis (EDA) + descriptive statistics**  
   - churn rate overall and by groups (gender, card category, income category, education)  
   - summary tables and plots (histograms/boxplots) for key numeric variables  
   - correlation checks among numeric predictors

2. **Logistic regression (GLM) for churn prediction**  
   - model `Attrition_Flag` as a function of customer behavior and account variables  
   - interpret odds ratios to explain key drivers  
   - evaluate performance with a holdout set (accuracy, precision/recall, confusion matrix)

If time allows, we will also compare logistic regression with a simpler baseline rule (or a second model) to show improvement and discuss trade-offs between accuracy and interpretability.

## 5) Planned data preparation
- Remove leakage columns (`Naive_Bayes_Classifier_*`) and the ID column (`CLIENTNUM`) from modeling.
- Check missing values (the file appears clean, but we will verify).
- Encode categorical variables (one-hot or grouped levels if needed).
- Standardize/scale numeric variables if helpful for model stability.

## 6) Expected output
We will deliver a final report that explains the data, the modeling steps, and the results in plain language, with clear charts and a short list of recommendations based on the main churn drivers.

