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

- Drive Link to SQL Scripts: [Insert Your Link Here]

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


- All DAX measures will be listed in the appendix of this presentation.




