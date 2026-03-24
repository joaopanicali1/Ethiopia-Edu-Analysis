# Causal Analysis of the USAID IQPEP in Ethiopia

This repository contains the code, data, and final paper analyzing the causal impact of the USAID Improving Quality of Primary Education Program (IQPEP) in Ethiopia. 

While previous evaluations of this teacher-training program relied on descriptive statistics, this project conducts a formal causal inference analysis on the 2014 endline data to isolate the intervention's effect on Early Grade Reading Assessment (EGRA) comprehension scores for second and third graders.

## Repository Contents

* **`Causal Analysis USAID IQPEP Ethiopia.pdf`**: The final research paper detailing our methodology, assumptions, and findings.
* **`FinalCode.Rmd` / `FinalCode.html`**: The R Markdown code and compiled HTML containing all the data preprocessing, exploratory data analysis, and modeling.
* **`endline.csv`**: The 2014 endline dataset used for the analysis.
* **`EndlineDocumentation.pdf`**: A data dictionary explaining the variables included in the `endline.csv` dataset.

## Methodology

Leveraging the randomized assignment of the treatment at the school level, the analysis explores the data through multiple approaches:

1.  **School-Level Analysis**: Simple linear models aggregating outcomes to estimate the Average Treatment Effect (ATE).
2.  **Student-Level Analysis (Lin's Estimator)**: An OLS regression specification that interacts the treatment indicator with centered covariates to provide a robust ATE estimate. We used CR0 cluster-robust standard errors to account for the school-level randomization.
3.  **Heterogeneous Treatment Effects (Causal Forests)**: A non-parametric approach utilizing Causal Forests to locally residualize outcomes and isolate the causal effect, allowing us to test for Conditional Average Treatment Effects (CATE) across different student demographics. 

## Key Findings

* **Student-Level Impact**: Our student-level analysis utilizing Lin's estimator revealed a modest but statistically significant positive treatment effect on reading comprehension scores (ATE $\approx$ 0.189).
* **Heterogeneity**: The Causal Forest analysis confirmed the positive ATE but did not detect statistically significant heterogeneity. This indicates that the benefits of the IQPEP intervention were relatively uniform across the observed dimensions (such as gender, age, and language).
