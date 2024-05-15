# Multivariate Analysis of Colorectal Cancer Patient Data

## Introduction
This repository contains R code for performing multivariate analysis of colorectal cancer (CRC) patient data. The analysis includes various clinical variables such as patient age, Dukes stage, gender, adjuvant radiotherapy, and adjuvant chemotherapy, along with clustering based on gene expression levels.

## Data
Two datasets are provided:
- `AssignII_SS24.txt`: Clinical data of CRC patients including age, gender, Dukes stage, adjuvant radiotherapy, adjuvant chemotherapy, disease-free survival (DFS), and DFS events.
- `AssignIIGE_SS24.txt`: Gene expression data for the same set of patients, pre-processed and log2 transformed.

## Background

The dataset (`AssignI_SS24.txt`) comprises colorectal cancer patients who underwent surgery to remove their tumors. It includes the following variables:

- Age at Diagnosis (Years)
- Dukes Stage: A to D (development/progression of disease)
- Gender: Male or Female
- Location: Left, Right, Colon, or Rectum
- DFS: Disease-free survival, months (survival without the disease returning)
- DFSevent: 0 or 1 (with 1 = event)
- AdjRadio: If the patient received radiotherapy
- AdjChem: If the patient received chemotherapy

## Analysis
## Question 1: Data Summary

The dataset summary is as follows:

- Number of patients: 247
- Mean age at diagnosis: [Mean Age]
- Standard deviation of age at diagnosis: [SD Age]
- Gender distribution: [Gender Table]
- Location distribution: [Location Table]
- Dukes Stage distribution: [Dukes Stage Table]
- Average disease-free survival: [Mean DFS]
- Standard deviation of disease-free survival: [SD DFS]
- Number of missing values for each variable: [Missing Values]

## Question 2a: Age at Diagnosis vs. Tumour Location

- We performed the Kruskal-Wallis test and found a significant difference in age at diagnosis among tumor locations (p-value = [P-value]).
- Pairwise comparisons using Dunn's test revealed [Dunn's Test Results].
  
## Question 2b: Age at Diagnosis vs. Dukes Stages

- The Kruskal-Wallis test showed no significant difference in age at diagnosis among different Dukes stages (p-value = [P-value]).
- Pairwise comparisons indicated [Pairwise Comparison Results].

## Question 3a: Gender vs. Dukes Stages

- Chi-squared test results indicated no significant association between gender and Dukes stages (p-value = [P-value]).
  
## Question 3b: Age at Diagnosis by Gender

- The Wilcoxon rank-sum test showed a significant difference in age at diagnosis between male and female patients (p-value = [P-value]).

## Question 3c: Age at Diagnosis by Gender within Dukes Stages

- Wilcoxon rank-sum tests suggested differences in age at diagnosis between genders within certain Dukes stages.

## Question 4: Duke's Staging vs. Chemotherapy

- Fisher's exact test confirmed a significant association between Duke's staging and chemotherapy (p-value < 0.001).

## Question 5a: Disease-Free Survival by Dukes Stages

- Median disease-free survival:
  - Dukes Stage A: 56.5 months (95% CI: 44.2 - 67.19)
  - Dukes Stage B: 44.8 months (95% CI: 38.0 - 52.14)
  - Dukes Stage C: 54.9 months (95% CI: 47.8 - 64.33)

## Question 5b: Association between Duke's Staging and Disease-Free Survival

- The log-rank test showed a significant association between Duke's staging and disease-free survival (p-value = [P-value]).

## Question 6:
- Selecting genes based on the interquartile range (IQR) of their expression levels.
- Performing hierarchical clustering using the Euclidean distance and Ward linkage method.
- Plotting the dendrogram and dividing the dataset into two clusters.

## Question 7:
- Investigating relationships between non-survival variables (e.g., location, Dukes stage, age, gender, adjuvant treatments) and the two clusters identified in Question 6.

## Question 8:
- Plotting survival curves corresponding to the two clusters.
- Summarising and explaining the results.

## Question 9:
- Performing univariate analysis for each clinical variable with respect to disease-free survival.
- Calculating the power of each univariate test.

## Question 10:
- Performing multivariate analysis combining each clinical variable with the cluster variable.
- Determining the best model for predicting patient survival based on AIC and McFadden pseudo-R-squared values.

## Usage
1. Load the provided datasets (`AssignII_SS24.txt` and `AssignIIGE_SS24.txt`) into R.
2. Run the R code provided in the repository for each analysis question.
3. Interpret the results to gain insights into the relationships between clinical variables, gene expression, and patient survival in CRC.

## Dependencies
- R packages used include `genefilter`, `survival`, `survminer`, `ggplot2`, `questionr`, `AICmodavg`, and `pscl`.

```
