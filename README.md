# Credit Card Customer & Transaction Dashboard Project Report

**Domain:** Financial Services (Credit Card Analytics)

**Project Type:** Self-Initiated Learning Project

**Tools Used:** PostgreSQL, SQL Scripts, Power BI, DAX

---

### 📃 Problem Statement
Banks and credit card providers often struggle to make timely, data-driven decisions due to scattered transaction and customer data. This results in:

- Poor visibility into revenue trends
- Ineffective customer segmentation
- Delayed response to underperforming regions or cards

**Goal:** To build an interactive BI solution that enables real-time monitoring of key performance metrics, weekly comparisons, and customer segmentation to assist decision-makers.

---

### 💡 Solution Overview

Developed two dashboards using Power BI connected to a PostgreSQL database:

**1- Transaction Dashboard:** Showcases weekly trends and key KPIs like revenue and transaction volume.

**2- Customer Segmentation Dashboard:** Highlights customer behaviors based on demographics, card usage, and location.

---

### ✅ Project Workflow

### 1. Data Collection
- collected open-source datasets simulating credit card customer and transaction data.

- Ensured reliability, column consistency, and availability of key fields like client num, state, revenue, income, etc.

### 2. Data Upload & Structuring (PostgreSQL)
- Used SQL scripts to:
  - Create customer and transaction tables
  - Define data types and constraints 
  - Upload CSV data using COPY command

- Drive Link to SQL Scripts: [https://docs.google.com/document/d/110cCcxli49-adrYy1phB_Zh081uNnczWL7wwGtZUVqQ/edit?usp=sharing]

### 3. Connecting Power BI to PostgreSQL
- Connected via localhost and database name
- Let Power BI auto-detect relationships based on client num
- Verified and reviewed relationships in model view

### 4. Data Transformation (in Power BI)
- Created calculated columns using DAX:
  - Age Group (18–25, 26–35, etc.)
  - Income Group (Low, Medium, High)
  - Week Number for time-based analysis


- Created DAX Measures:
  - Current Weekly Revenue, Previous Week Revenue
  - % Change in RevenueTop 5 States by Revenue



**📈DAX formula used for calculation -**

***Calculated Measure->***

**1. Current_week_revenue:**

Current_week_revenue = 
    CALCULATE( 
    SUM('public cc_detail'[Revenue]),
    
  FILTER(
        
  ALL('public cc_detail'),
        'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])
    )
)






**2. Previos_week_revenue:** 

  Previos_week_revenue = CALCULATE( 
    SUM('public cc_detail'[Revenue]),
    
  FILTER(
    
  ALL('public cc_detail'),
        'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])-1
    )
)






**3. Week NUmber:**
   
  week_num2 = WEEKNUM('public cc_detail'[week_start_date])



***Calculated column->***    

**4. New Column calculated Age group using Switch Function:**

AgeGroup = SWITCH(
    TRUE(),
     'public cust_detail'[customer_age] < 30, "20-30", 
  
  'public cust_detail'[customer_age] >=30 && 'public cust_detail'[customer_age] < 40, "30-40",
  
  'public cust_detail'[customer_age] >= 40 && 'public cust_detail'[customer_age] < 50, "40-50",
  
  'public cust_detail'[customer_age] >= 50 && 'public cust_detail'[customer_age] < 60, "50-60",
  
  'public cust_detail'[customer_age] >= 60, "60+"

  )





**5. New Column Calculated "Income Group" using Switch Function:**

IncomeGroup = SWITCH(
     TRUE(),
     
  'public cust_detail'[income] < 35000, "Low",
     
  'public cust_detail'[income] >= 35000 && 'public cust_detail'[income] < 70000, "Med",
     
  'public cust_detail'[income] >= 70000, "High",
     
  "Unknown")



### 5. Dashboard 1: Transaction Insights
**Key KPIs:**
- Total Revenue
- Total Transaction Amount
- Annual Fees

**Visuals:**
- Cards for KPIs
- Column Charts (Revenue by Category, Card Type, Education)
- Tables (Revenue by Job Role)
- Treemaps (Transaction distribution with slicer)


### 6. Dashboard 2: Customer Segmentation
**Key KPIs:**
- Revenue, Income
- Customer Satisfaction Score (CSS)

**Visuals:**
- Line Charts (Revenue trends by age, gender)
- Treemaps (By Quarter, Card Category, Chip Usage)
- Column Charts (By Marital Status, Education, Income Group, Dependents)
- Slicers (Gender, Week Start Date)
- Tables (Top 5 States, Job vs Revenue)

---

### 🔍 Key Insights Extracted
- **Revenue increased by 28.8%** week-over-week
- **TX, NY, CA** contributed 68% of total revenue
- **Blue & Silver cardholders** made up **93%** of transactions
- **Male customers** generated **₹31M vs. ₹26M** by females
- **Activation rate:** 57.5%, **Delinquency rate:** 6.06%

--- 

### 🔬 Key Learnings
- End-to-end implementation of a business dashboard project
- Use of SQL scripting for structured data import and checks
- Hands-on experience with DAX for business-focused calculations
- Improved understanding of data storytelling and visual design
- Strengthened ability to simulate real-world stakeholder thinking

---

### 📊 Impact & Outcome
This project helped simulate a real-world credit card analytics use case. It supports:
- Performance monitoring across KPIs
- Weekly trend tracking for business decisions
- Customer segmentation for targeted strategy

--- 



**Thank You! Have a great Day.**

