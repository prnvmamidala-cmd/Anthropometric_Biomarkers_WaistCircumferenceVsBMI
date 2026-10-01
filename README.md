# BMI vs. Waist Circumference for Cardiovascular Disease Association in NHANES

## Overview

This project compares **body mass index (BMI)** and **waist circumference** as anthropometric markers associated with prevalent cardiovascular disease (CVD) in U.S. adults using data from the **National Health and Nutrition Examination Survey (NHANES), 2005–2018**.

BMI is widely used as a general measure of obesity, but it does not directly capture the distribution of adipose tissue. Waist circumference more directly reflects central adiposity, which may be more closely related to cardiometabolic disease.

The primary goal of this study was to determine whether waist circumference demonstrates a stronger statistical association and greater univariate discrimination for prevalent CVD than BMI.

---

## Research Question

**Does waist circumference show a stronger association with prevalent cardiovascular disease than BMI in NHANES participants?**

The study evaluates whether waist circumference may provide useful anthropometric information beyond what is captured by BMI.

This project is intended as an **exploratory, cross-sectional association study** rather than a causal analysis or clinical prediction model.

---

## Dataset

Data were obtained from the **National Health and Nutrition Examination Survey (NHANES)** across survey cycles from:

**2005–2006 through 2017–2018**

The compiled dataset contained approximately:

- **58,830 participants**
- BMI measurements
- Waist circumference measurements
- Cardiovascular disease questionnaire information
- Demographic and clinical variables available from NHANES

### Outcome

The primary outcome was **prevalent self-reported cardiovascular disease**.

Participants were classified according to whether they reported a history of cardiovascular disease within the relevant NHANES questionnaire variables.

Because NHANES is cross-sectional, the analysis evaluates **existing disease prevalence rather than future cardiovascular risk**.

---

## Anthropometric Variables

### Body Mass Index

BMI represents body mass relative to height:

\[
BMI = \frac{weight\;(kg)}{height\;(m)^2}
\]

BMI is useful for characterizing general body size but does not distinguish between:

- visceral and subcutaneous fat
- muscle and adipose tissue
- central and peripheral fat distribution

### Waist Circumference

Waist circumference provides a direct measurement of abdominal size and serves as a proxy for **central adiposity**.

Central fat accumulation has been associated with metabolic abnormalities such as insulin resistance, dyslipidemia, and cardiovascular disease.

---

## Analysis

BMI and waist circumference were evaluated separately using several complementary statistical methods.

### 1. Group Comparisons

Mean BMI and waist circumference were compared between participants with and without prevalent cardiovascular disease using:

- two-sample t-tests
- effect-size analysis using Cohen's \(d\)

---

### 2. Point-Biserial Correlation

Point-biserial correlations were calculated between each continuous anthropometric measurement and binary CVD status.

This quantified the strength of the unadjusted relationship between:

- BMI and CVD
- waist circumference and CVD

---

### 3. Logistic Regression

Separate univariate logistic regression models were constructed for BMI and waist circumference.

Variables were standardized before modeling so that odds ratios could be interpreted per standard-deviation increase.

For each variable, the analysis reported:

- odds ratio
- 95% confidence interval
- statistical significance

These models were intended to quantify **association**, not causality.

---

### 4. ROC Analysis

Receiver operating characteristic curves were generated for BMI and waist circumference separately.

Performance was summarized using the area under the ROC curve (**AUROC**).

The difference in AUC between waist circumference and BMI was also calculated.

Because these were single-variable exploratory models, the AUC values should be interpreted as measures of **univariate discrimination**, not as performance of a clinical diagnostic system.

---

## Results

Across the statistical comparisons performed, waist circumference showed consistently stronger relationships with prevalent cardiovascular disease than BMI.

| Metric | BMI | Waist Circumference |
|---|---:|---:|
| Absolute t-statistic | 40.58 | **69.35** |
| Point-biserial correlation | 0.153 | **0.210** |
| Cohen's \(d\) | 0.640 | **0.888** |
| Odds ratio per SD | 1.70 | **2.47** |
| 95% CI for OR | 1.65–1.75 | **2.38–2.56** |
| ROC-AUC | 0.6939 | **0.7567** |

### Difference in AUC

\[
\Delta AUC = 0.7567 - 0.6939 = 0.0628
\]

Waist circumference therefore demonstrated approximately a **0.063 higher univariate ROC-AUC** than BMI in the analyzed sample.

---

## Interpretation

The results suggest that **waist circumference may capture cardiovascular-disease-related anthropometric information more strongly than BMI alone**.

This may occur because BMI measures overall body mass relative to height, while waist circumference more directly reflects abdominal adiposity.

However, these findings should **not** be interpreted to mean that waist circumference should replace BMI.

Instead, the results support the idea that waist circumference may serve as a useful **complementary anthropometric measure**, particularly when evaluating cardiometabolic health.

---

## Important Limitations

Several limitations substantially affect interpretation of the results.

### Cross-sectional study design

NHANES measurements and disease history were evaluated cross-sectionally.

Therefore, this study cannot determine whether higher BMI or waist circumference caused cardiovascular disease.

---

### Self-reported cardiovascular disease

CVD status was based on questionnaire responses rather than prospective adjudicated cardiovascular outcomes.

Misclassification may therefore be present.

---

### Unadjusted analyses

The primary comparisons were univariate and did not fully control for potential confounders such as:

- age
- sex
- smoking
- hypertension
- diabetes
- lipid levels
- medications
- race/ethnicity

Because waist circumference may correlate with several of these factors, the observed difference between BMI and waist circumference should not be interpreted as an independent causal effect.

---

### NHANES survey design

The exploratory analysis did not apply the full NHANES:

- sampling weights
- strata
- primary sampling units

As a result, the reported values describe the analyzed sample and should not automatically be interpreted as nationally representative U.S. estimates.

---

### Model comparison

BMI and waist circumference were evaluated independently.

More rigorous evaluation would compare the two variables within matched multivariable models and determine whether waist circumference provides meaningful **incremental information beyond BMI**.

---

## Future Work

A stronger follow-up study could evaluate whether waist circumference adds predictive or explanatory value after accounting for BMI and major cardiovascular risk factors.

Potential extensions include:

### Survey-weighted modeling

Use the NHANES complex survey design, incorporating:

- survey weights
- strata
- primary sampling units

This would allow estimates to better represent the U.S. population.

### Multivariable adjustment

Construct adjusted logistic regression models including variables such as:

- age
- sex
- race/ethnicity
- smoking
- diabetes
- hypertension
- lipid measurements
- BMI
- waist circumference

### Incremental-value analysis

Compare models such as:

1. clinical covariates only
2. clinical covariates + BMI
3. clinical covariates + waist circumference
4. clinical covariates + BMI + waist circumference

This would help determine whether waist circumference contributes information that is not already captured by BMI.

### Discordant BMI–waist groups

A particularly useful extension would examine participants whose BMI and waist circumference classifications disagree.

For example:

- normal BMI but elevated waist circumference
- elevated BMI but normal waist circumference

These groups may reveal situations in which waist circumference identifies central adiposity that BMI does not capture.

### Subgroup analysis

Future analyses could investigate whether the relationship differs across:

- sex
- age
- race/ethnicity
- metabolic status
- hormone levels

### External validation

Replication in an independent cohort would help determine whether the observed relationship generalizes beyond NHANES.

---

## Technologies

The analysis was conducted in Python using tools including:

- Python
- pandas
- NumPy
- SciPy
- statsmodels
- Matplotlib
- Seaborn

---

---

## Key Takeaway

Across multiple unadjusted statistical measures, **waist circumference demonstrated a stronger association with prevalent cardiovascular disease than BMI** in the analyzed NHANES sample.

Most notably:

- Waist AUC: **0.7567**
- BMI AUC: **0.6939**
- Difference: **0.0628**

The findings support further investigation of waist circumference as a complementary anthropometric marker alongside BMI, while emphasizing the need for survey-weighted, adjusted, and externally validated analyses before drawing clinical conclusions.

---
.
