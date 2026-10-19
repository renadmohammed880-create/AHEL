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
