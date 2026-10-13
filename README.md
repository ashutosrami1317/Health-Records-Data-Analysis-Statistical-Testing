[README (2).md](https://github.com/user-attachments/files/33369715/README.2.md)
# Health Records Data Analysis & Statistical Testing

## Project Overview
This project analyzes a synthetic health dataset containing 300 records. It demonstrates exploratory data analysis and statistical hypothesis testing using Python.

**Important:** This dataset is synthetic and intended for learning only. It must not be used for medical diagnosis or clinical decisions.

## Dataset
- **File:** `health_records_300.csv`
- **Records:** 300
- **Columns:** 15

| Column | Description |
|---|---|
| `record_id` | Unique identifier |
| `age_group` | Age category: 18–25, 26–35, 36–45, 46–60, 60+ |
| `age` | Age in years |
| `weight` | Weight in kilograms |
| `gender` | Gender category |
| `region` | Geographic region |
| `smoking_status` | Smoking habit category |
| `exercise_frequency` | Exercise frequency |
| `bmi` | Body Mass Index |
| `blood_pressure` | Systolic blood pressure (mmHg) |
| `diabetes` | Diabetes indicator (`True`/`False`) |
| `hypertension` | Hypertension indicator (`True`/`False`) |
| `cholesterol_level` | Total cholesterol (mg/dL) |
| `glucose_level` | Fasting glucose (mg/dL) |
| `visit_date` | Health check-up or diagnosis date |

## Project Objectives
1. Formulate null and alternative hypotheses.
2. Calculate 95% confidence intervals for numerical variables.
3. Interpret critical values and p-values.
4. Compare glucose levels for smokers and non-smokers using Welch's t-test.
5. Test smoking status versus diabetes using a chi-square test.
6. Demonstrate one-way ANOVA across age groups.
7. Calculate covariance and Pearson correlation between age and BMI.
8. State each test's decision and interpretation.

## Tools and Libraries
- Python
- Pandas
- NumPy
- SciPy
- Matplotlib (optional)
- Jupyter Notebook

## Setup
Install the required libraries:

```bash
pip install pandas numpy scipy matplotlib jupyter
```

Keep `health_records_300.csv` in the same folder as your notebook, then load it:

```python
import pandas as pd

df = pd.read_csv("health_records_300.csv")
print(df.head())
print(df.shape)
```

## Example Hypotheses

### Smoking Status and Diabetes
- **H₀:** Smoking status and diabetes are independent.
- **H₁:** Smoking status and diabetes are associated.

### Age Group and Diabetes
- **H₀:** Diabetes rates are equal across age groups.
- **H₁:** At least one age group has a different diabetes rate.

### Age and BMI
- **H₀:** Age and BMI have no linear correlation in the population.
- **H₁:** Age and BMI have a linear correlation in the population.

## Statistical Formulas

### 1. 95% Confidence Interval
`CI = sample mean ± t critical value × (sample standard deviation / √n)`

### 2. Welch's Independent-Samples t-Test
`t = (mean₁ − mean₂) / √(s₁²/n₁ + s₂²/n₂)`

### 3. Chi-Square Test
`χ² = Σ[(Observed − Expected)² / Expected]`

`Expected = (Row total × Column total) / Grand total`

### 4. One-Way ANOVA
`F = Mean Square Between Groups / Mean Square Within Groups`

**Method note:** Since diabetes is a binary variable, ANOVA is not ideal for comparing diabetes rates across age groups. A chi-square test or logistic regression is generally more appropriate. ANOVA is included only as a learning exercise.

### 5. Sample Covariance
`Cov(X, Y) = Σ[(X − mean X)(Y − mean Y)] / (n − 1)`

### 6. Pearson Correlation
`r = Σ[(X − mean X)(Y − mean Y)] / √[Σ(X − mean X)² × Σ(Y − mean Y)²]`

## Decision Rule
Use significance level `α = 0.05`:
- If `p-value < 0.05`, reject the null hypothesis (`H₀`).
- If `p-value ≥ 0.05`, fail to reject the null hypothesis (`H₀`).

Report each test's statistic, p-value, decision, and interpretation. Recalculate numerical results directly from the CSV before reporting them.

## Limitations
- The dataset is synthetic, not real patient data.
- Statistical association does not prove causation.
- Results should not be generalized to a real population.
- Verify all numerical findings by running your analysis on the included CSV.

## Project Structure

```text
health-records-analysis/
├── health_records_300.csv
├── README.md
└── analysis.ipynb   # Optional analysis notebook
```

## Author
**Rami Ashutosh**

Created as a Python data analysis and statistical testing practice project.
