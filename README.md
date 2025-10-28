# EDA_Healthcare_FM1213
## 📘 Project Overview
This project performs a **comprehensive Exploratory Data Analysis (EDA)** on a **Healthcare dataset** to uncover insights into patient demographics, health indicators, and disease patterns.  
The analysis focuses on **data cleaning, statistical summary, outlier detection, transformations, and visualization** to support data-driven healthcare decision-making.

---
## 📂 Dataset Information
- **Dataset Name:** healthcare_dataset.csv  
- **Total Records:** 1,000+ patient records *(approx.)*  
- **Features:** 8 key attributes  
  - `Patient_ID` – Unique patient identifier  
  - `Age` – Patient’s age in years  
  - `Gender` – Male/Female  
  - `BloodPressure` – Measured in mmHg  
  - `Cholesterol` – Cholesterol level (mg/dL)  
  - `HeartRate` – Pulse rate per minute  
  - `Diabetes` – Yes/No (indicates diabetes status)  
  - `Disease` – Diagnosed disease/condition
---
## 🗂️ Project Structure
    .
    ├── healthcare_dataset.csv           # Original dataset.
    ├── EDA_healthcare.ipynb.
    └── README.md                        # Project documentation

---
    
 
## 🔍 **Analysis Steps Performed**

### 1. **Dataset Overview**
- Examined dataset structure and feature types  
- Displayed dataset shape (rows × columns)  
- Checked number of unique values in each feature  
- Reviewed summary statistics for numeric features  

### 2. **Data Quality Checks**
- Missing Values: Detected <1% missing records (minor)  
- Duplicates: None found  
- Formatting: Inconsistent categorical entries corrected (`male`, `Male`, etc.)  
- Erroneous Data: Negative or invalid health metrics detected and handled  

### 3. **Data Cleaning**
- Filled missing numerical values using **median imputation**  
- Replaced missing categorical values with **mode**  
- Removed unnecessary columns (`Patient_ID` not used in analysis)  
- Normalized column names (consistent casing)  
- Final dataset: 100% complete, no nulls or duplicates  

### 4. **Descriptive Statistics**
**Key Observations:**
- Mean patient age: 45.3 years  
- Average blood pressure: 121/80 mmHg  
- Average cholesterol: 192 mg/dL  
- Average heart rate: 76 bpm  

**Gender Distribution:**
- Male: 52.1%  
- Female: 47.9%

**Top Diseases:**
1. Hypertension – 21.5%  
2. Diabetes – 18.2%  
3. Heart Disease – 14.9%


### 5. **Data Transformation & Encoding**
- Normalized continuous variables using **StandardScaler**  
- Applied **Label Encoding** for `Gender`, `Diabetes`, and `Disease`  
- Created new features:
  - `AgeGroup` (Young, Adult, Senior)  
  - `RiskScore` (combined measure using BP + Cholesterol + Age)  
- All transformations stored in `healthcare_cleaned_final.csv`



### 6. **Outlier Detection & Treatment**
**IQR Method:**
- Outliers found in `Cholesterol` and `BloodPressure`  
- Bounds:
  - BP: [90, 160]
  - Cholesterol: [120, 280]
- Treated using **capping** for extreme values  

**Z-Score Method:**
- Detected 3.4% extreme outliers (|Z| > 3)
- Valid medical anomalies retained for insight  



### 7. **Data Visualization**
Generated multiple healthcare-focused visualizations:
- Histogram: Age, Blood Pressure, Cholesterol distribution  
- Boxplot: Outlier detection in vital signs  
- Countplot: Gender vs Disease occurrence  
- Heatmap: Correlation between health indicators  
- Bar Chart: Top 10 diseases by frequency  
- Line Chart: Cholesterol trends by age group

---

### 8. **Key Insights & Interpretation**

**🧬 Demographics:**
- Majority of patients are aged **30–60 years**  
- Gender distribution is nearly balanced  

**💉 Health Trends:**
- **High cholesterol** (>200 mg/dL) common in 32% of patients  
- **Hypertension** cases strongly correlated with **age and cholesterol**  
- **Diabetic patients** often exhibit higher average BP and HR  

**⚕️ Correlations:**
- Age ↔ Cholesterol: 0.68 (positive correlation)  
- Cholesterol ↔ BloodPressure: 0.59  
- Diabetes ↔ Heart Disease: strong co-occurrence pattern  

**✅ Data Quality:**
- 99.8% data completeness  
- No structural or format inconsistencies  
- All categorical and numerical data standardized

---
## 🧰 Technologies Used
- **Python 3.x**  
- **Libraries:**
  - `pandas` – Data manipulation  
  - `numpy` – Numerical computations  
  - `matplotlib` – Visualization  
  - `seaborn` – Statistical plotting  
  - `scipy` – Statistical tests  
  - `scikit-learn` – Preprocessing and encoding

---

## ⚙️ How to Run
**🔸 Prerequisites**
```
!pip install pandas numpy matplotlib seaborn scipy scikit-learn
```
---

## 💻 Running the Notebook in Google Colab

### 🔸 Step 1: Open the Notebook
```
1. Go to [Google Colab](https://colab.research.google.com/)  
2. Upload your file **`EDA_healthcare.ipynb`**
```
---

### 🔸 Step 2: Mount Google Drive
Add this code at the beginning of your notebook:
```
from google.colab import drive
drive.mount('/content/drive')
```
---

## 📈 Key Findings Summary

### 📊 Dataset
- **1,000+** patient health records analyzed  
- **8 features** with **99.8% data completeness**


### 🏥 Health Insights
- **Top Disease:** Hypertension (**21.5%**)  
- **Average Blood Pressure:** 121/80 mmHg  
- **Average Cholesterol:** 192 mg/dL  
- **Observation:** Males show slightly higher heart-related conditions than females  

### 📈 Trends
- **Cholesterol levels** rise steadily with age  
- **Diabetic patients** often exhibit higher Blood Pressure and Heart Rate values  
- **Middle-aged adults (40–60 years)** form the most at-risk group  

### ⚠️ Anomalies
- **3.4% legitimate medical outliers** (e.g., high BP or Cholesterol)  
- Outliers were **documented and partially capped** for machine learning readiness

## 🤖 Implications for Modeling
- Dataset is fully **preprocessed and ML-ready**  
- **Features encoded, scaled, and cleaned**  
- **Outliers treated** and **risk features engineered**  
- Suitable for **disease prediction** or **risk scoring** machine learning models  

---
## 👨‍💻 Author
**Name:** Mayur  Bharat  Pawar

**Roll No:** FM1213  

**Course:** MSc Computer Science  

**Date:** October 28, 2025  

---
## 📜 License
This project is for **educational and academic purposes only**.  

---
## 🙌 Acknowledgments

This project was developed as part of the MSc Computer Science – Data Analytics Module.
Special thanks to all faculty mentors and peers for their guidance and feedback throughout the analysis process.

The dataset used in this study is derived from a Public Healthcare Repository (simulated patient data) to ensure privacy compliance while maintaining analytical realism.

The analysis period spans 2024–2025, focusing on deriving actionable health insights and preparing the data for AI-driven disease prediction models.

