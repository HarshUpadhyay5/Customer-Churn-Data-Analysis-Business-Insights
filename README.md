# Telco Customer Churn Prediction

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Feature Engineering](#feature-engineering)
- [Models and Evaluation](#models-and-evaluation)
- [Key Insights](#key-insights)
- [Business Recommendations](#business-recommendations)
- [Contributing](#contributing)
- [Contact](#contact)

---

## Project Overview
Customer churn is a major challenge for telecom companies, impacting revenue and growth. This project aims to:

- Understand churn drivers using Exploratory Data Analysis (EDA)
- Engineer features to improve model performance
- Train and evaluate machine learning models (Logistic Regression, Random Forest, AdaBoost, etc.) to predict churn
- Provide actionable insights for retention strategies

The analysis is implemented in a Jupyter Notebook (`Churn_Prediction_Analysis.ipynb`) covering data cleaning, visualization, modeling, and interpretation.

---

## Dataset
**Dataset:** `WA_Fn-UseC_-Telco-Customer-Churn.csv`

- **Rows:** 7,043 customers  
- **Columns:** 21 features (numerical & categorical)  
- **Target Variable:** `Churn` (Yes/No) – indicates if a customer left the service  

**Key Features:**
- **Demographics:** gender, SeniorCitizen, Partner, Dependents  
- **Account Info:** tenure, Contract, PaperlessBilling, PaymentMethod, MonthlyCharges, TotalCharges  
- **Services:** PhoneService, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies  

**Data Source:** IBM Sample Data Sets (publicly available)  

> **Note:** Missing values in `TotalCharges` are handled by converting to numeric and dropping NAs (11 rows affected).

---

## Installation
To run the notebook locally:

-1. Clone the repository:
   - `git clone https://github.com/HarshUpadhyay5/telco-churn-prediction.git`
   - `cd telco-churn-prediction`

-2. Install dependencies:
   - `pip install -r requirements.txt`  
   *(If `requirements.txt` is unavailable, install manually: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `xgboost`, `catboost`, `adaboost`)*

-3. Launch Jupyter Notebook:
   - `jupyter notebook Churn_Prediction_Analysis.ipynb`

---

## Usage
-1. Open `Churn_Prediction_Analysis.ipynb` in Jupyter Notebook  
-2. Run cells sequentially for:
   - Data loading & cleaning
   - Exploratory Data Analysis (EDA)
   - Feature engineering
   - Model training & evaluation  
-3. Visualizations are created using Matplotlib and Seaborn  
-4. Models are trained on scaled features with an 80/20 train-test split  
-5. Evaluate models using accuracy, precision, recall, F1-score, and classification reports  

**Example Output (AdaBoost):**

| Metric           | No     | Yes    |
|-----------------|--------|--------|
| Precision       | 0.84   | 0.69   |
| Recall          | 0.92   | 0.50   |
| F1-score        | 0.88   | 0.58   |
| Support         | 1294   | 464    |

**Overall Accuracy:** 80.77%  
**Macro Average:** Precision 0.76 | Recall 0.71 | F1-score 0.73  
**Weighted Average:** Precision 0.80 | Recall 0.81 | F1-score 0.80  

---

## Exploratory Data Analysis (EDA)
- **Churn Rate:** ~26.6% of customers churned  
- Key Visualizations:
  - Churn distribution by contract type (month-to-month has highest churn)
  - Tenure vs. churn (shorter tenure → higher churn)
  - Correlation heatmaps and box plots for numerical features (`MonthlyCharges`, `TotalCharges`)  

**Observations:**  
- Month-to-month contracts, lack of tech support/online security, and high monthly charges increase churn risk

---

## Feature Engineering
- Convert categorical variables to numerical using One-Hot Encoding (e.g., Contract, PaymentMethod)  
- Handle `TotalCharges` as numeric and drop missing values  
- Scale numerical features (`tenure`, `MonthlyCharges`, `TotalCharges`) using StandardScaler  
- Drop irrelevant features like `customerID`  

---

## Models and Evaluation

| Model                     | Accuracy (%) |
|----------------------------|-------------|
| K-Nearest Neighbors (KNN) | 76.00       |
| Decision Tree              | 73.00       |
| Random Forest              | 79.00       |
| AdaBoost                   | 81.00       |
| XGBoost                    | 79.00       |
| CatBoost                   | 79.00       |

- **Best Model:** AdaBoost Classifier (Accuracy: 81%)  
- Metrics focus on **recall for 'Yes' churn class** to minimize false negatives  
- Ensemble models (Random Forest, XGBoost, CatBoost) show robust performance  

---

## Key Insights
- **Churn Drivers:**
  - Month-to-month contracts → higher churn  
  - Short tenure (<12 months) → higher churn risk  
  - Lack of add-ons like online security or tech support → higher churn  

- **Overall Churn Rate:** 26.6%  
- Models predict non-churners more accurately; improving recall for churners is a focus for future work  

---

## Business Recommendations
- **Retention Offers:** Incentivize month-to-month customers to switch to longer contracts  
- **Early Engagement:** Onboarding programs for new customers  
- **High-Risk Monitoring:** Flag short-tenure, high-charge customers for proactive support  
- **Campaign Pilots:** Test loyalty programs or discounts on predicted churners  
- **KPI Tracking:** Monitor churn rates post-implementation to refine strategies  

---

## Contributing
Contributions are welcome!  
-1. Fork the repository  
-2. Create a branch  
-3. Submit a pull request  

> For major changes, open an issue first.

---

## Contact
**Author:** Harsh Upadhyay (Aspiring Data Analyst Intern)  
**Email:** [harshupadhyayofficial5@gmail.com](mailto:harshupadhyayofficial5@gmail.com)  
**GitHub:** [HarshUpadhyay5](https://github.com/HarshUpadhyay5)
