# Adidas Middle East Interactive Sales Performance Report
<img width="1650" height="1275" alt="Adidas Sales DashBoard" src="https://github.com/user-attachments/assets/1952ce0b-829d-4717-a270-c3057fa2a46d" />

---
## Executive Summary
This interactive dashboard provides a holistic view of Adidas sales distribution, revenue performance, and overall profitability across Middle Eastern regional markets (Egypt, Iraq, KSA, Lebanon, Oman) from 2023 through 2025. 

Key metrics highlight total transaction volume, channel breakdown (Online, Retail, Outlet, Wholesale), and category performance across Footwear, Apparel, and Accessories.

---

## Key Performance Indicators (KPIs)
* **Total Revenue:** $287,378
* **Total Profit:** $85,070
* **Total Units Sold:** 3,550
* **Total Retail Transactions/Orders:** 1,200

---

## Detailed Data Visualizations & Insights

### 1. Sales Per Store Type (Channel Distribution)
* **Online:** 46% ($133,207) – Primary driver of overall volume and revenue.
* **Retail:** 36% ($102,147) – Strong physical footprint across regional flagship stores.
* **Outlet:** 12% ($33,516) – Clearance and promotional channel sales.
* **Wholesale:** 6% ($18,507) – B2B partner distribution channel.

### 2. Product Profitability Breakdown
* **Top Performers:** Men's Footwear ($28,296 profit) and Women's Footwear ($22,038 profit) are the highest revenue and margin generators.
* **Apparel:** Men's Apparel ($11,960) and Women's Apparel ($9,483) show steady margin contributions.
* **Accessories & Other:** Lower margin volume overall, led by Men's Accessories ($5,461) and Women's Accessories ($4,661).

### 3. Regional Sales Map & Distribution
* **Iraq:** $81,725
* **Egypt:** $86,028
* **Oman:** $69,057
* **Saudi Arabia (KSA):** $32,966
* **Lebanon:** Regional slice included across key outlets.

### 4. Sales Trend by Year & Quarter (2023–2025)
* **2023:** Revenue peaked in Q4 at $9,194 after starting at $5,910 in Q1.
* **2024:** Maintained stable performance around $7,600–$8,016 per quarter with a slight dip in Q3 ($6,100).
* **2025:** Consistent performance through Q3 averaging ~$7,600–$7,892 quarterly.

---

## Dataset Schema Definition

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `Order_ID` | Integer | Unique identifier for each customer transaction |
| `Order_Date` | Datetime | Date of order execution |
| `SKU` | String | Unique product stock keeping unit code |
| `Product_Name` | String | Name of the Adidas merchandise item |
| `Category` | String | Broad product classification (Footwear, Apparel, Accessories) |
| `Region` | String | Geographical market (Egypt, Iraq, KSA, Lebanon, Oman) |
| `Store_Type` | String | Sales channel (Online, Retail, Outlet, Wholesale) |
| `Units_Sold` | Integer | Total quantity of items purchased |
| `Unit_Price` | Float | Price per individual product unit ($) |
| `Discount` | Integer | Percentage discount applied to order (%) |
| `Revenue` | Float | Gross revenue realized after discount ($) |
| `Profit` | Float | Net profit generated from transaction ($) |
| `Customer_Age` | Integer | Age of customer |
| `Gender` | String | Target demographic (Male / Female) |
| `Payment_Method` | String | Mode of payment (Apple Pay, Credit/Debit, NetBanking, PayPal) |

---

## Analytical Conclusions & Recommendations
1. **Focus on E-Commerce:** Online sales account for nearly half of all revenue (46%). Continued investment in regional digital marketing and direct-to-consumer (D2C) logistics will yield high returns.
2. **Double Down on Footwear:** Men's and Women's Footwear combine for over 50% of overall profitability. Maintain healthy stock levels for top footwear lines (e.g., Superstar, Ultraboost).
3. **Regional Expansion in KSA:** KSA currently lags behind Egypt and Iraq in total sales volume; target market expansion and localized promotional campaigns could unlock further revenue in Saudi Arabia.
