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
