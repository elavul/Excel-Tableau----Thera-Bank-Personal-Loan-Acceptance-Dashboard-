 # Thera Bank – Personal Loan Acceptance Dashboard
(Customer Profiling + Targeting Strategy)

 
![Tableau](https://img.shields.io/badge/-Tableau-E97627?style=for-the-badge&logo=tableau&logoColor=white)
![Excel](https://img.shields.io/badge/-Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)

Thera Bank aims to refine its targeting strategies for personal loan offers to improve conversion rates and reduce marketing spend. This project leverages customer profiling to identify high-value segments, using customer data from a previous campaign where only 9% of customers accepted the loan offer. The objective is to create an actionable plan that increases future loan acceptance rates by targeting the most promising customers based on income, education, family size, and credit behaviors.

---
# Table of Contents
1. [Aims of the Project](#aims-of-the-project)  
2. [Business Problem](#business-problem)  
3. [Tools Used](#tools-used)  
4. [Introducing the Dataset](#introducing-the-dataset)  
5. [Data Cleaning & Preprocessing](#data-cleaning-preprocessing)  
6. [What Influences Decisions? Ranking Variables by Correlation](#what-influences-decisions-ranking-variables-by-correlation)  
   - [Correlation Matrix](#correlation-matrix)  
   - [Key Insights](#key-insights)
7. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)  
<details>
  <summary>Correlation explored </summary>
 
  - [Income Groups vs Loan Acceptance](#income-groups-vs-loan-acceptance)  
  - [Education Levels vs Loan Acceptance](#education-levels-vs-loan-acceptance)  
  - [Education + Online Banking vs Loan Acceptance](#education-online-banking-vs-loan-acceptance)  
  - [Undergrad + Income + Age Insights](#undergrad-income-age-insights)  
  - [Age Group vs Loan Acceptance](#age-group-vs-loan-acceptance)  
  - [Credit Card Activity vs Loan Acceptance](#credit-card-activity-vs-loan-acceptance)  
</details>

8. [Scorecard Model](#scorecard-model)  
   - [Predictive Scorecard Approach](#predictive-scorecard-approach)  
   - [Weight Assignments](#weight-assignments)  
9.  [Visual Dashboard](#visual-dashboard)  
10. [Actionable Recommendations](#actionable-recommendations)  
11. [Challenges & Limitations](#challenges-limitations)  
12. [What Is Next](#what-is-next)  
  
> *“Data by itself is silent. Ask it the right questions, and it tells a story.”*

-----

### Business Problem:

The challenge is to optimize marketing efforts for Thera Bank’s personal loan campaign. Previous campaigns achieved only a 9% conversion rate, highlighting a need for a more targeted, data-driven approach to identify potential customers more likely to accept loan offers.

### Aims of the Project:
In this project I acted as a data analyst for the Thera Bank. My goal was to:
- Create a customer segmentation strategy based on profiling variables.
- Focus marketing efforts on the most promising customer segments.
- Enhance marketing ROI by optimizing resource allocation to high-potential customers.

--------------

### Tools used:
| Task                         | Tool Used                     |
|------------------------------|-------------------------------|
| Data Cleaning & EDA         | Excel                         |
| Dashboard & Visualization   | Tableau Public                |
| Data Source                 | [Kaggle Dataset](https://www.kaggle.com/datasets/itsmesunil/bank-loan-modelling/data) |

--------------------

### Introducing the Dataset:
The dataset includes 5,000 customers from Thera Bank, with demographic and financial data. The target variable is whether the customer accepted a personal loan (1 = Yes, 0 = No). Key features influencing loan acceptance include:

Income: Higher income brackets correlate with better loan acceptance rates.

Education: Higher education levels (graduate/professional) are linked with better acceptance rates.

Family Size: Larger families show higher loan acceptance rates.

Credit Behavior: Credit card spending and mortgage status help determine financial stability.

<details><summary> **All features (Columns):**</summary>

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


</details>

 <img width="1293" height="799" alt="Screenshot 2025-08-10 223810" src="https://github.com/user-attachments/assets/af290b4e-3024-4eb4-a409-d03060ba80dc" />

---

### Data Cleaning & Preprocessing: 

Data Cleaning & Transformation:
The dataset required initial profiling to handle missing values, outliers, and ensure consistency. 

  <img width="1778" height="306" alt="image" src="https://github.com/user-attachments/assets/24734d74-5ddd-4929-9c40-280d87009515" />

<details><summary>additional helper columns</summary>
I created helper columns to segment customers into meaningful groups based on income and age, making the analysis easier to interpret. For example:
 
 - Income was binned into ranges to identify key brackets. 
  - Age was categorized into brackets to evaluate different age group behaviors. <br>
This ensured that the data was ready for segmentation analysis, helping us understand how different groups respond to loan offers

</details>

----
### What Influences Decisions? Ranking Variables by Correlation (Heatmap)
 
Before diving into pivot tables and EDA, I used a correlation matrix to quickly identify which features had a meaningful relationship with our target: Loan Acceptance.

<img width="977" height="679" alt="image" src="https://github.com/user-attachments/assets/c788cb24-103c-488a-8606-91fcfee3a3f1" />
<img width="974" height="217" alt="image" src="https://github.com/user-attachments/assets/ed785391-4d35-4fc4-995b-c0e8a5df3a3b" />


---

##  Exploratory Data Analysis (EDA)
This helped me to:
- Focused on **loan response rates** across different customer attributes
- Identify patterns in **income**, **education**, **online banking**, and **credit card usage**
---
#### Initial Pivot Table: Loan Acceptance Overview

Firstly, I created a pivot table to analyze how many customers accepted the personal loan offered during the last campaign, and what **percentage** they represent within the total customer base.

</details>
<img width="870" height="183" alt="image" src="https://github.com/user-attachments/assets/bc89f306-5892-4b3a-90f9-e82d3812c9f1" />

<br>

Out of 5,000 customers, only 9.6% accepted a loan offer. This low conversion rate indicates that a large portion of the customer base is not being properly targeted. Therefore, we need to explore customer attributes and identify patterns that will allow us to improve future targeting.

-------

#### Income Groups vs Loan Acceptance:
Afterward, I created an additional pivot table to analyze and compare which income groups are more or less likely to accept personal loans, and to identify trends between income level and loan acceptance rates.

<img width="965" height="575" alt="image" src="https://github.com/user-attachments/assets/05ad7369-d288-41cd-a5ac-57ea73870f0e" />

##### Key Trends Observed:
As expected, customers with higher income levels are more likely to accept loans. Notably, customers in the $150K–199K income range show a 50% loan acceptance rate, indicating that financially stable individuals are prime targets. The marketing efforts should focused on customers earning above $100K to maximize conversion. 
On the other hand, customers in **lower income groups** show **very low or no loan acceptance**. This may be due to **lack of eligibility**, **limited need**, or **financial constraints**.

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

--------

#### Education Levels vs Personal Loan Acceptance:
<img width="1167" height="450" alt="image" src="https://github.com/user-attachments/assets/78f25dc2-96a6-47e9-9cb3-ed14a2944dc9" />
 <br>
Customers with graduate or professional education tend to have higher loan acceptance rates (11.52%, 13.69% respectively), possibly due to better financial understanding or higher disposable income. Focusing on graduate and professional degree holders will improve targeting efficiency.

##### Key Insights Worth Investigating:

Customers with only an undergraduate degree make up a significant portion of the overall customer base, representing **40.06%**(2,003 out of 5,000). However, only **4.71%** (93) of these customers accepted a loan during the last campaign. This stark contrast suggests that there may be barriers preventing loan adoption among undergraduate degree holders. Potential factors could include lower income, credit constraints, or limited financial literacy, all of which may limit their ability or willingness to accept loan offers.

-----

#### Education Levels + Online Banking vs Personal Loan Acceptance

<img width="1064" height="435" alt="image" src="https://github.com/user-attachments/assets/722fc81f-696e-4c57-bfbf-226822abe147" />

The same trend is observed here as well, with the customers who have only an undergraduate degree. They represent the largest group but also exhibit the lowest loan acceptance rate. This highlights a potential challenge in targeting this segment. To understand the underlying factors driving this trend, we will explore the issue in more detail in the next phase of analysis.

- It would be valuable to investigate:   
  - Whether **high-income undergraduates** with strong digital and financial understanding are still avoiding loans. 
  - If **younger undergraduates** are more open to taking out loans compared to older ones.
  
----------------

#### 🧑‍🎓 Undergrad + Income + Age Insights:

While the overall data shows undergrads as poor targets, adding income, age, and tenure reveals that some subgroups of undergrads are actually strong prospects. Let's dive deeper and investigate and explore if there is a corelation between the family size, education and loan acceptance.
<img width="1049" height="752" alt="image" src="https://github.com/user-attachments/assets/3d891fdf-96db-448c-8df1-636d7323e7ed" />

##### Key Trends Observed:

Loan acceptance is strongly linked to income above $100K, especially for customers aged 31–60. When targeting customers with an undergraduate degree, the focus should be on those earning over $100K and in the 31–60 age range. Additionally, family sizes of 3–4 members are most common among loan accepters in this group.

--------

🎯 Curious to see if this pattern held across other educational backgrounds, I filtered for customers with Level 2 (Graduate degrees) to check if the trend persisted, particularly within similar income and age groups.

<br>
<img width="467" height="292" alt="image" src="https://github.com/user-attachments/assets/65a38716-1104-49ce-b00a-4ab76f3cbe26" />
<br>
<img width="800" height="544" alt="image" src="https://github.com/user-attachments/assets/9022f42b-b7a4-404e-8d30-68423cb481f8" />
<br>

<details><summary> Key Trends Observed:  </summary>
Previous data shows that customers with a Graduate degree have a loan acceptance rate of 11.52%. The current table reinforces these earlier insights, revealing that the majority of loans are taken by customers with high incomes ($100K–199K). Notably, these customers are primarily aged 31–60, pointing to a trend of mid-career individuals seeking loans.

Within this high-income, 31–60 age group, loan acceptance is fairly evenly spread across family sizes, though there is a slight skew toward larger families, particularly in the $100K–149K income bracket.

As income rises within the $100K–199K range, an interesting trend emerges: **Family Size 2 becomes increasingly dominant**. This suggests that smaller, higher-income households may be more confident or capable in managing personal loans, possibly due to fewer financial obligations or a greater sense of financial stability.
</details>

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

#### Age Group vs Income Group vs Personal Loan Acceptance:

<img width="527" height="696" alt="image" src="https://github.com/user-attachments/assets/925696a3-ab2c-4b65-b5aa-dde8f84f2eb8" />

Customers aged 31-60 show higher loan acceptance rates, especially within the $100K–199K income range. This aligns with mid-career professionals who may have a greater need for personal loans. This further suggests we should prioritize this age group for targeted offers.

------

#### CCAvg vs Personal Loan Acceptance:
<img width="406" height="129" alt="image" src="https://github.com/user-attachments/assets/0485349b-b80d-4ba7-902e-323876f4ca35" />

Higher credit card spending correlates with higher loan acceptance, suggesting that customers who are already engaged in financial activity are more willing to take on personal debt. We should target customers who have a high CCAvg and mortgages, as they may be more open to borrowing.

----
##### CD Account vs Loan Acceptance:
<img width="726" height="107" alt="image" src="https://github.com/user-attachments/assets/3bbea8cd-5dbd-44db-aaa1-e8bfa49aea57" />

##### CD Account + CCAvg + Securities Account vs. Loan Acceptance:
<img width="1307" height="394" alt="image" src="https://github.com/user-attachments/assets/1bad3cc7-7684-4029-8ded-53bb66128eb7" />

Big credit spenders tend to be more comfortable with debt, making them warmer leads for loan offers. Customers who hold both CD Accounts and have a High CCAvg are especially active in taking out loans, suggesting they are more engaged with their finances. Additionally, having multiple financial products indicates a higher level of trust and engagement, making these customers prime targets for loan offers.

---
##### Mortgage vs Loan Acceptance:
<img width="469" height="447" alt="image" src="https://github.com/user-attachments/assets/c4cfe19f-a7c2-4291-8ee0-d13ec8a220b3" />

-----
##### Mortgage vs CCAvg vs Loan Acceptance:
<img width="794" height="410" alt="image" src="https://github.com/user-attachments/assets/fcc98689-e312-4321-8e17-e4bdda70b3c0" />
- Moderate mortgage customers tend to be more open to personal loans
- Mortgage + Credit Activity = solid targeting vector


--------

###  Scorecard Model 
SOON <br>
Income (weight: 40%)

CCAvg (Credit Card Average spending, weight: 20%)

CD Account (weight: 15%)

Education Level (weight: 10%)

Mortgage Value (weight: 5%)

Family Size (weight: 2.5%)  OUT OF 5

Age Group (weight: 5%)

Online Banking (weight: 2.5%)

Customers scoring above a certain threshold will be targeted with loan offers in the next campaign."

Total Score Formula = C4*0.025 + G4*0.4 + K4* 0.025 + M4*0.2 + P4*0.1 + S4*0.05 + X4*0.15+Z4*0.025

Scoring Threshold: top 25%

Score ≥ 60: High-priority targets for loan offers.

Score ≥ 40: Medium-priority targets for loan offers.

Score < 40: Low-priority targets (not ideal for loan offers)


### Visual Dashboard (Tableau)
SOON

--------
### Actionable Recommendations:

Target customers earning >$100K, especially in the $100K–199K range, for the next campaign to maximize conversions.
Focus marketing on customers aged 31-60 with a graduate or professional education, as this group shows the highest interest in personal loans.
Utilize digital channels to reach customers who have multiple financial products, such as credit cards or mortgages.

### Conclusion 

By focusing on high-income, educated customers who are active in financial activities, Thera Bank can significantly increase conversion rates while reducing wasted marketing spend. The insights provided here will help the marketing team target the right audience with the right offer, optimizing both the campaign’s success and ROI.

## What Is Next

- The feature ZIP Code isn’t mentioned after being introduced, which could be a valuable aspect for segmentation (e.g., regional targeting). If it’s not relevant, why include it in the first place?
- a tableau dashboard
