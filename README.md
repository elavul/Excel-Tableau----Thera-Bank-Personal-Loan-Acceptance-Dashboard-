# Excel-Tableau----SaaS-Revenue-Churn-Dashboard-Thera Bank

 
![Tableau](https://img.shields.io/badge/-Tableau-E97627?style=for-the-badge&logo=tableau&logoColor=white)
![Excel](https://img.shields.io/badge/-Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)

Thera Bank is aiming to grow its base of *asset customers* (i.e., borrowers) since most of its current customers are *liability customers* (depositors). The bank earns more through interest on loans, so it wants to convert depositors into personal loan takers. A previous marketing campaign had a 9% conversion rate, which has encouraged further targeted efforts to increase loan adoption with minimal costs.

### 📚 Table of Contents

 [🎯 Aims of the Project](#-aims-of-the-project) <br>
 [🗂️ Introducing the Dataset](#️-introducing-the-dataset)   <br>
 [🧹 Pre-Analysis Steps](#-pre-analysis-steps)   <br>
 [🎯 Key Insights](#-key-insights) <br>
 [💼 Final thoughts & business initiatives](#-final-thoughts--business-initiatives) <br>
 [⚠️ Challenges & Limitations](#-challenges--limitations) <br>
 [🚀 What is Next](#-what-is-next)
 > *“Data by itself is silent. Ask it the right questions, and it tells a story.”*
<details>
<summary><strong>📌 </strong></summary></details>


### 🎯 Aims of the Project:

In this project I acted as the data analyst for the Thera Bank company. My goal was to:
- Help the bank identify which customers are more likely to accept a personal loan.

* Use this to make marketing more targeted and cost-effective. 

 Show how a company is growing (or struggling) with its recurring revenue, churn, and customer retention, using clean visuals and actionable insights.
Help the bank identify which customers are more likely to accept a personal loan.

Use this to make marketing more targeted and cost-effective

---

#### **Business Goal:**

* Build a **predictive model** to identify which liability customers are most likely to accept a **personal loan**.
* This model will help improve the **success rate of marketing campaigns** while **reducing overall costs**.

The main goal of this dataset is to:

Predict which customers are likely to accept a personal loan offer.

Help the bank target the right customers in future marketing campaigns, to save money and increase success rates.

This is a classification problem because the target variable (whether a customer accepted a personal loan) is binary (0 = No, 1 = Yes).
---



### 🚀 Tools used:
Data wrangling	Excel  (or Python/Pandas if you're comfortable) <br>
Dashboard building	Tableau Public (best choice for visual + interactivity)   <br>
Data cleaning (optional advanced)	Python, Jupyter Notebook  <br>
Tableau -  Final interactive dashboard with KPIs 



---

#### ### 🗂️ Introducing the Dataset:
📦 Dataset:
Imported from Kaggle.com: https://www.kaggle.com/datasets/itsmesunil/bank-loan-modelling/data

The dataset contains information about customers and their financial behavior. The main **target variable** is:

* **Personal Loan**: Whether the customer accepted the loan offer during the last campaign (1 = Yes, 0 = No)

#### **Features (Columns):**

| Column                 | Description                                                     |
| ---------------------- | --------------------------------------------------------------- |
| **ID**                 | Unique customer ID                                              |
| **Age**                | Age in years                                                    |
| **Experience**         | Years of professional experience                                |
| **Income**             | Annual income (\$000)                                           |
| **ZIPCode**            | Customer’s residential ZIP code                                 |
| **Family**             | Family size                                                     |
| **CCAvg**              | Avg. monthly credit card spending (\$000)                       |
| **Education**          | Education level (1 = Undergrad, 2 = Graduate, 3 = Professional) |
| **Mortgage**           | Value of house mortgage if any (\$000)                          |
| **Personal Loan**      | Did this customer accept the personal loan offered in the last campaign?|
| **Securities Account** | Does the customer have a securities account with the bank? (0/1)|
| **CD Account**         | Does the customer have a Certificate of Deposit account? (0/1)  |
| **Online**             | Uses internet banking? (0/1)                                    |
| **CreditCard**         | Does the customer use a credit card issued by UniversalBank? (0/1)|

 <img width="1293" height="799" alt="Screenshot 2025-08-10 223810" src="https://github.com/user-attachments/assets/af290b4e-3024-4eb4-a409-d03060ba80dc" />

---

#### **Inspiration & Use Case:**

* **Exploratory Analysis**: Understand how various features like income, credit card usage, or education level affect loan adoption.

* **Business Impact**: More efficient and cost-effective targeting in future campaigns.

Would you like help exploring the data or building the predictive model next?

### 🧹 Pre-Analysis Steps:
🎯 Methods I Used for Analysis:   </strong> </summary> 

- Exploratory Data Analysis & cleaning??? (EDA): Investigated data structure, table relationships, and schema to understand the database.
- 
- Create a Pivot table to analyse how many people - This tells you how many customers accepted the loan, and what % they represent.
Understand the distribution of the target variable:

How many customers accepted the loan vs. how many did not?

What’s the percentage of loan takers?


 ### Analysis 
 1. We create a pivot tabel to see how many customers accepted the loan offered in the last campaign, and what % they represent 
<img width="450" height="108" alt="image" src="https://github.com/user-attachments/assets/1132344d-c50d-4f1a-8a76-4a01f2b992e3" />
<br>
2. Create an additional pivot table to analyse which income groups are more or less likely to accept personal loans, if there are any trends between income level and loan acceptance rates
Personal Loan Acceptance by Income Group.
 <img width="747" height="385" alt="image" src="https://github.com/user-attachments/assets/3c374e5b-2467-4107-b9c4-844f79596e5c" />

The trends between income level and loan acceptance rate - This might suggest that loan acceptance increases with income - possibly due to better creditworthiness or greater borrowing confidence.
 
##### Insights:
#####1. 
. High-Income Groups Are More Likely to Accept Loans
In Income Group 100–149:

Only 11% of customers rejected the loan.

But 4.38% accepted — much higher acceptance rate compared to lower income brackets.

They make up 15.38% of the total customer base.

Income Group 150–199:

Equal % of people accepted and rejected the loan (4.34% each).

That means 50% acceptance rate — very high!

✅ Insight: Loan acceptance rate increases significantly with income, especially starting from 100+ income brackets.
Insight: Lower-income customers are not accepting personal loans at all. Could be due to lack of eligibility, interest, or need.

#####2.Total Customer distribution:

