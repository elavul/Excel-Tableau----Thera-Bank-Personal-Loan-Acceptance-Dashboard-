# Excel-Tableau----SaaS-Revenue-Churn-Dashboard-Thera Bank

 
![Tableau](https://img.shields.io/badge/-Tableau-E97627?style=for-the-badge&logo=tableau&logoColor=white)
![Excel](https://img.shields.io/badge/-Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)

Thera Bank is aiming to grow its base of *asset customers* (i.e., borrowers) since most of its current customers are *liability customers* (depositors). The bank earns more through interest on loans, so it wants to convert depositors into personal loan takers. A previous marketing campaign had a 9% conversion rate, which has encouraged further targeted efforts to increase loan adoption with minimal costs.

This case is about a bank (Thera Bank) whose management wants to explore ways of converting its liability customers to personal loan customers (while retaining them as depositors). A campaign that the bank ran last year for liability customers showed a healthy conversion rate of over 9% success. This has encouraged the retail marketing department to devise campaigns with better target marketing to increase the success ratio with minimal budget.

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
- Help the bank identify high-probability customers, minimizing marketing costs and maximizing loan uptake.
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


 ### We start by performing EDA: We are going to study and combine some variabels to uncover high-value customer segments
 1. We create a pivot tabel to see how many customers accepted the loan offered in the last campaign, and what % they represen: 
<img width="457" height="114" alt="image" src="https://github.com/user-attachments/assets/549d7ef5-5cb3-4644-b399-0474234ea7c5" />
The overall acceptance rate: 9.60%
<br>
2. Create an additional pivot table to analyse and compare which income groups are more or less likely to accept personal loans, if there are any trends between income level and loan acceptance rates
Personal Loan Acceptance by Income Group.
<img width="965" height="575" alt="image" src="https://github.com/user-attachments/assets/05ad7369-d288-41cd-a5ac-57ea73870f0e" />
The trends between income level and loan acceptance rate - This might suggest that loan acceptance increases with income - possibly due to better creditworthiness or greater borrowing confidence.
 
##### Insights:
##### 1.High-Income Groups Are More Likely to Accept Loans
In Income Group 100–149:

Only 11% of customers rejected the loan.

But 4.38% accepted — much higher acceptance rate compared to lower income brackets.

They make up 15.38% of the total customer base.

Income Group 150–199:

Equal % of people accepted and rejected the loan (4.34% each).

That means 50% acceptance rate — very high!

✅ Insight: Loan acceptance rate increases significantly with income, especially starting from 100+ income brackets.
Insight: Lower-income customers are not accepting personal loans at all. Could be due to lack of eligibility, interest, or need.

3. Middle-Income Group 70–99 Shows Growing Acceptance
This group is starting to show some interest:

0.74% acceptance vs 21% rejection.

Not very high in % terms but significantly better than lower brackets.
4. High Acceptance in High-Income, but Small Numbers
Group >200 has high income but very few people (only 19 total).

Very small share of customer base (0.38%).

✅ Insight: These customers might not need loans often, or it’s a small niche.
✅ Insight: This income group could be a growing target segment for personal loans.

#### Education Levels vs Personal Loan Acceptance
<img width="663" height="374" alt="image" src="https://github.com/user-attachments/assets/ef01b869-60e7-41d0-8500-1ca824a982d6" />
Education Level 3(Advanced/Professional) has the Highest Acceptance Rate, closely folowed by Level 2 (Graduate)
🎯 Objective:
The goal of this table is to analyze how education level correlates with acceptance of a personal loan offer.

##### Age Group vs Personal Loan Acceptance:

<img width="389" height="148" alt="image" src="https://github.com/user-attachments/assets/7ef98cce-7d30-4c0c-bb79-02a679c4d76c" />
<img width="528" height="491" alt="image" src="https://github.com/user-attachments/assets/db1c296a-3495-4059-a7a3-94b6aad17ac1" />
##### Age Group vs Income Group vs Personal Loan Acceptance:
