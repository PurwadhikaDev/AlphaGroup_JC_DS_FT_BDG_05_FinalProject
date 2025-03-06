# E-commerce Analysis and Seller Churn Prediction Model

**Data Period:** September 2016 - October 2018  

**Contributors:**  
`Glen Valencius Joydi` | `Khrysna Taruna Putra` | `Daffa Dzaky Naufal`

> [!NOTE]
> Presentation Deck : [View the Google Slides Presentation](https://docs.google.com/presentation/d/1RXtLS-ZDupxqhABBnfjqadugFRhJX3UAFSvMGAnbRYs/edit?usp=sharing)<br>
> Streamlit Deploy : [View here](https://olist-seller-churn-dashboard-team-alpha-jcds0508.streamlit.app/)
---

## 1. Business Problem

Olist generates revenue from two primary sources:  
- **Seller subscriptions**  
- **Commissions from sold items**  

To maximize commissions, we need to identify the best-performing products. Since Olist's products come from sellers, finding the top sellers is key to increasing commission-based revenue.

### **Our Approach**
We will focus on three main areas:
1. **Analyzing Olist’s Business Performance**  
2. **Understanding Buyer Preferences in Shopping on Olist**  
3. **Analyzing and modeling which sellers to retain and prioritize for churn prevention**  

## 2. Analysis

### **2.1. Objective: Maximizing Profit & Preventing Losses**  

Our primary goal is to **maximize profit** by identifying the best in each category:  
- 🛍️ **Best Products** – High-demand and high-profit items  
- 👤 **Best Buyers** – Loyal customers with high spending  
- 🏪 **Best Sellers** – Reliable sellers with strong performance  

Additionally, we aim to **prevent profit loss** by detecting and addressing seller churn. Future growth opportunities include identifying **promising cities for expansion** and **high-potential product categories** for investment.  

### **2.2. How Does Olist Generate Revenue?**

- **Commission on Sales:** 18% platform fee and 5% operating cost per item sold.
- **Subscription Fees:** $39 BRL monthly subscription.

### **2.3. Stakeholders**

#### 1. Olist (Company Perspective)  
- **Problem:** Identifying high-performing sellers who are at risk of churning.  
- **Impact:** Loss of revenue **commissions** if top sellers leave or stop selling.  

#### 2. Seller Perspective  
- **Problem:** High-performing sellers may churn if they don't get sales for a long time.  
- **Impact:** Losing **top sellers**, reducing product availability and sales volume.  

#### 3. Buyer Perspective  
- **Problem:** A decline in product variety on Olist Store makes the platform less attractive.  
- **Impact:** **Lower sales revenue** due to reduced customer engagement and purchases.

### **2.4. Analytical Approach**
We will separate our analysis into two major categories:
- **Descriptive Analytics**: Focuses on understanding business, seller, and buyer performance.
- **Inferential Analytics**: Focuses on modeling to predict churn for the next quarter based on seller performance from the last three months.

## 3. Data Overview

We have combined 8 CSV datasets into 3 focused datasets:

| **Original Dataset** | **New Dataset** |
| --- | --- |
| olist_customers_dataset.csv | business_side.csv |
| olist_geolocation_dataset.csv | buyer_side.csv |
| olist_order_items_dataset.csv | seller_side.csv |
| olist_order_payments_dataset.csv |  |
| olist_order_reviews_dataset.csv |  |
| olist_orders_dataset.csv |  |
| olist_products_dataset.csv |  |
| olist_sellers_dataset.csv |  |
| product_category_name_translation |  |

### **3.1. Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| customer_id | Object | Each order has a unique customer_id. (NOTE: Hash) |
| customer_unique_id | Object | Unique identifier of a customer. (NOTE: Hash) |
| customer_zip_code_prefix | Object | First five digits of customer ZIP code |
| customer_state | Object | Customer state |
| geolocation_zip_code_prefix | Object | First five digits of ZIP code |
| geolocation_lat | float64 | Latitude of ZIP area |
| geolocation_lng | float64 | Longitude of ZIP area |
| geolocation_city | Object | City of ZIP area |
| geolocation_state | Object | Province of ZIP area |
| product_id | Object | Represents a unique product |
| product_category_name_english | Object | Category of Product |
| price | float64 | Item price |
| order_id | Object | Represents a unique order, each order_id contains multiple product_id |
| order_item_id | int64 | The quantity of items and their order sequence in a single order |
| order_purchase_timestamp | datetime64[ns] | Purchase timestamp by buyer |
| avg_items_per_order | int64 | Number of products per transaction |
| net_profit | int64 | Net Profit (Price * 18%) |
| payment_type | Object | Customer’s chosen payment method |
| order_status | Object | Order status (delivered, shipped, etc.) |
| review_score | int64 | Customer satisfaction rating (1 to 5) |
| seller_id | Object | Represents a unique seller |
| seller_zip_code_prefix | Object | ZIP code of Seller |
| seller_city | Object | City of Seller |
| seller_state | Object | State of Seller |
| order_approved_at | datetime64[ns] | Payment approval timestamp |
| shipping_limit_date | datetime64[ns] | Deadline for seller to ship the item |
| order_delivered_carrier_date | datetime64[ns] | Timestamp when the order was handed to the logistics partner |
| order_delivered_customer_date | datetime64[ns] | Actual order delivery date |
| order_estimated_delivery_date | datetime64[ns] | Estimated delivery date provided at the time of purchase |
| time_deliver_to_carrier | int64 | Time taken for the seller to deliver the package to the logistics partner |

## 4. Data Cleaning Process

| **Column** | **Cleaning Method** |
| --- | --- |
| Product Category | Fill missing values as "Unknown" |
| Review | Set missing values to 0 (indicating no reviews or not delivered yet) |
| Payment | Fill missing values with the most common method (Credit Card) |
| Order Approved At | Fill missing values using the median approval time per seller |
| Order Delivered Carrier Date | Fill missing values using the median delivery time per seller |
| Order Delivered Customer Date | Align missing values with the estimated delivery date |

## 5. Analysis

### **5.1. Business Performance Analysis**
- Total Profit & Revenue Trends
- Seasonal Trends (Year-on-Year Analysis)
- Seller & Buyer Growth Trends
- Correlation Between Product Variety and Profit
- Pareto Analysis
- Black Friday Anticipation
- Delivery Status

### **5.2. Buyer Analysis**
- Best Selling Products & High-Profit Items
- Customer Loyalty & Spending Analysis
- Geographic Trends & Buyer Behavior
- Payment Type Preferences
- Customer Feedback & Sentiment Analysis

### **5.3. Seller Analysis**
- Geographic Analysis & Best-Selling Products by Region
- Service Quality & Delivery Performance
- Seller Issues & Risk Analysis
- Financial & Profitability Analysis
- Identifying Top Sellers to Retain

## 6. Feature Engineering (TBD)

## 7. Modeling (TBD)

## 8. Deployment (TBD)
- **Planned Tool:** Streamlit (for model prediction)

---
