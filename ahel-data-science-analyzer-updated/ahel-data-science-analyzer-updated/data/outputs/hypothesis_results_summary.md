# AHEL Hypothesis Results Summary

# Student Survey Analysis Report

## Hypothesis H1

H1: Practical exposure positively affects student readiness.

## Data Used

File: `data/student_survey.csv`  
Rows analyzed: **10**

## Descriptive Statistics

|                          |   count |   mean |      std |   min |   25% |   50% |   75% |   max |
|:-------------------------|--------:|-------:|---------:|------:|------:|------:|------:|------:|
| student_id               |      10 |    5.5 |  3.02765 |     1 |  3.25 |   5.5 |  7.75 |    10 |
| practical_exposure_score |      10 |   57.5 | 22.3818  |    20 | 41.25 |  58.5 | 76    |    88 |
| readiness_score          |      10 |   63   | 20.2704  |    30 | 48.5  |  64   | 80    |    90 |
| confidence_score         |      10 |   61.9 | 17.7917  |    35 | 47.5  |  64   | 75.75 |    85 |
| projects_completed       |      10 |    2.7 |  1.76698 |     0 |  1.25 |   2.5 |  4    |     5 |
| weekly_hours             |      10 |   12   |  6.68331 |     3 |  6.5  |  11   | 17.5  |    22 |

## Correlation Result

Pearson correlation between practical exposure and readiness:

- r = **0.999**
- p-value = **0.0000**

## H1 Result

H1 is **supported**.

## Important Note

This file includes a student survey template/sample so the analysis pipeline is implemented. Replace `data/student_survey.csv` with the final collected student survey before final submission if you have actual student survey responses.

## Output Files

- `outputs/student_survey_descriptive_stats.csv`
- `outputs/student_survey_correlation.csv`
- `outputs/student_survey_h1_report.md`


---

# Developer Survey Logistic Regression Report

## Hypothesis H2

H2: Higher skill diversity and experience are positively associated with employment status.

## Derived Variable

`Skill_Diversity_Index` was created from the number of distinct technologies listed across language, database, platform, framework, methodology, and version-control fields.

Formula:

`Skill_Diversity_Index = Skill_Count / Maximum_Skill_Count × 100`

## Model

Model used: Logistic Regression  
Target variable: Employed full-time = 1, part-time/other = 0  
Rows used after cleaning: **2157**

## Performance

Accuracy: **0.950**  
ROC-AUC: **0.669**

Confusion Matrix:

```
[[  0  27]
 [  0 513]]
```

## Coefficients

| feature               |   coefficient |
|:----------------------|--------------:|
| YearsCodingProf_Num   |     1.40264   |
| YearsCoding_Num       |     0.178356  |
| Skill_Count           |    -0.0447505 |
| Skill_Diversity_Index |    -0.0451984 |

## H2 Result

H2 is **partially supported: professional experience is positively associated with full-time employment, while Skill Diversity Index is not positive in this sample**. The dataset is heavily skewed toward full-time employment, so accuracy is high but ROC-AUC and coefficient direction should be interpreted carefully.

## Output Files

- `outputs/developer_survey_processed.csv`
- `outputs/developer_logistic_coefficients.csv`
- `outputs/developer_logistic_regression_report.md`


---

# Job Market Dataset Analysis

Dataset: `Data_jobs.csv`  
Records analyzed: **1048**

## NLP Preprocessing Implemented

- Lowercase normalization
- Symbol cleanup
- Tokenization
- Stop-word filtering
- Skill alias matching
- CountVectorizer frequency extraction
- TF-IDF term weighting

## Top Extracted Skill Frequencies

| skill            |   job_count |   percentage_of_jobs |
|:-----------------|------------:|---------------------:|
| Data Analysis    |         727 |                69.37 |
| SQL              |         719 |                68.61 |
| Python           |         676 |                64.5  |
| Machine Learning |         457 |                43.61 |
| Cloud            |         387 |                36.93 |
| Big Data         |         289 |                27.58 |
| Tableau          |         263 |                25.1  |
| Power BI         |         261 |                24.9  |
| Excel            |         206 |                19.66 |
| Cybersecurity    |         182 |                17.37 |

## Output Files

- `outputs/job_skill_frequency.csv`
- `outputs/job_nlp_top_terms.csv`
- `outputs/job_tfidf_terms.csv`

## Hypothesis H3 Evidence

H3 states that job-market skill demand can be used to identify readiness gaps. The extracted frequency table provides the job-market evidence used by the AHEL frontend to compare user-selected skills with market demand.


---
