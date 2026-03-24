# Causal Analysis of the USAID IQPEP in Ethiopia

[cite_start]This repository contains the code, data, and final paper analyzing the causal impact of the USAID Improving Quality of Primary Education Program (IQPEP) in Ethiopia[cite: 1, 4]. 

[cite_start]While previous evaluations of this teacher-training program relied on descriptive statistics, this project conducts a formal causal inference analysis on the 2014 endline data to isolate the intervention's effect on Early Grade Reading Assessment (EGRA) comprehension scores for second and third graders[cite: 5, 6, 14].

## Repository Contents

* [cite_start]**`Causal Analysis USAID IQPEP Ethiopia.pdf`**: The final research paper detailing our methodology, assumptions, and findings[cite: 1].
* [cite_start]**`FinalCode.Rmd` / `FinalCode.html`**: The R Markdown code and compiled HTML containing all the data preprocessing, exploratory data analysis, and modeling[cite: 244].
* [cite_start]**`endline.csv`**: The 2014 endline dataset used for the analysis[cite: 42].
* **`EndlineDocumentation.pdf`**: A data dictionary explaining the variables included in the `endline.csv` dataset.

## Methodology

[cite_start]Leveraging the randomized assignment of the treatment at the school level, the analysis explores the data through multiple approaches[cite: 7, 101]:

1.  [cite_start]**School-Level Analysis**: Simple linear models aggregating outcomes to estimate the Average Treatment Effect (ATE)[cite: 7, 103].
2.  [cite_start]**Student-Level Analysis (Lin's Estimator)**: An OLS regression specification that interacts the treatment indicator with centered covariates to provide a robust ATE estimate[cite: 158, 159]. [cite_start]We used CR0 cluster-robust standard errors to account for the school-level randomization[cite: 152].
3.  [cite_start]**Heterogeneous Treatment Effects (Causal Forests)**: A non-parametric approach utilizing Causal Forests to locally residualize outcomes and isolate the causal effect, allowing us to test for Conditional Average Treatment Effects (CATE) across different student demographics[cite: 175, 177]. 

## Key Findings

* [cite_start]**Student-Level Impact**: Our student-level analysis utilizing Lin's estimator revealed a modest but statistically significant positive treatment effect on reading comprehension scores (ATE $\approx$ 0.189)[cite: 8, 169].
* [cite_start]**Heterogeneity**: The Causal Forest analysis confirmed the positive ATE but did not detect statistically significant heterogeneity[cite: 201, 204]. [cite_start]This indicates that the benefits of the IQPEP intervention were relatively uniform across the observed dimensions (such as gender, age, and language)[cite: 9, 207].
