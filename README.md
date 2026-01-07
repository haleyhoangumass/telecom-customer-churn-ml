# Customer Churn Analysis for Telecom
**Machine Learning for Analytics – SCH-MGMT 655**

## 📌 Project Overview
Customer churn is a critical challenge for subscription-based businesses, especially in the telecom industry where switching costs are low and competition is intense. Retaining existing customers is significantly more cost-effective than acquiring new ones.

This project applies machine learning techniques to **predict customer churn**, **identify key churn drivers**, and **translate model outputs into actionable business strategies** that improve customer retention and lifetime value.

---

## 🎯 Business Objectives
The project is designed to answer three core business questions:

1. **High-Revenue Customer ROI**  
   What is the dollar value of reducing churn among high-revenue customers, and which retention interventions maximize return on investment?

2. **Customer Lifetime Value (CLV)**  
   Which customer segments—based on contract type, tenure, and billing method—contribute most to total lifetime revenue?

3. **Service Bundle Impact**  
   Which service combinations most strongly increase or reduce churn risk?

---

## 📊 Dataset
- **Source:** IBM Telco Customer Churn Dataset  
- **Initial observations:** 7,043 customers  
- **Final observations:** 7,032 customers (after cleaning)  
- **Features:** 21 variables  
  - Demographics (e.g., gender, senior citizen status)
  - Account & billing information (tenure, contract type, payment method)
  - Service subscriptions (internet, security, tech support, streaming)
- **Target variable:** `Churn` (Yes / No)

---

## 🧹 Data Preparation & Exploration
- Removed 11 records with missing `TotalCharges` values (<0.2% of data)
- Classified variables into numerical and categorical groups
- Conducted exploratory data analysis using:
  - Histograms
  - Boxplots
  - Scatterplots
  - Correlation analysis
- Verified absence of severe multicollinearity among predictors

Key findings:
- Churn is heavily concentrated among early-tenure customers
- High monthly charges alone do not guarantee loyalty
- Long-term contracts significantly reduce churn probability

---

## 🤖 Machine Learning Models
Three classification models were implemented and compared:

### 1️⃣ Logistic Regression
- Selected for **interpretability and business insight**
- Stepwise variable selection used to identify key predictors
- Strong generalization performance:
  - Training AUC ≈ 0.85
  - Validation AUC ≈ 0.85
- Optimized cutoff using decile analysis:
  - Final cutoff ≈ 0.29 (top 40% highest-risk customers)

### 2️⃣ Decision Tree
- Prioritized **transparent, rule-based decision-making**
- Tuned using minimum leaf size (tested 300–700)
- Optimal model:
  - Minimum leaf size = 300
  - Test AUC ≈ 0.82
- Produced clear IF–THEN rules suitable for frontline retention teams

### 3️⃣ Neural Network
- Designed to capture **nonlinear relationships and interactions**
- Tested multiple architectures; best model (Net36):
  - Two hidden layers (2 and 7 neurons)
  - AUC ≈ 0.73
- Cutoff optimization significantly improved recall for churn detection

---

## 📈 Model Evaluation & Cutoff Optimization
- Evaluation metrics:
  - ROC AUC
  - Precision
  - Recall
  - F1-score
- Default cutoff (0.50) was suboptimal for churn detection
- Decile-based cutoff selection improved recall and overall model balance
- Business-oriented thresholds were chosen to prioritize churn prevention

---

## 💡 Key Insights
- **Contract type is the strongest churn driver**  
  Month-to-month customers are significantly more likely to churn than customers on 1–2 year contracts.
- **Early tenure is the highest-risk period**  
  Most churn occurs within the first few months of service.
- **Fiber optic customers without support services are high-risk**
- **Online Security and Tech Support act as protective factors**
- **Electronic check payment method is associated with higher churn risk**

---

## 🧠 Business Recommendations
- Convert month-to-month customers to longer-term contracts using targeted incentives
- Strengthen onboarding and early-stage support programs
- Bundle internet services with Online Security and Tech Support
- Focus retention campaigns on early-tenure, high-risk customers
- Deploy decision tree rules in operational dashboards for real-time intervention

---

## 🧪 Tools & Techniques
- Excel (Data Science Toolkit)
- Logistic Regression
- Decision Tree
- Neural Network
- ROC & Decile Analysis
- Business-oriented cutoff optimization

