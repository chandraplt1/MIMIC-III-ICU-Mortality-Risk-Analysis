# MIMIC-III-ICU-Mortality-Risk-Analysis

## 1. Background and Overview

Intensive Care Units (ICUs) are high-stakes environments where early identification of at-risk patients is crucial to prevent mortality. This project uses the publicly available **MIMIC-III dataset** to analyze clinical data from ICU stays and uncover patterns associated with increased mortality. The goal is to derive insights that could assist clinicians and data scientists in understanding ICU trends and building early warning models for critical care.

We focus on:

* Patient demographics and ICU admissions
* Vital signs and lab measures within the first 24 hours of ICU stay
* Mortality prediction trends based on these early indicators
* Disparities in mortality across age groups, genders, and ICU types

This project simulates how a hospital data team might analyze patient outcomes to improve quality of care and reduce ICU mortality rates.

---

## 2. Data Structure Overview

We utilized the following tables from MIMIC-III:

* `PATIENTS.csv`: Demographics, date of birth/death
* `ICUSTAYS.csv`: ICU admission/discharge timestamps, stay IDs
* `CHARTEVENTS.csv`: Time-stamped vitals and lab values

### ER Diagram

```
PATIENTS (SUBJECT_ID, GENDER, DOB, DOD)  
   |
   +-- ICUSTAYS (SUBJECT_ID, HADM_ID, ICUSTAY_ID, INTIME, OUTTIME, LOS)  
         |
         +-- CHARTEVENTS (ICUSTAY_ID, ITEMID, CHARTTIME, VALUENUM, VALUEUOM)
```

---

## 3. Executive Summary

* Patients aged **75+** had the highest in-hospital ICU mortality rate (\~18%), with **non-surgical ICUs** showing significantly higher rates.
* Abnormal early vitals (SBP < 90 mmHg, HR > 110 bpm) in the first 24 hours were strong indicators of higher mortality.
* **Female patients** had a slightly lower ICU mortality rate compared to males.
* ICU stays with **early hypotension** or abnormal oxygen saturation (< 90%) correlated with a **3x increase in death risk**.

These findings highlight the potential of using first-day clinical signals to flag patients at higher risk.

---

## 4. Insights Deep Dive

### Insight 1: Age-Based Mortality

```python
sns.barplot(data=summary_df, x='Age_Group', y='Mortality_Rate')
plt.title('ICU Mortality Rate by Age Group')
```

* Clear upward trend with age.

### Insight 2: Vital Signs and Risk

```python
sns.boxplot(data=icu_vitals, x='Mortality', y='HeartRate')
plt.title('Heart Rate Distribution by Outcome')
```

* Patients who died had higher median HRs in the first 24h.

### Insight 3: Gender Comparison

```python
sns.barplot(data=gender_summary, x='Gender', y='Mortality_Rate')
```

* Slightly higher mortality in male patients.

### Insight 4: ICU Type Influence

```python
sns.barplot(data=icu_type_summary, x='ICU_Type', y='Mortality_Rate')
```

* MICU and SICU had contrasting trends, important for triage decisions.

---

## 5. Recommendations

* **Early Risk Scoring**: Hospitals can build risk scores using patient age and first-day vitals to triage ICU care.
* **Monitor Hypotensive Events**: Introduce EHR alerts for systolic BP < 90 mmHg in first 24h.
* **Prioritize Older Adults**: Design targeted interventions for patients aged 65+ to reduce in-hospital mortality.
* **Further NLP Analysis**: Investigate clinical notes in MIMIC for sentiment or symptom patterns in high-risk groups.

---

## Links

* 📊 [Interactive Dashboard](https://github.com/yourprofile/mimic-icu-dashboard)
* 📁 [Jupyter Notebook Code](notebooks/ICU_Mortality_Analysis.ipynb)
* 📄 [Data Dictionary](docs/mimic_data_dictionary.md)

---

> **Note**: Data is sourced from [PhysioNet MIMIC-III Clinical Database](https://physionet.org/content/mimiciii/1.4/) under a credentialed license.

> **Caveats & Assumptions**:

* Data reflects one hospital system (Beth Israel Deaconess).
* Some variables (e.g., lab values) had missing or sparse entries.
* We only analyzed first ICU admission per patient.

---

**Created by:** Lakshmi Tejaswini Chandra Pampana
**GitHub Repo:** [chandraplt1/mimic-icu-risk](https://github.com/chandraplt1/mimic-icu-risk)
