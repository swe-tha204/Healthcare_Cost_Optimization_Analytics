
# 🏥 Healthcare Cost Optimization Analytics

### End-to-End Healthcare Data Analytics Project | Python | Statistical Modeling | Power BI

## 📌 Project Overview

This project focuses on analyzing healthcare expenditure, identifying major cost drivers, understanding patient utilization patterns, and discovering opportunities for healthcare cost optimization.

Using the Synthea Synthetic Healthcare Dataset, this project follows an end-to-end data analytics workflow involving data understanding, data cleaning, analytical dataset construction, exploratory data analysis (EDA), statistical and predictive modeling, and interactive Power BI dashboard development.

The primary objective is to understand where healthcare spending is concentrated, identify high-cost and high-utilization patterns, and generate data-driven insights that can support better financial and operational decision-making without compromising patient outcomes.

## 🎯 Business Objectives

- Identify major drivers of healthcare cost variation.
- Analyze healthcare spending across encounter types and demographics.
- Evaluate clinical procedures and utilization patterns.
- Identify high-cost encounters and high-cost patient segments.
- Analyze repeat encounters and healthcare utilization.
- Understand cost variation across providers, organizations, and payers.
- Develop a predictive model for encounter-level healthcare costs.
- Identify potential cost-optimization opportunities.
- Quantify illustrative cost-saving scenarios.
- Develop an interactive Power BI dashboard.

## 📊 Dataset Overview

**Dataset:** Synthea Synthetic Healthcare Dataset

The project uses multiple interconnected healthcare datasets to build a comprehensive encounter-level analytical dataset.

| Description | Details |
|---|---|
| Final Analytical Records | 61,459 |
| Analytical Features | 58 |
| Total Patients | 1,163 |
| Total Providers | 1,123 |
| Primary Dataset | Encounters |
| Primary Cost Measure | TOTAL_CLAIM_COST |
| Currency | USD |
| Data Type | Synthetic Healthcare Data |

### Source Datasets

The project integrates multiple healthcare datasets, including:

- Patients
- Encounters
- Conditions
- Procedures
- Medications
- Imaging Studies
- Providers
- Organizations
- Payers
- Claims
- Claims Transactions
- Observations
- Care Plans
- Immunizations
- Allergies
- Devices
- Supplies
- Payer Transitions

**Analytical Approach:** One row represents one healthcare encounter. Supporting datasets were aggregated to encounter level before integration to prevent row multiplication and double-counting.

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Python | Data Analysis and Processing |
| Pandas | Data Cleaning and Manipulation |
| NumPy | Numerical Operations |
| Matplotlib | Data Visualization |
| Jupyter Notebook | Development Environment |
| Scikit-learn | Statistical and Predictive Modeling |
| Power BI | Interactive Dashboard Development |
| DAX | KPI Calculations and Measures |

## 🔄 Project Workflow

### 1. Data Understanding & Collection

- Explored multiple healthcare CSV datasets.
- Examined dataset structures, relationships, and data quality.
- Identified primary and supporting datasets.
- Established encounter-level analytical grain.
- Selected TOTAL_CLAIM_COST as the primary cost measure.

### 2. Data Cleaning & Preparation

Performed data cleaning and validation using Python and Pandas.

**Data Cleaning Activities:**

- Inspected missing values across datasets.
- Identified and handled exact duplicate records.
- Validated date and timestamp fields.
- Investigated invalid placeholder dates.
- Performed financial and numerical validation.
- Checked reference consistency across datasets.
- Preserved meaningful missing values.
- Kept original raw datasets unchanged.
- Stored cleaned datasets separately.

**Important Data Quality Findings:**

- Identified 249 exact duplicate rows in observations.csv.
- Identified 70,733 invalid TODATE placeholder records in claims_transactions.csv.
- Excluded organization revenue from financial analysis because the source contained all-zero values.
- Validated the final analytical dataset for duplicate encounter IDs and missing primary cost values.

### 3. Analytical Dataset Construction

Built a consolidated healthcare analytical dataset by integrating encounter-level information from multiple supporting datasets.

**Final Dataset Validation:**

| Validation | Result |
|---|---:|
| Total Rows | 61,459 |
| Total Columns | 58 |
| Duplicate Encounter IDs | 0 |
| Missing Encounter IDs | 0 |
| Missing Patient IDs | 0 |
| Missing Primary Cost | 0 |
| Negative Primary Cost | 0 |
| Derived Feature Missing Values | 0 |

The final dataset includes encounter information, patient demographics, clinical utilization, procedures, medications, cost components, providers, organizations, payers, and claims-related features.

### 4. Exploratory Data Analysis (EDA)

Performed EDA by developing 11 business questions to understand healthcare spending patterns and identify potential cost drivers.

**EDA Business Analysis:**

1. Overall Healthcare Cost Distribution.
2. Cost Analysis by Encounter Type.
3. Demographic Cost Variation.
4. Utilization vs Healthcare Cost.
5. Clinical Cost Component Analysis.
6. Provider and Organization Cost Analysis.
7. Payer Cost Variation.
8. High-Cost Encounter Analysis.
9. 30-Day Repeat Encounter Analysis.
10. Inpatient Length of Stay Analysis.
11. Cost-Inefficiency Screening Patterns.

Used statistical summaries, grouping, aggregation, correlation analysis, and visualizations to identify important healthcare cost patterns.

### 5. Statistical & Predictive Modeling

Developed and evaluated multiple machine learning models to predict encounter-level healthcare costs.

**Model Development:**

- Selected TOTAL_CLAIM_COST as the prediction target.
- Used an 80% training and 20% testing split.
- Applied one-hot encoding to categorical variables.
- Standardized numerical variables.
- Used 22 non-leakage predictors.
- Compared multiple predictive models.

**Model Comparison:**

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Mean Cost Baseline | $5,515.74 | $10,115.98 | 0.0000 |
| Linear Regression | $4,390.25 | $8,475.29 | 0.2980 |
| Random Forest | $1,761.36 | $7,638.83 | 0.4298 |
| Log-Transformed Random Forest | $1,557.67 | $6,741.13 | 0.5559 |

**Best Performing Model:** Log-Transformed Random Forest.

The model achieved an R² of 0.5559, explaining approximately 55.6% of the variation in encounter-level healthcare costs on the held-out test dataset.

**Top Predictive Features:**

- Procedure Count
- Age at Encounter
- Medication Count
- Payer Name
- Observation Count
- Encounter Class
- Organization Utilization
- Provider Utilization
- Condition Count

Feature importance represents predictive contribution, not causation.

### 6. Healthcare Cost Optimization Analysis

Identified high-cost encounters, repeated utilization patterns, high procedure intensity, and high-cost patient segments.

**Major Analysis Areas:**

- High-Cost Encounter Identification.
- High Procedure Intensity Analysis.
- 30-Day Repeat Encounter Analysis.
- High-Cost Patient Segmentation.
- Frequent Healthcare User Analysis.
- Opportunity Screening.
- Potential Cost-Saving Scenarios.

## 💡 Key Business Insights & Findings

### 1. Overall Healthcare Cost Analysis

- Total Healthcare Cost: $255.03 Million.
- Total Encounters: 61,459.
- Average Encounter Cost: $4,149.53.
- High-Cost Encounters: 615.
- The top 1% of encounters accounted for approximately 17.05% of total spending.

**Business Insight:** Healthcare spending was highly concentrated, with a relatively small number of encounters contributing disproportionately to total costs.

### 2. Cost by Encounter Type

- Ambulatory encounters contributed approximately $131.29M in total spending.
- Ambulatory encounters represented approximately 51.48% of total recorded spending.
- Inpatient encounters recorded the highest average cost of approximately $8,766.
- Emergency encounters recorded an average cost of approximately $7,926.

**Business Insight:** Healthcare expenditure varied significantly across encounter types. Ambulatory care contributed the largest share of total spending, while inpatient encounters had the highest average recorded cost.

### 3. Demographic Cost Analysis

- Female average encounter cost: $4,408.26.
- Male average encounter cost: $3,795.23.
- Patients aged 81+ recorded an average encounter cost of $7,495.30.

**Business Insight:** Cost variation was observed across demographic groups. These are descriptive associations and should not be interpreted as demographic causes of higher costs.

### 4. Clinical Utilization Analysis

- Procedure count showed the strongest simple utilization correlation with total healthcare cost at 0.3172.
- Procedure cost showed a strong positive correlation of 0.7366 with total claim cost.
- Total procedure cost was approximately $210.20M.
- Total medication cost was approximately $73.91M.

**Business Insight:** Procedure-related utilization and expenditure were important areas to investigate when understanding healthcare cost variation.

### 5. Payer Analysis

- Uninsured encounters had the highest average cost of $7,455.91.
- Medicaid average cost: $4,915.02.
- Medicare average cost: $3,812.77.
- Uninsured encounters represented approximately 39.82% of total recorded spending.

**Business Insight:** Significant cost variation existed across payer categories. Further investigation should consider utilization, access, and case-mix differences.

### 6. High-Cost Encounter Analysis

- High-cost threshold: $45,209.38.
- Total high-cost encounters: 615.
- Associated spending: $43.52M.
- Average high-cost encounter: $70,766.12.

**Business Insight:** High-cost encounters represented an important segment for further financial and operational investigation.

### 7. Repeat Encounter Analysis

- Total repeat encounters: 22,739.
- Repeat encounter rate: 36.99%.
- Repeat encounter spending: $143.68M.
- Average repeat encounter cost: $6,318.59.
- Average non-repeat encounter cost: $2,875.91.

**Business Insight:** Repeat encounters represented a substantial share of recorded healthcare utilization and spending, making care coordination and follow-up important areas for further investigation.

### 8. Patient Segmentation

- Total Patients: 1,163.
- High-Cost Patients: 12.
- Frequent Users: 119.
- Patients belonging to both segments: 11.
- The top 1% of high-cost patients accounted for approximately $44.67M in spending.

**Business Insight:** A small group of high-cost and frequent users represented an important segment for targeted care coordination and further review.

### 9. Cost Optimization Opportunities

The analysis identified a unique opportunity-pattern pool of approximately $168.33M.

| Opportunity Area | Volume | Associated Spend |
|---|---:|---:|
| High Procedure Intensity | 5,264 encounters | $42.54M |
| 30-Day Repeat Encounters | 22,739 encounters | $143.68M |
| Top 1% High-Cost Patients | 12 patients | $44.67M |
| Unique Opportunity Pool | 27,330 encounters | $168.33M |

**Illustrative Savings Scenarios:**

| Optimization Rate | Potential Savings |
|---|---:|
| 5% | $8.42M |
| 10% | $16.83M |
| 15% | $25.25M |

These are scenario-based estimates, not guaranteed savings. The opportunity pool represents overlapping screening patterns and should not be treated as proven avoidable expenditure.

## 📊 Power BI – Interactive Dashboard Development

Developed a professional six-page Power BI dashboard using the final healthcare analytical dataset.

The dashboard follows a structured business storyline:

**Page 1 – Healthcare Cost Overview**
- Total Healthcare Cost.
- Total Encounters.
- Average Encounter Cost.
- High-Cost Encounters.
- Cost distribution and encounter-type analysis.

**Page 2 – Cost Analysis**
- Cost by encounter type.
- Procedure intensity analysis.
- Average encounter cost.
- Cost driver analysis.

**Page 3 – Utilization & Repeat Encounters**
- Repeat encounter analysis.
- Repeat encounter spending.
- High-cost encounters.
- Procedure utilization.

**Page 4 – Patient Segmentation**
- Total patients.
- High-cost patients.
- Frequent users.
- High-cost and frequent patient segments.

**Page 5 – Provider & Payer Analysis**
- Provider cost comparison.
- Average cost by payer.
- High-cost encounters by payer.
- Uninsured spending analysis.

**Page 6 – Cost Optimization Opportunities**
- Opportunity-pattern spending.
- Repeat encounter cost.
- High procedure cost.
- High-cost patient spending.
- Potential savings scenarios.
- Cost optimization recommendations.

## 📁 Project Structure

```text
Healthcare_Cost_Optimization_Analytics/
│
├── data/
│   ├── Raw_Datasets/
│   ├── Cleaned_Datasets/
│   └── Analytical_Dataset/
│
├── notebooks/
│   ├── 01_Data_Understanding.ipynb
│   ├── 02_Data_Cleaning_Preparation.ipynb
│   ├── 03_Analytical_Dataset_Building.ipynb
│   ├── 04_Exploratory_Data_Analysis.ipynb
│   ├── 05_Statistical_Modeling.ipynb
│   └── 06_Cost_Optimization_Analysis.ipynb
│
├── PowerBI/
│
├── Report/
│
└── README.md
```

## ⚠️ Project Limitations

- The dataset is synthetic and does not represent actual patients or healthcare-system performance.
- High healthcare costs or utilization do not automatically indicate unnecessary care.
- The 30-day repeat encounter measure is a utilization proxy, not a clinically validated preventable-readmission measure.
- Potential savings scenarios are illustrative and require clinical and operational validation.
- Payer differences are not causal without case-mix adjustment.
- Provider comparisons use minimum encounter-volume thresholds.
- Predictive feature importance does not establish causation.
- The project uses USD because the dataset represents a US healthcare context.

## 🏁 Conclusion

This project demonstrates an end-to-end healthcare cost analytics workflow, transforming multiple raw healthcare datasets into a consolidated analytical dataset and generating meaningful business insights.

Through Python-based data cleaning, exploratory data analysis, statistical and predictive modeling, cost optimization analysis, and Power BI dashboard development, the project identified important patterns related to healthcare expenditure, encounter types, patient utilization, procedures, providers, payers, and high-cost patient segments.

The final six-page Power BI dashboard provides an interactive view of healthcare cost performance and potential optimization opportunities.

The project strengthened practical skills in data preparation, data integration, exploratory data analysis, statistical analysis, machine learning, business intelligence, and data-driven decision-making.

## 👩‍💻 Author

**Swetha K**

Aspiring Data Analyst

**Skills:** Python | Pandas | NumPy | Matplotlib | Statistics | Power BI | DAX | Data Analytics

**GitHub:** https://github.com/swe-tha204

---

⭐ If you find this project interesting, feel free to explore the repository!
