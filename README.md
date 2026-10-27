# 🩺 Health Statistics & Hypothesis Testing | Python Analytics Project

<p align="center">
  <b>Exploratory Health Data Analysis • Statistical Inference • Hypothesis Testing</b><br>
  A Python-based project examining relationships between lifestyle factors, health measurements, and diabetes-related outcomes.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Pandas-Data%20Wrangling-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/NumPy-Numerical%20Analysis-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy">
  <img src="https://img.shields.io/badge/SciPy-Statistics-8CAAE6?style=for-the-badge" alt="SciPy">
  <img src="https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=for-the-badge" alt="Seaborn">
  <img src="https://img.shields.io/badge/Status-Portfolio%20Project-2EA44F?style=for-the-badge" alt="Project status">
</p>

---

## 📌 Project Overview

**Derivable Judgement** is a statistical analysis project built with Python, Jupyter Notebook, and a health-related dataset. It explores whether selected lifestyle and demographic variables are associated with diabetes outcomes, estimates confidence intervals for numerical health measurements, and applies statistical tests to compare groups.

The notebook combines statistical inference with visual exploration to demonstrate a practical workflow for analysing structured data.

> **Scope note:** This is an educational analytics project, not a clinical study or a medical diagnosis tool. Statistical associations in this dataset do not establish cause and effect.

## 🎯 Project Objectives

- Formulate null and alternative hypotheses from the dataset.
- Test the association between smoking status and diabetes.
- Compare glucose levels between diabetes and non-diabetes groups.
- Calculate 95% confidence intervals for key numerical variables.
- Interpret test statistics, critical values, and p-values.
- Demonstrate z-test, t-test, chi-square, and ANOVA procedures.
- Calculate covariance and correlation between age and BMI.
- Visualize distributions, group differences, and correlations.
- Save analysis charts for reporting and presentation.

## 🗂️ Repository Structure

```text
.
├── Derivable_Judgement.ipynb
├── Derivable Judgement.csv
├── Theory Notes.docx
├── charts/
│   ├── fig1_diabetes_by_smoking.png
│   ├── fig2_contingency_heatmap.png
│   ├── fig3_glucose_dist.png
│   ├── fig4_bp_by_age.png
│   ├── fig5_bmi_bp_scatter.png
│   └── fig6_corr_matrix.png
└── README.md
```

The `charts/` files are generated when the notebook is run. The theory notes document contains supporting definitions of inferential statistics, hypothesis testing, confidence intervals, p-values, common statistical tests, covariance, and correlation.

## 🧰 Technology Stack

| Tool / Library | Role in the Project |
|---|---|
| Python | Main programming language |
| Pandas | Dataset loading, filtering, and crosstabulation |
| NumPy | Numerical computing |
| SciPy | Confidence intervals and statistical tests |
| Statsmodels | Z-test implementation |
| Matplotlib | Chart creation and export |
| Seaborn | Statistical plots and heatmaps |
| Jupyter Notebook | Interactive analysis and code documentation |

## 📊 Dataset Overview

The supplied CSV contains **148 records and 15 columns**.

| Column | Description |
|---|---|
| `record_id` | Record identifier |
| `age_group` | Age category |
| `age` | Age in years |
| `weight` | Weight value as recorded in the dataset |
| `gender` | Gender category |
| `region` | Region category |
| `smoking_status` | Smoking status |
| `exercise_frequency` | Exercise frequency |
| `bmi` | Body mass index |
| `blood_pressure` | Blood pressure value as recorded |
| `diabetes` | Diabetes indicator (`True` / `False`) |
| `hypertension` | Hypertension indicator (`True` / `False`) |
| `cholesterol_level` | Cholesterol measurement |
| `glucose_level` | Glucose measurement |
| `visit_date` | Visit date |

The notebook uses these fields to investigate relationships and differences across groups. Confirm units and measurement definitions with the dataset provider before interpreting the health measurements.

## 🔬 Analysis Workflow

### 1. Load the dataset

The notebook reads the CSV into a Pandas DataFrame.

```python
import pandas as pd

DF = pd.read_csv("Derivable Judgement.csv")
DF.head()
```

Using a relative path makes the project easier to run on another computer than using a machine-specific absolute path.

### 2. Hypothesis testing

The notebook sets a significance level of \(\alpha = 0.05\) and explores two hypotheses.

**Hypothesis 1 — Smoking status and diabetes**

- \(H_0\): Smoking status and diabetes are independent.
- \(H_1\): Smoking status and diabetes are associated.
- Method: Chi-square test of independence.

**Hypothesis 2 — Glucose level and diabetes**

- \(H_0\): Mean glucose levels are equal for the diabetes and non-diabetes groups.
- \(H_1\): Mean glucose levels differ between the groups.
- Method: Independent two-sample t-test with unequal variances (Welch's t-test).

The notebook compares each p-value with the significance level to determine whether to reject the null hypothesis.

### 3. Confidence intervals

The notebook calculates 95% t-based confidence intervals for:

- Age
- Weight
- BMI
- Blood pressure
- Cholesterol level

These intervals estimate the population mean under the assumptions of the method.

### 4. Critical value and p-value

For the glucose comparison, the notebook calculates a t-statistic, an approximate degrees-of-freedom value, a two-sided 5% critical value, and a p-value. These quantities are used to interpret statistical significance.

### 5. Z-test demonstration

A z-test is also applied to compare glucose levels between the two diabetes groups. The choice of test and its assumptions should be checked carefully; for an unequal-variance comparison, the Welch t-test is the more directly aligned method unless a suitable z-test variance assumption is justified.

### 6. Chi-square test

A contingency table summarizes smoking status against diabetes status. The chi-square test evaluates whether the observed categorical variables show evidence of an association.

### 7. ANOVA across age groups

The notebook applies one-way ANOVA to diabetes indicators across age groups. Because diabetes is a binary outcome, ordinary ANOVA is not generally the best inferential choice; a chi-square test or logistic regression would usually be more appropriate for comparing disease proportions.

### 8. Covariance and correlation

The notebook calculates covariance and Pearson correlation between age and BMI.

- Positive covariance indicates that the variables tend to move in the same direction.
- Correlation ranges from \(-1\) to \(+1\) and describes the strength and direction of a linear relationship.
- Correlation does not prove causation.

### 9. Visual analytics

The notebook creates and saves six plots:

1. Diabetes prevalence by smoking status.
2. Smoking status vs. diabetes contingency heatmap.
3. Glucose-level distribution with a density curve.
4. Blood pressure by age group.
5. BMI vs. blood pressure scatter plot.
6. Correlation matrix for numerical variables.

Plots are saved as PNG files in the `charts/` folder.

## 🚀 Getting Started

### Prerequisites

- Python 3.x
- Jupyter Notebook or JupyterLab

### Installation

Install the required packages:

```bash
pip install pandas numpy scipy statsmodels matplotlib seaborn jupyter
```

### Run the project

1. Download or clone the repository.
2. Keep `Derivable_Judgement.ipynb` and `Derivable Judgement.csv` in the same folder.
3. If needed, update the notebook's CSV path to the relative path shown above.
4. Start Jupyter:

```bash
jupyter notebook
```

5. Open `Derivable_Judgement.ipynb`.
6. Run the cells from top to bottom.
7. Check the generated plots in the `charts/` directory.

## 📈 Interpretation Guidelines

- A p-value below 0.05 is evidence against the null hypothesis under the test assumptions; it does not measure the size or practical importance of an effect.
- A p-value at or above 0.05 means there is insufficient evidence to reject the null hypothesis, not that the null hypothesis has been proven true.
- A confidence interval expresses uncertainty around an estimated parameter.
- Statistical conclusions should be based on the actual outputs produced by the notebook, not hard-coded interpretation text.
- Association between smoking status and diabetes does not establish that smoking caused diabetes in this dataset.

## ⚠️ Validation & Limitations

- The notebook includes hard-coded interpretation statements and example covariance/correlation values. Re-run the analysis and verify those statements against the computed outputs before publishing results.
- The CSV has 148 records; the dataset's sampling method and representativeness are not documented here.
- The z-test, t-test, chi-square test, and ANOVA each have assumptions that must be checked before interpreting their results.
- Diabetes is a binary outcome; logistic regression or suitable categorical tests may be more appropriate than ANOVA for comparing diabetes rates.
- The dataset should not be used for diagnosis, treatment decisions, or clinical recommendations.

## 🔮 Future Enhancements

- Add a reproducible data-quality report for missing values, duplicates, and invalid ranges.
- Create a single summary table of test name, null hypothesis, test statistic, p-value, decision, and interpretation.
- Replace hard-coded results with values calculated directly from test outputs.
- Report effect sizes and confidence intervals alongside p-values.
- Consider logistic regression for diabetes outcomes and check relevant assumptions.
- Add a `requirements.txt` file and a clear data dictionary with measurement units.
- Improve chart labels and add a concise executive summary of verified results.

## 👤 Author

**Harshit Dara**  
Aspiring Data Analyst | Python | Statistics | Data Visualization

- GitHub: [Add your GitHub profile URL]
- LinkedIn: [Add your LinkedIn profile URL]

## 📄 License

No license is currently specified. Add a `LICENSE` file if you want to define how others may use, modify, and distribute this project.

---

<p align="center">
  <i>Using statistical thinking to turn health data into interpretable insights.</i>
</p>
