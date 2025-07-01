# Power BI for Global Retail: Analyzing Superstore Sales Performance
Author: Nguyễn Phương Huy

Date: 2000-15-08

Tools Used: PowerBI

---
## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)  
3. [🧠 Design Thinking Process](#-design-thinking-process)  
4. [📊 Key Insights & Visualizations](#-key-insights--visualizations)  
5. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

---
## 📌 Background & Overview  

### 🎯 Objective  
Develop a **Global Sales Dashboard** that enables senior management to:  
- Analyze worldwide sales performance and market trends  
- Identify high-potential products and regions for expansion  
- Monitor return rates and sales team effectiveness  

### 🏭 Business Context  
**Data Structure:**  
1. **Orders:** 50,000+ transactions with order details (sales, profit, shipping, etc.)  
2. **People:** Sales personnel assignments by region  
3. **Returns:** 10.7% return rate across all transactions  

**Key Challenges:**  
- Regional performance disparities (APAC vs. EU vs. Americas)  
- High return rates in specific product categories  
- Inconsistent sales performance across teams  

### 👤 Who is this project for?  
✔️ Senior leadership team  
✔️ Regional sales managers  
✔️ Product strategy executives  
✔️ Marketing campaign planners  

### ❓ Business Questions:  
1. **Market Expansion**  
   - Which regions show strongest growth potential?  
   - What product categories dominate each market?  

2. **Product Strategy**  
   - Which products have highest profit margins?  
   - How do return rates vary by product category?  

3. **Sales Performance**  
   - Which sales teams outperform others?  
   - What's the correlation between shipping time and return rates?  

### 📊 Project Outcome:  
| Metric               | Current State | Target Improvement |  
|----------------------|---------------|--------------------|  
| Global Return Rate   | 10.7%         | Reduce to 8.5%     |  
| Regional Growth      | APAC +12%     | EU +15%            |  
| Avg. Profit Margin   | 14.3%         | Increase to 16%    |  

**💡 Innovation Opportunity:** Implement predictive analytics to:  
- Forecast regional demand spikes  
- Identify at-risk orders likely to be returned  
- Optimize product mix by market  

---

## 📂 Dataset Description & Data Structure  

### 📌 Data Source  
- Source: (Mention where the dataset is obtained from—Kaggle, company database, government sources, etc.)  
- Size: (Mention the number of rows & columns)  
- Format: (.csv, .sql, .xlsx, etc.)  

### 📊 Data Structure & Relationships  

#### 1️⃣ Tables Used:  
Mention how many tables are in the dataset.  

#### 2️⃣ Table Schema & Data Snapshot  

Table 1: Products Table  

👉🏻 Insert a screenshot of table schema 

 _Example:_

| Column Name | Data Type | Description |  
|-------------|----------|-------------|  
| Product_ID  | INT      | Unique identifier for each product |  
| Name        | TEXT     | Product name |  
| Category    | TEXT     | Product category |  
| Price       | FLOAT    | Price per unit |  



Table 2: Sales Transactions  

👉🏻 Insert a screenshot of table schema 


 _Example:_

| Column Name    | Data Type | Description |  
|---------------|----------|-------------|  
| Transaction_ID | INT      | Unique identifier for each sale |  
| Product_ID     | INT      | Foreign key linking to Products table |  
| Quantity       | INT      | Number of items sold |  
| Sale_Date      | DATE     | Date of transaction |  


📌If the table is too big, only capture a part of it that contains key metrics you used in the projects or put the table in toggle

#### 3️⃣ Data Relationships:  
Describe the connections between tables—e.g., one-to-many, many-to-many.  

👉🏻 Include a screenshot of Data Modeling to visualize relationships.  

---

## 🧠 Design Thinking Process  

*A human-centered approach for actionable insights*  

### 1️⃣ Empathize - Understand Stakeholder Needs 
**Primary User:** Senior Business & Strategy Manager
**Core Problem::**  
 *"How to identify potential markets and strategic products to expand operations while maximizing profit?"*

**Empathy Map:**  
| Aspect | Insights |  
|--------|----------|  
| **Thinking** | "Profit quality matters more than revenue volume"|  
| **Pains** | No unified view of profitability across dimensions (product/region/time)|  

### 2️⃣ Define - Frame the Problem 
**Northstar Metric:**  
📊 **OEE (Overall Equipment Effectiveness)** - Measures production efficiency through:
- **Availability** (Uptime vs Planned Production Time)  
- **Performance** (Actual vs Maximum Speed)  
- **Quality** (Defect-Free Products)

**Growth Formula:**  OEE = Availability (%) × Performance (%) × Quality (%)


### 3️⃣ Ideate - Dashboard Framework
**Information Architecture:**  
| Layer | Scope | Visualization Examples  |  
|-------|-------|------------------------ |  
| **Layer 0** | Executive Summary	 | OEE Scorecard, Defect Rate, Downtime|  
| **Layer 1** | Machine/Process Level| Downtime Hours, Scrap Rate by Station |  

**Dashboard Structure:**
1. **Overview Page:** Key OEE metrics (78.46%) with KPI alerts
2. **Analytics Page:** Granular performance breakdown by product line/machine

### 4️⃣ Prototype (Design Iterations)
Key Features Implemented:
- ✅ Dynamic OEE Breakdown Wheel
- ✅ Machine Status Traffic Light System
- ✅ Interactive Downtime Pareto Chart
- ✅ Shift Comparison Matrix  

### 5️⃣ Validate (User Testing)
**Feedback Implementation:**  
- Improved color contrast for color-blind users 
- Added export functionality for reports
- Simplified navigation between hierarchy levels
  
> Iterative Improvement: Conducted 3 sprint cycles with stakeholder reviews to refine the final solution

---

## ⚒️ Main Process

1️⃣ Data Cleaning & Preprocessing  
2️⃣ Exploratory Data Analysis (EDA)  
3️⃣ SQL/ Python Analysis 

- In each step, show your Code

- Include query/ code execution screenshots or result samples

- Explain its purpose and its findings

4️⃣ Power BI Visualization  (applicable for PBI Projects)

---

## 📊 Key Insights & Visualizations  
### 🔍 Dashboard Preview  
#### 1️⃣ Page 1: Manufacturing Overview Dashboard  
 ![Project3_NgPhuongHuy_page-0001](https://github.com/user-attachments/assets/9be82d5c-56c8-41bf-9b59-79ddb48f5a24)

📌 **Analysis:**  
- **Observation:**  
  - Plant-wide OEE at **78.46%** with significant location variance (19%-49%)  
  - 12-month trend shows July dip (aligns with maintenance period)  
  - Road products outperform Mountain lines by **12-18% OEE**  

- **Recommendation:**  
  - Investigate best practices at top-performing location (49%)  
  - Schedule preventive maintenance during low season  
  - Cross-train teams between Road/Mountain lines  

#### 2️⃣ Page 2: Quality & Performance Dashboard  
 ![Project3_NgPhuongHuy_page-0002](https://github.com/user-attachments/assets/e3007d2d-b108-4ac3-a698-24a5a724dbc6)
 
📌 **Analysis:**  
- **Observation:**  
  - Paint process failures account for **32%** of total scrap  
  - HL Mountain Frame has highest downtime (**129,168h**)  
  - Strong correlation: 57.8% scrap rate → 1,440h downtime  

- **Recommendation:**  
  - Implement paint process audit for HL Mountain line  
  - Redesign drill size QC checks (top scrap reason)  
  - Prioritize maintenance for high-downtime assemblies
 
---
## 🔎 Final Conclusion & Recommendations  

👉🏻 Based on the OEE and quality analysis, we recommend the **Production Leadership Team** to prioritize these actions:  

📌 **Key Takeaways:**  
✔️ **Immediate Quality Intervention**  
- Address paint process failures (32% of scrap) through equipment calibration and operator retraining  
- Implement mandatory drill size checks for HL Mountain Frame line (57.8% defect correlation)  

✔️ **OEE Improvement Plan**  
- Replicate Road-150 production methods (90.17% OEE) to underperforming lines  
- Focus on location with 19% OEE through cross-training and process benchmarking  

✔️ **Downtime Reduction**  
- Schedule preventive maintenance during low season (July trend dip)  
- Optimize HL Mountain Frame assembly (129,168h downtime) using Lean methodologies  

> 🚀 **Next Steps:** Establish a 30-60-90 day action plan with weekly OEE tracking and scrap rate alerts
