🏥 ICU Mortality Risk Analysis with MIMIC-III
This project analyzes ICU patient data from the MIMIC-III clinical database to uncover patterns related to mortality risk, with a focus on age, gender, ICU type, and vital sign abnormalities.

🔍 Project Overview
Early detection of ICU mortality risk factors is crucial to improving outcomes in critical care. Using Python (pandas, seaborn, matplotlib) and Power BI, we:

Conducted exploratory data analysis (EDA)

Engineered mortality flags and age groups

Visualized trends by age, gender, and ICU unit

Created a dashboard-ready summary dataset

Exported insights to an interactive Power BI dashboard

📁 Files Included
File	Description
ICU_Mortality_Analysis_Enhanced.ipynb	Jupyter Notebook with full analysis, visualizations, and feature engineering
dashboard_summary.csv	Clean dataset ready for Power BI dashboarding
ICU_Mortality_Dashboard.pbix	💡 Interactive Power BI dashboard file
README.md	This project overview and documentation

📊 Key Insights
Age ≥ 75 had the highest ICU mortality (>17%)

Males had slightly higher mortality than females

MICU and SICU showed contrasting death rates

Patients with early hypotension or high heart rate showed elevated risk

🛠 Tech Stack
Python (pandas, matplotlib, seaborn)

Power BI

Jupyter Notebook

MIMIC-III Dataset (Beth Israel Deaconess Medical Center)

📈 Power BI Dashboard
Visualizes:

Mortality trends by gender

ICU-specific risk distributions

Patient age histograms

Combined view of ICU admissions and outcomes

📥 Download Dashboard: ICU_Mortality_Dashboard.pbix

🚀 How to Run
Clone the repo

Launch ICU_Mortality_Analysis_Enhanced.ipynb in Jupyter

Export dashboard_summary.csv

Open ICU_Mortality_Dashboard.pbix in Power BI Desktop

Refresh the data and explore!

📌 Note: This analysis uses a sample from MIMIC-III and is meant for educational and prototype purposes. Data is anonymized and access requires credentialed approval via PhysioNet.

Author: Lakshmi Tejaswini Chandra Pampana
GitHub: @chandraplt1

