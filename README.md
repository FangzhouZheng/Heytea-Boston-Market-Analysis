# HEYTEA Boston Market: Promotion A/B Test & Customer Experience Analysis

## Project Overview

This academic survey project examines consumer responses to two promotional offers in the context of HEYTEA's Boston market: **Buy One, Get One Free (BOGO)** and a **free canvas bag giveaway**. It also explores customer satisfaction, promotional recommendation intentions, and factors associated with the in-store experience.

The project is an **independent academic analysis**, not an official HEYTEA campaign or a company-sponsored experiment. Outcomes are based on survey responses rather than observed transactions.

## Research Questions

- Do the two promotional offers differ in stated purchase intention?
- Are promotion recommendations associated with offer type?
- Which aspects of the in-store experience are associated with overall satisfaction?
- How representative is the surveyed audience of the wider Boston market?

## Data

Survey responses were collected using a questionnaire with two promotional scenarios. The notebook merges survey exports, consolidates overlapping question fields, removes incomplete or otherwise excluded responses, and prepares variables for analysis.

| Measure | Value |
| --- | ---: |
| Valid survey responses | 112 |
| Respondents reporting prior HEYTEA Boston store visits | 78 |
| Promotion-group sizes | 54 and 58 |
| Purchase-intention scale | 1–5 |

**Data privacy:** The raw survey exports include fields such as response identifiers, IP addresses, and location information. Do not publish identifiable respondent-level data. Share only appropriately anonymized data, if permitted.

## Tools and Methods

- **Python:** Pandas, NumPy
- **Statistical analysis:** SciPy, Statsmodels
- **Visualization:** Matplotlib, Seaborn, Plotly
- **Methods:** Welch's independent-samples t-test, chi-square tests, multiple linear regression (OLS), interaction analysis, Pearson correlation, exploratory data analysis (EDA)

## Analysis Workflow

### 1. Data preparation

- Import and combine two versions of the survey export.
- Reconcile duplicated survey questions and normalize response fields.
- Filter completed responses and apply the notebook's quality-control rules.
- Encode promotion groups and survey outcomes for statistical analysis.

### 2. Promotion comparison

Compare respondents' stated likelihood of placing an order under the two promotional scenarios using Welch's t-test. Assess whether recommendation responses vary by promotion type using a chi-square test.

### 3. Customer satisfaction

Use multiple linear regression to examine relationships between overall satisfaction and ratings of drink taste, store environment, price, waiting time, pickup experience, and service. Explore an interaction between perceived store environment and drink taste.

### 4. Additional exploratory analysis

Examine demographic balance, survey response distributions, promotion information channels, and correlations among experience measures.

## Results

### Purchase intention

| Statistic | Survey group 0 | Survey group 1 |
| --- | ---: | ---: |
| Sample size | 54 | 58 |
| Mean purchase-intention score | 3.33 | 3.72 |
| Standard deviation | 1.08 | 1.09 |

- **Welch's t-test:** *t* = −1.905, *p* = 0.0595.
- The observed difference was approximately **0.39 points** on a five-point scale.
- This difference **does not meet the conventional 5% statistical significance threshold**. It should not be described as a proven improvement in conversion or sales.

**Important group-label caveat:** The notebook contains inconsistent comments and labels for numeric promotion codes (`0` and `1`). Before attributing the higher mean to BOGO or the canvas bag offer, reconcile the code mapping against the original questionnaire and source responses.

### Promotion recommendation

- **Chi-square test:** χ² = 14.4249, *p* ≈ 0.0001.
- The notebook reports recommendation rates of **79.3%** and **42.6%** across the two promotion conditions.
- The association is statistically significant in this sample, but **the direction by named promotion must be verified** because the notebook's group labels are inconsistent.

### Customer experience

- **Multiple linear regression:** R² = 0.213 for the satisfaction model reported in the notebook.
- **Waiting-time rating vs. environment rating:** Pearson *r* = 0.3222, *p* = 0.0040. This is an association between **ratings**, not evidence that objectively longer waits improve the store experience.
- **Gender distribution across promotion groups:** χ² = 2.8767, *p* = 0.4110; no statistically significant difference was detected by this test.

## Interpretation

The survey provides preliminary evidence that promotion format is associated with respondents' willingness to recommend an offer. The purchase-intention difference is less conclusive at the 5% threshold. Findings should be treated as **survey-based behavioral indicators**, not measured changes in purchases, revenue, or customer retention.

## Limitations

1. **Self-reported outcomes:** Purchase intention and willingness to recommend are not actual conversion or referral behavior.
2. **Sample representativeness:** The notebook describes a sample heavily concentrated among students and Chinese respondents, limiting generalizability.
3. **Small sample:** The study contains 112 valid responses; the observed purchase-intention difference is not significant at α = 0.05.
4. **Observational experience analysis:** Satisfaction regressions and correlations should not be interpreted as causal effects.
5. **Reproducibility:** The notebook loads survey CSVs from Google Drive and includes notebook-state dependencies. A cleaned, privacy-safe data pipeline would make replication easier.

## Repository Structure

```text
Heytea-Boston-Market-Analysis/
├── README.md
└── Heytea_Boston_Market_Analysis.ipynb
```

## Next Steps

- Verify the promotion-group mapping from the original survey form.
- Consolidate preprocessing into a reproducible pipeline.
- Re-run group-level statistics and update promotion-specific interpretations.
- Remove personal information and external data-access dependencies before sharing the project publicly.

## Project Context

**Type:** Academic survey / A/B scenario analysis  
**Market:** Boston, Massachusetts  
**Brand studied:** HEYTEA
