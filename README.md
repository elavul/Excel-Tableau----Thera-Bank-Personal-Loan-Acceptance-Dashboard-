# Thera Bank – Personal Loan Acceptance Dashboard
(Customer Profiling + Targeting Strategy)

 
![Tableau](https://img.shields.io/badge/-Tableau-E97627?style=for-the-badge&logo=tableau&logoColor=white)
![Excel](https://img.shields.io/badge/-Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)

Thera Bank is aiming to grow its base of *asset customers* (i.e., borrowers) since most of its current customers are *liability customers* (depositors). The bank earns more through interest on loans, so it wants to convert depositors into personal loan takers. A previous marketing campaign had a 9% conversion rate, which has encouraged further targeted efforts to increase loan adoption with minimal costs.
 
This case is about a bank (Thera Bank) whose management wants to explore ways of converting its liability customers to personal loan customers (while retaining them as depositors). A campaign that the bank ran last year for liability customers showed a healthy conversion rate of over 9% success. This has encouraged the retail marketing department to devise campaigns with better target marketing to increase the success ratio with minimal budget.


### 📚 Table of Contents
## 1. Business Objective
## 2. Tools Used
## 3. Dataset Overview
## 4. Exploratory Data Analysis (EDA)
## 5. Key Insights
## 6. Recommendations
## 7. Limitations & Next Steps
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
* 
* Objective: Build a classification model to predict which liability customers are most likely to accept a personal loan, enabling Thera Bank to run cost-effective, targeted marketing campaigns.

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

The dataset contains demographic and financial attributes of 5,000 Thera Bank customers. The goal is to identify patterns among those who accepted a personal loan during a previous campaign

The dataset contains information about customers and their financial behavior. The main **target variable** is:

* **Personal Loan**: Whether the customer accepted the loan offer during the last campaign (1 = Yes, 0 = No)

<details><summary>#### **Features (Columns):**

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

A Certificate of Deposit is a type of savings account offered by banks that offers a higher interest rate in exchange for the customer agreeing to keep the money deposited for a fixed period, such as 6 months, 1 year, 5 years, etc.

</summary></details>

 <img width="1293" height="799" alt="Screenshot 2025-08-10 223810" src="https://github.com/user-attachments/assets/af290b4e-3024-4eb4-a409-d03060ba80dc" />

---

#### **Inspiration & Use Case:**

* **Exploratory Analysis**: Understand how various features like income, credit card usage, or education level affect loan adoption.

* **Business Impact**: More efficient and cost-effective targeting in future campaigns.

Would you like help exploring the data or building the predictive model next?

### 🧹 Pre-Analysis Steps:
🎯 Methods I Used for Analysis:   </strong> </summary> 

- Exploratory Data Analysis & cleaning??? (EDA): Investigated data structure, table relationships, and schema to understand the database.
- <img width="1778" height="306" alt="image" src="https://github.com/user-attachments/assets/24734d74-5ddd-4929-9c40-280d87009515" />

- Create a Pivot table to analyse how many people - This tells you how many customers accepted the loan, and what % they represent.
Understand the distribution of the target variable:

How many customers accepted the loan vs. how many did not?

What’s the percentage of loan takers?


 ### We start by performing EDA: We are going to study and combine some variabels to uncover high-value customer segments
 1. 
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
<img width="663" height="374" alt="image" src="https://github.com/user-attachments/assets/ef01b869-60e7-41d0-8500-1ca824a982d6" /> <br>
Education Level 3(Advanced/Professional) has the Highest Acceptance Rate, closely folowed by Level 2 (Graduate)
🎯 Objective:
The goal of this table is to analyze how education level correlates with acceptance of a personal loan offer.
#### Education Levels + Online Banking vs Personal Loan Acceptance

<img width="1064" height="435" alt="image" src="https://github.com/user-attachments/assets/722fc81f-696e-4c57-bfbf-226822abe147" />


Insights:
 Online banking users with Graduate degrees and Advanced Degrees have high acceptance rates (14.07%, respectively 13.69%). It looks like digital tools only really help people respond better when they already have a good understanding of finances. 
Lowest acceptance, but also largest group: Online users with only Undergrad (4.06%). Possibly due to lower income, lower credit scores. Interesting to investigate if undergrads with high income are still not accepting loans, or if younger undergrands are more willing to take out a loan than older ones.


### . Undergraduates:
While your overall data shows undergrads as poor targets, adding income, age, and tenure reveals that some subgroups of undergrads are actually strong prospects. Let's dive deeper and investigate :

<img width="1049" height="752" alt="image" src="https://github.com/user-attachments/assets/3d891fdf-96db-448c-8df1-636d7323e7ed" />
<br>
Targeting strategy for customers with just undergraduates:
 
 2. <img width="467" height="292" alt="image" src="https://github.com/user-attachments/assets/65a38716-1104-49ce-b00a-4ab76f3cbe26" />
 3. <img width="800" height="544" alt="image" src="https://github.com/user-attachments/assets/9022f42b-b7a4-404e-8d30-68423cb481f8" />
<br>
Marketing :
1. Loan Acceptance is Strongly Linked to Income Above 100K - only target undergrads if income > $100K and in the age range 31-60 years old
2. with 3-4 members

##### Age Group vs Personal Loan Acceptance:

<img width="389" height="148" alt="image" src="https://github.com/user-attachments/assets/7ef98cce-7d30-4c0c-bb79-02a679c4d76c" />
<img width="528" height="491" alt="image" src="https://github.com/user-attachments/assets/db1c296a-3495-4059-a7a3-94b6aad17ac1" />....moistalek
##### Age Group vs Income Group vs Personal Loan Acceptance:

##### CCAvg vs Personal Loan Acceptance:
###### Low Credit Card Balance:
- Better for avoiding debt and maintaining a low credit utilization ratio.
- Helps improve or maintain a healthy credit score.
- Too low a balance may result in missed rewards or lack of credit activity.
###### High Credit Card Balance:
- Can lead to high-interest charges and lower credit score.
- Increases risk of accumulating debt.
- Should be avoided if not manageable.

##### CD Account + CCAvg + Securities Account vs. Loan Acceptance:
<img width="1307" height="394" alt="image" src="https://github.com/user-attachments/assets/1bad3cc7-7684-4029-8ded-53bb66128eb7" />

##### Mortgage vs Loan Acceptance:
<img width="469" height="447" alt="image" src="https://github.com/user-attachments/assets/c4cfe19f-a7c2-4291-8ee0-d13ec8a220b3" />

##### Mortgage vs CCAvg vs Loan Acceptance:
<img width="794" height="410" alt="image" src="https://github.com/user-attachments/assets/fcc98689-e312-4321-8e17-e4bdda70b3c0" />


