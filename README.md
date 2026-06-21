# CPC152 - Introduction to Data Science (Assignment 2)

This repository contains the Jupyter Notebook implementation for **CPC152: Introduction to Data Science - Assignment 2** at Universiti Sains Malaysia (USM).

## Course Details
- **Course Code:** CPC152
- **Course Name:** Introduction to Data Science
- **Semester:** Year 1, Semester 2 (2023/2024)

---

## Assignment Overview

The assignment applies data cleaning, exploratory data analysis (EDA), and statistical profiling techniques to a medical dataset (Heart Disease):
1. **Data Loading:** Reading the Cleveland Heart Disease CSV dataset using `pandas`.
2. **Data Cleaning:**
   - Renaming cryptic column names to readable labels (`cp → ChestPainType`, `trestbps → RestingBP`, etc.).
   - Detecting and removing duplicate entries.
   - Verifying no null/missing values remain.
3. **Exploratory Data Analysis (EDA):**
   - Describing distribution of age, blood pressure, cholesterol, and max heart rate.
   - Counting unique values for categorical features (ChestPainType, Thalassemia, etc.).
   - Profiling the `target` variable (heart disease presence).
4. **Statistical Summary:** Computing count, mean, std, min, max, and quartile statistics per feature.

---

## What I Did
- Loaded and profiled a 303-row, 14-feature heart disease dataset.
- Cleaned column names and removed 1 duplicate row (302 clean records remaining).
- Performed univariate analysis on all features using `pandas` descriptive statistics.
- Written in [`heart_disease_eda.ipynb`](heart_disease_eda.ipynb).

---

## Tools & Tech Stack
- **Language:** Python 3
- **Libraries:** `pandas`, `matplotlib`
- **Environment:** Jupyter Notebook

---

## How to Run

1. Install the required libraries:
   ```bash
   pip install pandas matplotlib jupyter
   ```
2. Launch Jupyter Notebook:
   ```bash
   jupyter notebook heart_disease_eda.ipynb
   ```
3. Run all cells to reproduce the data cleaning and EDA steps.

> **Note:** The original dataset CSV is loaded from a local path. Update the `pd.read_csv(...)` path in cell 2 to point to your local copy of the heart disease dataset.

---

## 📸 Sample Output

**Dataset Shape & Columns:**
```python
df.shape  # (302, 14)
df.columns
# Index(['age', 'sex', 'ChestPainType', 'RestingBP', 'Cholesterol',
#        'FastingBS', 'restecg', 'MaxHR', 'ExerciseAngina', 'oldpeak',
#        'slope', 'MajorVessels', 'Thalassemia', 'target'], dtype='object')
```

**Data Quality Checks:**
```
df.isnull().sum()  →  All 14 columns: 0 nulls
df.duplicated().sum() before cleaning: 1
df.duplicated().sum() after cleaning:  0
```

**Age Distribution Summary:**
```
count    302.0
mean      54.4
std        9.0
min       29.0
25%       48.0
50%       55.5
75%       61.0
max       77.0
Name: age, dtype: float64
```

**Dataset Preview (df.head()):**
```
   age  sex  ChestPainType  RestingBP  Cholesterol  FastingBS  MaxHR  target
0   63    1              3        145          233          1    150       0
1   37    1              2        130          250          0    187       0
2   41    0              1        130          204          0    172       0
3   56    1              1        120          236          0    178       0
4   57    0              0        120          354          0    163       0
```

**Column Info:**
```
<class 'pandas.core.frame.DataFrame'>
302 entries, 14 columns — all int64 / float64, no nulls
```
