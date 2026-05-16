# Medical Insurance Cost - Exploratory Data Analysis (EDA)

This repository contains an end-to-end Exploratory Data Analysis (EDA) and statistical analysis on a medical insurance cost dataset. The goal of this project is to discover which medical and demographic factors influence health insurance charges the most.

## 📋 Table of Contents
1. [Dataset Overview](#dataset-overview)
2. [Key Objectives & Methodology](#key-objectives--methodology)
3. [Project Directory Structure](#project-directory-structure)
4. [Installation & Setup](#installation--setup)
5. [Usage](#usage)

---

## 📊 Dataset Overview
The dataset contains information on 1,338 individuals with 7 baseline features:

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `age` | Integer | Age of primary beneficiary |
| `sex` | Object | Insurance contractor gender (`female`, `male`) |
| `bmi` | Float | Body mass index, providing an understanding of body weight relative to height |
| `children` | Integer | Number of children covered by health insurance / Number of dependents |
| `smoker` | Object | Smoking status (`yes`, `no`) |
| `region` | Object | The beneficiary's residential area in the US (`northeast`, `northwest`, `southeast`, `southwest`) |
| `charges` | Float | Individual medical costs billed by health insurance (Target Variable) |

---

## 🛠️ Key Objectives & Methodology

### 1. Data Cleaning
* Handling duplicated records using `pandas` `.drop_duplicates(inplace=True)` to ensure statistical validity.

### 2. Feature Engineering
* Categorizing BMI into standard health bands (`bmi_category_Normal weight`, `bmi_category_Overweight`, `bmi_category_Obese`).
* Bining continuous `charges` into discrete quartiles using `pd.qcut()` for categorical test processing.
* Encoding categorical attributes (`sex`, `smoker`, `region`) into numerical indicators via one-hot encoding (`pd.get_dummies()`).

### 3. Statistical Analysis
* **Pearson Correlation Matrix ($r$):** Executed on numerical features to rank linear relationships with insurance `charges`.
* **Chi-Square ($\chi^2$) Test of Independence:** Performed between engineered categorical values and binned charge tiers to test significance against a default $\alpha = 0.05$ threshold.

---

## 📁 Project Directory Structure

```text
insurance_eda/
│
├── venv/                  # Python Virtual Environment (Excluded from Git)
├── insurance.csv          # Raw dataset (Excluded from Git)
├── .gitignore             # Configured to ignore data, venv, and cache files
├── README.md              # Project documentation (This file)
└── analysis.ipynb         # Main Jupyter Notebook containing EDA and tests


⚙️ How to Run

Clone the repo: git clone <repo-url>
Install dependencies
