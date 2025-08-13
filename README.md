# Thera Bank – Personal Loan Acceptance Dashboard
(Customer Profiling + Targeting Strategy)

 
![Tableau](https://img.shields.io/badge/-Tableau-E97627?style=for-the-badge&logo=tableau&logoColor=white)
![Excel](https://img.shields.io/badge/-Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)

Thera Bank, with a large depositor base, aims to grow its loan portfolio by converting liability customers into asset (loan) customers. A prior campaign achieved a 9% conversion rate, prompting the need for more refined targeting to improve results while reducing costs. 

This project uses data analysis and visualisation to explore customer behavior and identify patterns among those who accepted a personal loan in a previous campaign. It delivers strategic insights and a dashboard that highlights actionable segments for future marketing efforts.

---
 [🎯 Aims of the Project](#-aims-of-the-project) <br>
 [Business Goal](#-business-goal) <br>
  [🚀 Tools used](#-tools-used) <br>
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

In this project I acted as the data analyst for the Thera Bank. My goal was to:
- Identify customers with the **highest probability** of accepting personal loan offers.
- Optimize future marketing campaigns through **segmentation and data-driven targeting**.
- Build clear, visual dashboards for communicating key metrics and campaign performance.
- Provide actionable insights to improve customer conversion and **marketing ROI**.

---

#### **Business Goal:**

- Build a **predictive profile** of potential loan customers using existing campaign data.
- Reduce unnecessary marketing spend by focusing on **high-value, high-probability leads**.
- Improve **campaign success rate** using segmented strategies.

- Improve marketing ROI by targeting high-probability customers.
- Avoid wasting budget on uninterested or unqualified customers.
- Use insights to build a reliable, scalable classification model.


This is a **binary classification problem**:  
> **Target Variable**: `Personal Loan` → (1 = Accepted, 0 = Declined)



### 🚀 Tools used:
| Task                         | Tool Used                     |
|------------------------------|-------------------------------|
| Data Cleaning & EDA         | Excel                         |
| Dashboard & Visualization   | Tableau Public                |
| Data Source                 | [Kaggle Dataset](https://www.kaggle.com/datasets/itsmesunil/bank-loan-modelling/data) |



### 🗂️ Introducing the Dataset:
The dataset contains demographic and financial attributes of 5,000 Thera Bank customers. The goal is to identify patterns among those who accepted a personal loan during a previous campaign

The dataset contains information about customers and their financial behavior. The main **target variable** is:
* **Personal Loan**: Whether the customer accepted the loan offer during the last campaign (1 = Yes, 0 = No)

<details><summary>#### **Features (Columns):**</summary>

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

- A Certificate of Deposit is a type of savings account offered by banks that offers a higher interest rate in exchange for the customer agreeing to keep the money deposited for a fixed period, such as 6 months, 1 year, 5 years, etc.

I also added **additional helper columns** to the dataset, particularly where certain variables needed to be **binned or grouped** to support a more straightforward and meaningful analysis.

This allowed for:
- Cleaner segmentation (e.g., income ranges, age brackets)
- Easier trend identification across categorical variables
- Improved clarity in pivot tables and visualizations

</details>

 <img width="1293" height="799" alt="Screenshot 2025-08-10 223810" src="https://github.com/user-attachments/assets/af290b4e-3024-4eb4-a409-d03060ba80dc" />

### 🧹 Pre-Analysis Steps:

- Performed **initial data profiling** to assess column types, nulls, and distributions
- Final cleaned dtaset:
- <img width="1778" height="306" alt="image" src="https://github.com/user-attachments/assets/24734d74-5ddd-4929-9c40-280d87009515" />

----
### 🧭 Variable Prioritization Strategy (Based on Correlation)
- Focused on **loan response rate** across different customer attributes
- Identified patterns in **income**, **education**, **online banking**, and **credit card usage**
- 
Before diving into pivot tables and EDA, I used a correlation matrix to quickly identify which features had a meaningful relationship with our target: Loan Acceptance.

This helped me:

- Focus efforts on top predictors like **Annual Income**, **CCAvg**, and **CD Account**
- Ignore low-signal variables like **Age** and **Family Size**
- Avoid multicollinearity by choosing between strongly linked variables like **Income vs. CCAvg**

<img width="977" height="679" alt="image" src="https://github.com/user-attachments/assets/c788cb24-103c-488a-8606-91fcfee3a3f1" />
<img width="974" height="217" alt="image" src="https://github.com/user-attachments/assets/ed785391-4d35-4fc4-995b-c0e8a5df3a3b" />


----
##  Exploratory Data Analysis (EDA)
---
#### Initial Pivot Table: Loan Acceptance Overview

Firstly, I created a pivot table to analyze how many customers accepted the personal loan offered during the last campaign, and what **percentage** they represent within the total customer base.

</details>
<img width="870" height="183" alt="image" src="https://github.com/user-attachments/assets/bc89f306-5892-4b3a-90f9-e82d3812c9f1" />

<br>
 **Overall acceptance rate** = 9.60%
 <br>
- Highly imbalanced data — needs attention in modeling phase
<br>
----

#### Income Groups vs Loan Acceptance:
Afterward, I created an additional pivot table to analyze and compare which income groups are more or less likely to accept personal loans, and to identify trends between income level and loan acceptance rates.

<img width="965" height="575" alt="image" src="https://github.com/user-attachments/assets/05ad7369-d288-41cd-a5ac-57ea73870f0e" />
The trends between income level and loan acceptance rate - 

##### Key Trends Observed:

- Customers with **income > \$100K**, especially the **150–199K income group** (with **50% loan acceptance rate**), showed **significantly higher acceptance rates**.
  - This suggests a strong correlation between **income level and willingness or ability to take out loans**.
  - Potential drivers: **greater creditworthiness**, **financial confidence**, or **eligibility**.

- On the other hand, customers in **lower income groups** show **very low or no loan acceptance**.
  - This may be due to **lack of eligibility**, **limited need**, or **financial constraints**.

..............

<details>
<summary>In-depth Analysis:</summary>

#### 🔹 Income Group: 100–149K
- Only **11%** of customers rejected the loan.
- **4.38%** accepted — a much higher acceptance rate compared to lower income brackets.
- This group represents **15.38%** of the total customer base.

#### 🔹 Income Group: 150–199K
- Equal percentages of customers **accepted and rejected** the loan (**4.34%** each).
- This implies a **50% acceptance rate**, which is **very high** relative to other groups.

#### 🔹 Middle-Income Group: 70–99K
- This group is starting to show interest in loans:
  - **0.74% acceptance** vs **21% rejection**.
- While still low in absolute terms, it’s a **significant improvement** over lower-income brackets.

#### 🔹 High-Income Group: >200K
- Very few customers in this group (**only 19 total**), making up just **0.38%** of the customer base.
- Despite high income, **loan uptake is minimal**.
  - Possible reasons: these customers may **not need personal loans**, or it may be a **small, niche segment**.

</details>

------
#### Education Levels vs Personal Loan Acceptance:
<img width="1167" height="450" alt="image" src="https://github.com/user-attachments/assets/78f25dc2-96a6-47e9-9cb3-ed14a2944dc9" />
 <br>
- Loan acceptance increases with education level as education level 3(Advanced/Professional) has the highest acceptance rate with 13.69%, closely followed by Level 2 (Graduate) with 11.52%.

🎯 Key Insight Worth Investigating:

- Customers with **only an Undergraduate degree** make up a significant portion of the overall customer base — **40.06% (2,003 out of 5,000)**.
- However, only **4.71% (93)** of them accepted a loan during the last campaign.

> This stark contrast suggests a potential barrier to loan adoption among undergraduates — possibly due to **lower income**, **credit constraints**, or **limited financial literacy**.

- It would be valuable to investigate:
  - Whether **high-income undergraduates** with strong digital and financial understanding are still avoiding loans.
  - If **younger undergraduates** are more open to taking out loans compared to older ones.


#### Education Levels + Online Banking vs Personal Loan Acceptance

<img width="1064" height="435" alt="image" src="https://github.com/user-attachments/assets/722fc81f-696e-4c57-bfbf-226822abe147" />

🎯 Observation:
- A similar trend is observed here: while customers with **only an Undergraduate degree** make up the **largest group**, they also show the **lowest loan acceptance rate**.
- Next, we’ll explore this trend in more detail to understand the underlying drivers.


#### 🧑‍🎓 Undergrad + Income + Age Insights:

While the overall data shows undergrads as poor targets, adding income, age, and tenure reveals that some subgroups of undergrads are actually strong prospects. Let's dive deeper and investigate and explore if there is a corelation between the family size, education and loan acceptance:
<img width="1049" height="752" alt="image" src="https://github.com/user-attachments/assets/3d891fdf-96db-448c-8df1-636d7323e7ed" />

📌 Insights:

**Loan acceptance is strongly correlated with income above $100K**, particularly for customers aged **31–60**.
   - When targeting customers with **Undergraduate degrees**, focus only on those earning **over $100K** and falling within the **31–60 age range**.
   - **Family sizes of 3–4 members** are most common among loan accepters in this segment.

🎯 To validate this pattern across educational backgrounds, apply a filter for customers with **Level 2 (Graduate degrees)** and assess whether the same trend holds, especially within the same income and age brackets.

<br>
<img width="467" height="292" alt="image" src="https://github.com/user-attachments/assets/65a38716-1104-49ce-b00a-4ab76f3cbe26" />
<br>
<img width="800" height="544" alt="image" src="https://github.com/user-attachments/assets/9022f42b-b7a4-404e-8d30-68423cb481f8" />
<br>
Insights:<br>

- Previous data indicates that customers with a **Graduate degree** have a **loan acceptance rate of 11.52%**.

- The current table reinforces earlier insights:
  - The **majority of loans** are taken by customers with **high incomes ($100K–199K)**.
  - These customers are primarily aged **31–60**, highlighting mid-career individuals.

- Within this high-income, 31–60 age group:
  - **Loan acceptance is fairly evenly spread across family sizes**.
  - There is a **slight skew toward larger families**, especially in the 100–149K bracket.

- However, as **income increases within the 100–199K range**, a trend emerges:
  - **Family Size 2 becomes increasingly dominant**, suggesting that smaller, higher-income households may be more confident or capable in managing personal loans.


<details><summary> More insights: </summary>

🔹Income Groups 100–149K and 150–199K account for 167 out of 182 total loan acceptances — over 91.7% of all accepted loans.<br>
🔹Family Size of 2 is Overrepresented in Loan Acceptance: <br>
🔹🔹Family Size 4: 48 accepted loans (26.4%)<br><br>
🔹🔹Family Size 3: 44 accepted loans (24.2%)<br>
🔹🔹Family Size 2: 50 accepted loans (27.5%)<br>
</details>

---

#### Age Group vs Personal Loan Acceptance:

<img width="389" height="148" alt="image" src="https://github.com/user-attachments/assets/7ef98cce-7d30-4c0c-bb79-02a679c4d76c" />
<img width="527" height="696" alt="image" src="https://github.com/user-attachments/assets/925696a3-ab2c-4b65-b5aa-dde8f84f2eb8" />

------
#### Age Group vs Income Group vs Personal Loan Acceptance:

#### CCAvg vs Personal Loan Acceptance:
<img width="406" height="129" alt="image" src="https://github.com/user-attachments/assets/0485349b-b80d-4ba7-902e-323876f4ca35" />

- Higher credit card spending correlates with higher loan interest
- Too low = low financial activity
- Too high = potential debt risk

----

##### CD Account + CCAvg + Securities Account vs. Loan Acceptance:
<img width="1307" height="394" alt="image" src="https://github.com/user-attachments/assets/1bad3cc7-7684-4029-8ded-53bb66128eb7" />
- Big credit spenders may be more comfortable with debt, making them warmer leads. 
- Customers with both **CD Accounts + High CCAvg** are highly loan-active
- Multiple financial products signal trust and engagement

---
##### Mortgage vs Loan Acceptance:
<img width="469" height="447" alt="image" src="https://github.com/user-attachments/assets/c4cfe19f-a7c2-4291-8ee0-d13ec8a220b3" />

-----
##### Mortgage vs CCAvg vs Loan Acceptance:
<img width="794" height="410" alt="image" src="https://github.com/user-attachments/assets/fcc98689-e312-4321-8e17-e4bdda70b3c0" />
- Moderate mortgage customers tend to be more open to personal loans
- Mortgage + Credit Activity = solid targeting vector
----

### Correlation Analysis 
Following the exploratory analysis, we computed correlation coefficients to quantitatively assess which variables are most predictive of loan acceptance. Income and credit card spending emerged as the strongest indicators, guiding the creation of our predictive scorecard.

###  Scorecard Model 


Visual Dashboard or Summary Sheet

### 💼 Final Thoughts & Business Initiatives:
📌 Insights
9.6% of total customers accepted the loan.
Income, education, CD accounts, and CCAvg are strongest predictors.
Top 20% income group has >25% acceptance rate.
Customers with CD + high income + high credit card usage are goldmine targets.

-  Focus marketing efforts on:
  - Income > \$100K, ideally $100-$199K
  - Education level 2 or 3 (Graduate/Professional)
  - Age 31–60
  - Online banking users with multiple financial products
-  Avoid targeting:
  - Undergrads with low income (<70K) or young age 
  - Inactive credit users






## ✅ Strategic Recommendations

| Action                              | Rationale                                       |
|-------------------------------------|-------------------------------------------------|
| Target income > \$100K              | Highest acceptance across all segments          |
| Focus on graduates & professionals  | Education is a strong predictor                 |
| Use digital channels (email, online)| Best ROI with educated + online banking users   |
| Segment undergrads by income/age    | Avoid broad targeting—focus on qualified leads  |

---
