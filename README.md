# Analyzing Superstore Sales Performance in Global Retail

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
<img width="4000" height="2250" alt="PowerBi_Project2-1" src="https://github.com/user-attachments/assets/a4942c0b-671f-4c0b-89bf-0eaf8d3c2d99" />

<img width="4000" height="2250" alt="PowerBi_Project2-2" src="https://github.com/user-attachments/assets/ba101249-522a-473d-8144-8a8ba6ae201d" />

### 2️⃣ Define point of view 

<img width="4000" height="2250" alt="PowerBi_Project2-3" src="https://github.com/user-attachments/assets/98aaaee0-1670-4d94-a8a7-8c508401cc67" />

<img width="4000" height="2250" alt="PowerBi_Project2-4" src="https://github.com/user-attachments/assets/52c57f31-1451-4936-a648-c90544af0c58" />

### 3️⃣ Ideate

<img width="4000" height="2250" alt="PowerBi_Project2-5" src="https://github.com/user-attachments/assets/81162885-0c40-4c6b-bdde-6bb578e58c99" />

<img width="4000" height="2250" alt="PowerBi_Project2-6" src="https://github.com/user-attachments/assets/e74f8be6-584a-416c-9453-3c62faf2c38b" />

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
   - Customer count grew from **1303 (2011)** to **1589 (2014)**, with a stable **~1% return rate**. → Indicates **strong customer retention** and consistent service quality over time.

**3. Canada Shows Highest Profit Margin**  
   - **Canada** achieved a **28% profit margin** despite low revenue. **US, EU, and APAC** contributed the highest revenue overall. → Suggests **Canada** has high **profitability potential**, while the **US remains the core market** in terms of scale.

**4. Consumer Segment Leads**  
   - The **Consumer segment** generated **$4.9M**, the highest among all segments, with a stable **11–12% margin**. → Indicates **steady demand** and a key role in **driving overall growth**.

**5. Technology Drives Growth**  
   - **Technology products** generated the highest revenue across all regions. → Suggests **customers have a strong preference** for **tech products** over other categories.

**6. Growth Driven by Existing Customers**  
   - **Customner count** increased only **1%**, but **orders surged 51.7%**; **Average Order Value (AOV)** slightly decreased by **-0.3%**. → Indicates **strong repeat purchase behavior**, with smaller but more frequent orders.

#### 2️⃣ Page 2: Market Analysis Dashboard Preview 
![Analyzing Superstore Sales Performance in Global Retail_page-0002](https://github.com/user-attachments/assets/1ed79463-606d-4ef2-baeb-f8c061c61dd3)

### 📌 Key Findings:

**1. Revenue & Profit Distribution**  
   - Total revenue **$9.48M**, with **APAC ($2.7M)**, **EU ($2.1M)**, and **US ($1.8M)** leading. → **Canada** had the highest **profit margin (28%)**, despite low revenue. **EMEA** and **Africa** underperformed with low revenue and profit margins (~6–12%).

**2. Profit Contribution by Market**  
   - **APAC, EU, and US** contributed the most to profit. → **LATAM** steady (~15%), while **Africa** and **Canada** contributed minimally.

**3. Revenue Growth by Market & Category**  
   - **Canada** saw **+219.5% YoY** growth, especially in **Technology (+63.5%)**. → Emerging markets **EMEA (+183.15%)** and **Africa (+168.25%)** grew rapidly.

 **4. The best Sale Agent**  
   - **Central, South, and EMEA**  is the **top-performing salesperson** with revenue exceeding **$210K**.

**5. Order Volume & Return Rate**  
   - **Central** led in **order volume** and **lowest return rate (~1%)**. → Other regions had stable return rates (1–3%).

#### 3️⃣ Page 3: Product Analysis Dashboard Preview 
![Analyzing Superstore Sales Performance in Global Retail_page-0003](https://github.com/user-attachments/assets/f17db2b9-69f1-443c-b3e7-fba34c140ad3)

### 📌 Key Findings:

**1. Quadrant Analysis by Sub-Category**
- **Copiers** and **Phones** are the leaders with high **revenue** and **strong profit margins**. **Accessories**, **Art**, and **Labels** are **profitable but under-scaled**, showing growth potential. **Chairs**, **Bookcases**, and **Storage** perform well in revenue but have **low profit margins**. **Supplier** and **Furnishings** are underperforming with both **low revenue** and **low margins**.

**2. Revenue and Profit Margin by Sub-Category**
- **Phones ($1.4M)**, **Chairs**, **Copiers**, and **Tables** lead in **revenue**. **Accessories (26%)**, **Labels (23%)**, and **Art (18%)** stand out for **profit margins**. **Tables (-7%)** are underperforming with negative profit margins.

**3. Orders, Customers, and Return Rate by Sub-Category**
- **Storage** leads in **orders (216)** but has low profit margins. **Labels (10%)**, **Fasteners (6%)**, and **Paper (5%)** show high **return rates**, raising potential quality concerns. Categories like **Art** and **Appliances** have **low return rates**, indicating high customer satisfaction.

**4. Revenue Decomposition**
- This revenue dashboard effectively breaks down sales by **segment** and **category** but suffers from **data repetition** and **inconsistent formatting** that reduces clarity

**5. Top 10 Products by Profit**
- **Canon imageCLASS 2200**, **Motorola Smart Phone**, and **Cisco Smart Full Size** top the profit list, mainly from **Technology**. → **Furniture** and **Office Supplies** products lag behind in profitability.

---
## 5. 🔎 Final Conclusion & Recommendations

| **Strategy** | **Insight** | **Recommendation** |
| ------------ | ----------- | ------------------ |
| **🚀 1. Market Expansion Strategy** | - **Canada** has the highest **profit margin (28%)** despite low revenue. <br> - **Africa** and **EMEA** show exceptionally high **revenue growth** (+168% / +183%). <br> - **Oceania** & **Africa** have the highest number of **new customers**. | - **Expand selectively in Canada** to maximize profitability. <br> - **Increase investment in Africa and EMEA** to capture growth. <br> - **Focus promotions in Oceania & Africa** to drive new customer growth. |
| **🛒 2. Product Portfolio Optimization** | - **Technology** leads in both **revenue** and **profit**. <br> - **Accessories**, **Art**, and **Labels** are high-margin but **low-revenue**. <br> - **Suppliers** and **Furnishings** underperform in both **revenue** and **profit**. <br> - **Tables** bring high **revenue** but incur **losses (-7%)**. <br> - **Storage** has high **orders** but **low profit margin**. | - **Scale Technology**, focusing on high-margin products like **Canon Copiers** and **Motorola/Cisco Phones**. <br> - **Market Accessories**, **Art**, and **Labels**, leveraging high margins. <br> - **Consider delisting Suppliers**, **Furnishings**, and **Tables** due to poor performance. <br> - **Review Storage pricing** and costs for better profitability. |
| **👥 3. Customer Strategy**        | - **99.97%** of revenue comes from **existing customers**. <br> - **Oceania** & **Africa** have the largest **new customer base**.                                                      | - **Focus on customer retention** with loyalty and upselling initiatives. <br> - **Expand acquisition efforts in Oceania & Africa** to capture growth potential. |
| **⚙️ 4. Operational Efficiency**   | - **US**, **EU**, and **APAC** show slower growth. <br> - **Central region** leads in **employee productivity** ($2.07M per employee). <br> - **Standard Class** dominates **shipping revenue**. | - **Optimize operations** in mature markets to maintain margins. <br> - **Replicate Central region's model** in other regions. <br> - **Focus on Standard Class shipping** and audit other modes for savings. |
