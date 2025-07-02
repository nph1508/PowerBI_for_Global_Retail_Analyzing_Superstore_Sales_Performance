# Analyzing Superstore Sales Performance in Global Retail | Power BI
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
- Source: 
- Size: 
- Format: 

### 📊 Data Structure & Relationships  

📌If the table is too big, only capture a part of it that contains key metrics you used in the projects or put the table in toggle

####  Data Relationships:  
*Visualized connections between tables for the Profit Optimization Dashboard*

 🔗 **Relationship Types**
| Connection | Description | Example |
|------------|-------------|---------|
| **One-to-Many** | Single record in Dim table links to multiple records in Fact table | `Dim_Product` → `Fact_Orders` |
| **Many-to-One** | Multiple Fact records reference one Dim record | `Fact_Orders` → `Dim_Date` |
| **Filter Propagation** | Relationships enable cross-table filtering | Selecting a `Category` filters linked `Products` |

🗂️ **Table Relationships**
1. **`Dim_Date` ↔ `Fact_Orders`**  
   - **Type**: One-to-Many  
   - **Key**: `Order Date` → `Date`  
   - **Purpose**: Analyze profit trends over time  

2. **`Dim_Product` ↔ `Fact_Orders`**  
   - **Type**: One-to-Many  
   - **Key**: `Product ID` → `Product`  
   - **Purpose**: Track profitability by product  

3. **`Dim_Category` ↔ `Dim_Product`**  
   - **Type**: One-to-Many  
   - **Key**: `Category ID` → `Category ID`  
   - **Purpose**: Hierarchical product classification  

4. **`Fact_Orders` ↔ `Fact_Returns`**  
   - **Type**: One-to-One  
   - **Key**: `Order ID` → `Order ID`  
   - **Purpose**: Calculate return rates  

5. **`Dim_PeopleSale` ↔ `Fact_Orders`**  
   - **Type**: One-to-Many  
   - **Key**: `Person` → `Customer Name`  
   - **Purpose**: Regional performance analysis  

 📸 **Data Model Diagram**
<img width="585" alt="datamodeling2" src="https://github.com/user-attachments/assets/e872b470-44bd-405c-9b7a-a4fee57ec447" />

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
| **Thinking** | "Profit quality matters more than revenue volume" |  
| **Pains** | No unified view of profitability across dimensions (product/region/time) |  
| **Gains** | Optimize resource allocation and investment decisions |

**Dataset:**
   - **Fact Tables:** fact_orders, fact_return
   - **Dimension Tables:** dim_product, dim_date, dim_category, dim_subcategory, dim_peoplesale

### 2️⃣ Define - Frame the Problem 
**Northstar Metric:**  
📊 **Profit Ratio** = Net Profit / Total Revenue
   - Why?: Reflects financial efficiency of business decisions. 

**Growth Formula Breakdown:**
Profit Ratio = (SUM(Profit) / SUM(Revenue))  
↓  
Drill-down by: [Product] × [Market] × [Sales Channel]  


### 3️⃣ Ideate - Dashboard Framework
**Information Architecture:**  
| Layer | Scope | Visualization Examples  |  
|-------|-------|------------------------ |  
| **Layer 0** | Executive Summary | Profit Ratio KPI, Revenue vs Profit Waterfall |  
| **Layer 1** | Single-Dimension Analysi | Top/Nth Products by Profit (Bar Chart), Profit Heatmap |
| **Layer 0** | Multi-Dimension Analysis | Market Detail |

**Dashboard Structure:**
1. **Overview Page:**
   - Key Metrics: Profit Ratio (18.5%), YoY Growth
   - Visuals: Geo Map (Profit by Region), Trend Line (Monthly Profit)
2. **Product/Market Page:**
   - Key Metrics: Profit Ratio (18.5%), YoY Growth
   - Visuals: Geo Map (Profit by Region), Trend Line (Monthly Profit)
3. **Detail Page:**
   - Visuals: Geo Map (Profit by Region), Trend Line (Monthly Profit)
   
### 4️⃣ Prototype (Design Iterations)
Key Features Implemented:
- ✅ Dynamic Profit Matrix: Interactive cross-filtering (Product × Market)
- ✅ Drill-Through: From overview to granular data
- ✅ Alert System: Highlight products with profit margin < 10%

### 5️⃣ Review & Iterate
**Improvements Across Versions:**  
| Version | Key Changes |
|-------- |------------ |
| V1      |	Added industry benchmarks to KPI cards |
| V2      |	Simplified tooltip formatting (currency units) |
| V3      |	Enabled PDF export per page |
  
> Iteration Insight: *"After testing, users requested a new comparison feature: Online vs. Offline sales profitability. Revisited Empathize stage to refine requirements."*

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
#### 1️⃣ Page 1: Overview Dashboard Preview 
![DAC K35 Project2_NguyenPhuongHuy_page-0001](https://github.com/user-attachments/assets/4a744f57-faf9-49d4-8445-5b1b3c1f5449)

📌 **Analysis 1:**  
- **Observation:**  
  - **Profit Ratio:** 11.61% overall, with Canada leading (26.62%) 
  - **Return Rate:** 4.68% globally, highest in EU (6.18%) 
  - **Sales Trend:** Steady growth from 2011-2014, with seasonal dips in mid-year 

- **Recommendation:**  
  - Prioritize **Canada market** for high-profit campaigns. 
  - Investigate **EU return rates** for product quality issues.    

#### 2️⃣ Page 2: Market Analysis Dashboard Preview 
![DAC K35 Project2_NguyenPhuongHuy_page-0002](https://github.com/user-attachments/assets/8db6a01c-cc95-457d-8bac-e9e701712199)

📌 **Analysis 2:**  
- **Observation:**  
  - **Top Markets:** Canada (26.62% profit), EU (12.69%), US (12.47%)  
  - **YoY Growth:** 51.54% market expansion  
  - **Regional Gaps:** EMEA has lowest profit ratio (5.45%)  

- **Recommendation:**  
  - Replicate **Canada’s strategies** in similar markets (e.g., Oceania). 
  - Optimize pricing/costs in **EMEA** to improve margins.

#### 3️⃣ Page 3: Product Analysis Dashboard Preview 
![DAC K35 Project2_NguyenPhuongHuy_page-0003](https://github.com/user-attachments/assets/881a94c8-447f-4434-a584-c21cd9f00458)

📌 **Analysis 3:**  
- **Observation:**  
  - **Best Performers:** Envelopes (47.96% profit), Phones (high revenue)
  - **Worst Performers:** Tables (4% profit, >12% returns)
  - **Category Trends:** Technology leads in profit ratio (13.99%)

- **Recommendation:**  
  - Scale **high-margin products** (Envelopes, Phones).
  - Discontinue or redesign **low-margin products** (Tables).
 
---
## 🔎 Final Conclusion & Recommendations  

👉🏻 Based on the insights and findings above, we recommend the **Business Strategy Team** to consider:   

📌 **Key Takeaways:**  
✔️ **Strategic Market Expansion**  
- **Focus**: EU (18% Profit Ratio, 3.5% Return) and US (15% Profit Ratio, 4.2% Return)  
- **Action**: Allocate 60% of marketing budget to these high-potential markets.  

✔️ **Product Portfolio Optimization**  
- **Scale Up**: Phones & Chairs (High Profit, Low Return) → Design bundled offers.  
- **Phase Out**: Tables (4% Profit, >12% Return) → Test redesign before discontinuation.  

✔️ **Risk-Managed Growth**  
- **Stabilize**: APAC (12.16% Profit) and Canada (26.62% Profit) → Maintain current operations.  
- **Experiment**: LATAM/Africa (High Return Rates) → Pilot localized promotions to reduce returns.
  
### 🎯 Strategic Framework:  
| **Strategy**  | **Markets**       | **Products**          | **Budget Allocation** |  
|---------------|-------------------|-----------------------|-----------------------|  
| **Expand**    | EU, US            | Phones, Chairs        | 60%                   |  
| **Stabilize** | APAC, Canada      | Office Supplies       | 30%                   |  
| **Test**      | LATAM, Africa     | Tables (Redesign)     | 10%                   |  

> 💡 **Next Steps**: Monitor Return Rate trends quarterly and adjust product mix accordingly.  

