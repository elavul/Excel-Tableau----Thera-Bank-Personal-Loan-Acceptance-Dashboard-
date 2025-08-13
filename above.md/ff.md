# 💼 Thera Bank – Personal Loan Acceptance Prediction

![Tableau](https://img.shields.io/badge/-Tableau-E97627?style=for-the-badge&logo=tableau&logoColor=white)
![Excel](https://img.shields.io/badge/-Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Python](https://img.shields.io/badge/-Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

> **Objective**: Identify which customers are most likely to accept a personal loan, enabling Thera Bank to execute highly targeted and cost-effective marketing campaigns.

---

## 📌 Project Summary

Thera Bank, with a large depositor base, aims to grow its loan portfolio by converting liability customers into asset (loan) customers. A prior campaign achieved a 9% conversion rate, prompting the need for more refined targeting to improve results while reducing costs.

This project explores patterns in customer behavior using data analysis and visualization. It delivers strategic insights and a dashboard that highlights actionable segments for future campaigns.

---

## 🧰 Tools & Technologies

| Task                         | Tool Used                     |
|------------------------------|-------------------------------|
| Data Cleaning & EDA         | Excel / Python (Pandas)       |
| Dashboard & Visualization   | Tableau Public                |
| Predictive Modeling         | Python (Scikit-learn)         |
| Data Source                 | [Kaggle Dataset](https://www.kaggle.com/datasets/itsmesunil/bank-loan-modelling/data) |

---

## 🧠 Business Problem

> **Can we predict which liability customers will accept a personal loan offer?**

- Improve marketing ROI by targeting high-probability customers.
- Avoid wasting budget on uninterested or unqualified customers.
- Use insights to build a reliable, scalable classification model.

---

## 📦 Dataset Overview

| Feature            | Description                                              |
|--------------------|----------------------------------------------------------|
| Age                | Customer's age                                           |
| Experience         | Years of professional experience                         |
| Income             | Annual income (\$000)                                    |
| ZIP Code           | Residential location                                     |
| Family             | Family size                                              |
| CCAvg              | Avg. monthly credit card spending (\$000)                |
| Education          | 1 = Undergrad, 2 = Graduate, 3 = Professional            |
| Mortgage           | House mortgage value (\$000)                             |
| Personal Loan      | **Target Variable** – Accepted loan (1 = Yes, 0 = No)    |
| Securities Account | Has securities account (0/1)                             |
| CD Account         | Has Certificate of Deposit account (0/1)                 |
| Online             | Uses internet banking (0/1)                              |
| CreditCard         | Has a bank-issued credit card (0/1)                      |

---

## 📊 Key Analysis & Insights

### 🎯 1. Loan Acceptance Rate

- Only **9.6%** of customers accepted a personal loan.
- This is a **highly imbalanced classification problem**.

---

### 💰 2. Income vs Loan Acceptance

| Income Bracket (\$000) | Loan Acceptance Rate |
|------------------------|----------------------|
| <70                    | Very low (<2%)       |
| 100–149                | 4.38%                |
| 150–199                | **50%** ✅           |
| >200                   | High but small segment |

> ✅ **High-income customers (>$100K) are significantly more likely to accept loans.**

---

### 🎓 3. Education Level Insights

| Education Level     | Acceptance Rate |
|---------------------|------------------|
| Undergrad (1)       | 4.06%            |
| Graduate (2)        | 11.52%           |
| Professional (3)    | **13.69%** ✅    |

> 🎓 **Higher education correlates with higher acceptance.**

---

### 🌐 4. Online Banking + Education

| Segment                                | Acceptance Rate |
|----------------------------------------|-----------------|
| Graduate + Online Banking              | 14.07% ✅       |
| Professional + Online Banking          | 13.69% ✅       |
| Undergrad + Online Banking             | 4.06% ❌       |

> 📱 **Digital tools work best for financially literate (educated) customers.**

---

### 🧑‍🎓 5. Undergrad Strategy: Income + Age Segments

- Undergrads with **Income > \$100K** and **Age 31–60** show strong loan interest.
- Family size of **3–4** correlates with higher acceptance.

---

### 💳 6. Credit Card Spending (CCAvg)

- Moderate to high monthly CC spending (> \$2K) links to higher loan interest.
- Extremely low spenders are unlikely to respond.

---

## 📈 Interactive Dashboard Preview

> 🎯 Built in Tableau: Clean layout with KPI cards, filters, and actionable segments.

🔗 [View Dashboard on Tableau Public](#) *(Insert your Tableau link here)*  
🖼️ *Includes visuals for: income brackets, education levels, online usage, and more.*

---

## ✅ Strategic Recommendations

| Action                              | Rationale                                       |
|-------------------------------------|-------------------------------------------------|
| Target income > \$100K              | Highest acceptance across all segments          |
| Focus on graduates & professionals  | Education is a strong predictor                 |
| Use digital channels (email, online)| Best ROI with educated + online banking users   |
| Segment undergrads by income/age    | Avoid broad targeting—focus on qualified leads  |

---

## 🚧 Limitations

- No access to **credit score**, existing debt, or previous loan history.
- Dataset is **static** from a past campaign.
- Assumes income is accurate and current.

---

## 🚀 Next Steps

- ✅ Train classification model (Random Forest / Logistic Regression)
- ⚖️ Handle class imbalance using **SMOTE** or **class_weight**
- 📊 Score new customers for ongoing campaign targeting
- 🧪 Deploy A/B tests to compare campaign performance vs baseline

---

## 📂 Repository Structure

```bash
├── data/
│   └── thera_bank.csv
├── notebooks/
│   └── eda.ipynb
├── dashboard/
│   └── tableau_dashboard.twbx
├── visuals/
│   └── income_vs_loan.png
├── README.md
