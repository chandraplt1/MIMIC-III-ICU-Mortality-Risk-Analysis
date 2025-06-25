
# 🏥 MIMIC-III ICU Mortality Risk Analysis

This project analyzes ICU patient data from the [MIMIC-III](https://physionet.org/content/mimiciii/1.4/) clinical database to uncover patterns in mortality risk. It provides insights through Python visualizations and a Power BI dashboard for stakeholders in healthcare analytics, clinical strategy, and policy.

---

## 📌 Project Goals

- Identify key predictors of ICU mortality
- Compare outcomes across gender, age groups, and ICU types
- Leverage early vitals (within 24h) for risk estimation
- Demonstrate healthcare data storytelling using real EHR data

---

## 📂 Files in Repository

| File | Description |
|------|-------------|
| `ICU_Mortality_Analysis.ipynb` | Full Jupyter Notebook with data cleaning, EDA, and visual insights |
| `dashboard_summary.csv` | Cleaned summary file used for Power BI dashboard |
| `MIMIC_ICU_Mortality.pbix` | Power BI dashboard showing trends and risk segments |
| `docs/mimic_data_dictionary.md` | Data dictionary explaining key fields |
| `images/preview.png` | Repository social preview image |

---

## 🧪 Data Used

- `PATIENTS.csv`: Gender, birthdate, death info
- `ADMISSIONS.csv`: Admission dates and hospital outcome
- `ICUSTAYS.csv`: ICU admission/discharge timestamps
- `CHARTEVENTS.csv`: Vital signs and charted observations (limited to 1M rows)
- `D_ITEMS.csv`: Item IDs with descriptions

---

## 📊 Key Insights

- **Mortality increases with age**: Especially notable beyond 75 years.
- **Males show higher ICU mortality** than females.
- **Low systolic blood pressure (<90 mmHg)** and **high heart rate (>110 bpm)** in the first 24 hours strongly correlate with increased mortality.
- **MICU (Medical ICU)** showed higher risk concentration than SICU (Surgical ICU).

---

## 📈 Dashboard Preview (Power BI)

The Power BI dashboard  contains:

- Mortality by Age Group
- Gender Distribution & Risk
- ICU Type Comparison
- First 24h Heart Rate & BP Analysis
- Interactive slicers for subgroup analysis

---

## 📦 Getting Started

1. Clone the repo  
   ```bash
   git clone https://github.com/chandraplt1/mimic-icu-risk.git
   cd mimic-icu-risk
   ```

2. Install dependencies  
   ```bash
   pip install pandas matplotlib seaborn
   ```

3. Open the notebook  
   Launch `ICU_Mortality_Analysis_Fixed.ipynb` and run it in Jupyter.

---


## 👩‍💻 Author

**Lakshmi Tejaswini Chandra Pampana**  
[GitHub](https://github.com/chandraplt1) | [LinkedIn](https://www.linkedin.com/in/chandraplt)

---

> ⚠️ Data from MIMIC-III is under credentialed license. Ensure ethical and compliant use.
