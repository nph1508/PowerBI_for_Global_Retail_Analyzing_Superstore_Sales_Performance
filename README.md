# Analyzing Superstore Sales Performance in Global Retail | Power BI

<img src="https://github.com/user-attachments/assets/e1583dd2-3b38-453a-b6ab-efd4136d4a42" width="100%" />

**Author:** Nguyễn Phương Huy

**Date:** April 2025

**Tools Used:**  PowerBI

---
## 📑 Table of Contents  
[1. 📌 Background & Overview](#1--background--overview)  
[2. 📂 Dataset Description & Data Structure](#2--dataset-description--data-structure)   
[3. 🧠 Design Thinking Process](#3--design-thinking-process)  
[4. 📊 Key Insights & Visualizations](#4--key-insights--visualizations)  
[5. 🔎 Final Conclusion & Recommendations](#5--final-conclusion--recommendations)

---
## 1. 📌 Background & Overview 

**Objective:**

**📖 What is this project about?**

This project aims to build a **Power BI dashboard** using the *Global Superstore Sales* dataset, which includes data on transactions (**Orders**), sales representatives (**People**), and product returns (**Returns**).
The goal is to provide senior managers with **data-driven insights** to:
 - **Understand current business performance**
 - **Optimize market expansion strategies**
 - **Identify strategic products for growth**
 - **Support better decision-making to drive revenue and ROI**

**👤 Who is this project for?**
 - ✔️ Data analysts & business analysts seeking actionable insights. 
 - ✔️ Marketing and sales teams focusing on product performance and market growth. 
 - ✔️ Route to market team aiming to improve distribution strategies and market reach. 

**❓Business Questions:**
 - ✔️ What is the current performance of Superstore?
 - ✔️ Which markets should Superstore expand into to increase revenue and ROI?
 - ✔️ Which products should be prioritized for strategic growth?

**📊 Project Outcome:**
| Metric               | Current State | Target Improvement |  
|----------------------|---------------|--------------------|  
| Global Return Rate   | 10.7%         | Reduce to 8.5%     |  
| Regional Growth      | APAC +12%     | EU +15%            |  
| Avg. Profit Margin   | 14.3%         | Increase to 16%    |   

---

## 2. 📂 Dataset Description & Data Structure 

### **📌 Data Source** 
- **Source**: Kaggle  
- **Size**: The **Orders** table contains **51,290** records.  
- **Format**: CSV 

### 📊 **Data Structure & Relationships**  

#### 1️⃣ **Tables Used:**  
The dataset consists of **three tables**:  

- 🛒 **Orders** – Contains detailed transaction and customer information (**51,290 records**).

<details>
<summary> <strong>Table 1: Orders</strong></summary>

| Column Name       | Data Type   | Description                              |
|------------------|------------|------------------------------------------|
| `Order ID`      | `VARCHAR`   | Unique identifier for each order.       |
| `Order Date`    | `DATE`      | Date when the order was placed.         |
| `Ship Date`     | `DATE`      | Date when the order was shipped.        |
| `Ship Mode`     | `VARCHAR`   | Shipping method used for delivery.      |
| `Customer ID`   | `VARCHAR`   | Unique identifier for each customer.    |
| `Customer Name` | `VARCHAR`   | Full name of the customer.              |
| `Segment`       | `VARCHAR`   | Customer segment (e.g., Consumer, Corporate). |
| `City`         | `VARCHAR`   | City where the order was placed.        |
| `State`        | `VARCHAR`   | State where the order was placed.       |
| `Country`      | `VARCHAR`   | Country where the order was placed.     |
| `Postal Code`  | `VARCHAR`   | Postal code of the shipping address.    |
| `Market`       | `VARCHAR`   | Market region (e.g., APAC, EMEA).       |
| `Region`       | `VARCHAR`   | Geographical region of the order.       |
| `Product ID`   | `VARCHAR`   | Unique identifier for each product.     |
| `Category`     | `VARCHAR`   | Product category (e.g., Furniture, Office Supplies). |
| `Sub-Category` | `VARCHAR`   | Sub-category of the product.            |
| `Product Name` | `VARCHAR`   | Name of the product ordered.            |
| `Sales`        | `DECIMAL`   | Revenue generated from the order.       |
| `Quantity`     | `INT`       | Number of items ordered.                |
| `Profit`       | `DECIMAL`   | Profit earned from the order.           |

</details>

- 🔄 **Returns** – Stores data on returned orders.

<details>
<summary> <strong>Table 2: Returns</strong></summary>

| Column Name  | Data Type | Description |
|--------------|-----------|-------------|
| `Returned`   | `VARCHAR` | Indicates whether the order was returned (e.g., 'Yes' or 'No'). |
| `Order ID`   | `VARCHAR` | Unique identifier for each order. |

</details>
  
- 👥 **People** – Holds information about sales representatives.

<details>
<summary> <strong>Table 3: People</strong></summary>

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| `Person`    | `VARCHAR` | Name of the salesperson. |
| `Region`    | `VARCHAR` | Geographic region where the salesperson operates. |

</details>

 📸 **Data Model Diagram**

<img width="989" height="659" alt="image" src="https://github.com/user-attachments/assets/10a10afc-b638-4a99-b727-bb3a6e02b77b" />

| **From Table** | **To Table** | **Join Key**   | **Relationship Type** |
|------------|----------|------------|----------------------------------------------------|
| `Orders`   | `People` | `Region`   | Many-to-One (multiple orders belong to one region) |
| `Orders`   | `Returns`| `Order ID` | One-to-One or Left Join (not all orders are returned) |

---

## 3. 🧠 Design Thinking Process 

*A human-centered approach for actionable insights*  

### 1️⃣ Empathize

### 2️⃣ Define point of view 

### 3️⃣ Ideate

### 4️⃣ Prototype and review

This part is in the dashboard

---

## 4. 📊 Key Insights & Visualizations 
### 🔍 Dashboard Preview  
#### 1️⃣ Page 1: Overview Dashboard Preview 
![Analyzing Superstore Sales Performance in Global Retail_page-0001](https://github.com/user-attachments/assets/2354a59d-e233-4d31-83c4-9f546cf0b765)

### 📌 Key Findings:

**1. Revenue & Profit Surged**  
   - Revenue reached **$9.48M** and profit hit **$1.1M**, both increasing **51.3% YoY**. → **Growth** was primarily driven by **increased order volume**, **not by improved operational efficiency** (profit margin remained at **12%**).

**2. Customer Base Expands Steadily**  
   - Customer count grew from **1303 (2011)** to **1501 (2014)**, with a stable **~1% return rate**. → Indicates **strong customer retention** and consistent service quality over time.

**3. Canada Shows Highest Profit Margin**  
   - **Canada** achieved a **28% profit margin** despite low revenue. **US, EU, and APAC** contributed the highest revenue overall. → Suggests **Canada** has high **profitability potential**, while the **US remains the core market** in terms of scale.

**4. Consumer Segment Leads**  
   - The **Consumer segment** generated **$4.9M**, the highest among all segments, with a stable **11–12% margin**. → Indicates **steady demand** and a key role in **driving overall growth**.

**5. Technology Drives Growth**  
   - **Technology products** generated the highest revenue across all regions. → Suggests **customers have a strong preference** for **tech products** over other categories.

**6. Growth Driven by Existing Customers**  
   - **Buyer count** increased only **1%**, but **orders surged 51.7%**; **Average Order Value (AOV)** slightly decreased by **-0.3%**. → Indicates **strong repeat purchase behavior**, with smaller but more frequent orders.

#### 2️⃣ Page 2: Market Analysis Dashboard Preview 
![Analyzing Superstore Sales Performance in Global Retail_page-0002](https://github.com/user-attachments/assets/1ed79463-606d-4ef2-baeb-f8c061c61dd3)

📌 **Analysis 2:**  
- **Observation:**  
  - **Top Markets:** Canada (26.62% profit), EU (12.69%), US (12.47%)  
  - **YoY Growth:** 51.54% market expansion  
  - **Regional Gaps:** EMEA has lowest profit ratio (5.45%)  

- **Recommendation:**  
  - Replicate **Canada’s strategies** in similar markets (e.g., Oceania). 
  - Optimize pricing/costs in **EMEA** to improve margins.

#### 3️⃣ Page 3: Product Analysis Dashboard Preview 
![Analyzing Superstore Sales Performance in Global Retail_page-0003](https://github.com/user-attachments/assets/f17db2b9-69f1-443c-b3e7-fba34c140ad3)

📌 **Analysis 3:**  
- **Observation:**  
  - **Best Performers:** Envelopes (47.96% profit), Phones (high revenue)
  - **Worst Performers:** Tables (4% profit, >12% returns)
  - **Category Trends:** Technology leads in profit ratio (13.99%)

- **Recommendation:**  
  - Scale **high-margin products** (Envelopes, Phones).
  - Discontinue or redesign **low-margin products** (Tables).
 
---
## 5. 🔎 Final Conclusion & Recommendations

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

