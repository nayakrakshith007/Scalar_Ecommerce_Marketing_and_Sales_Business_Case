# Scalar_Ecommerce_Marketing_and_Sales_Business_Case

# 🛍️ E-Commerce Customer & Revenue Insights

## 🧩 Overview

This project explores how an e-commerce company can use data-driven strategies to boost **customer acquisition**, **retention**, and **revenue optimization**. Using historical transaction and customer data, the analysis uncovers behavioral trends, evaluates marketing effectiveness, and suggests targeted actions for growth.

## 📁 Dataset

- **Link:** [Google Drive Folder](https://drive.google.com/drive/folders/1Qt1HfSoTyCKiyDy2frR-hYOT9UvfwGq7?usp=sharing)
- **Details:** Includes transaction history, customer demographics, coupon usage, marketing spend, and taxes.

## 🎯 Objectives

- Identify **acquisition** and **retention trends** across months and cohorts.
- Compare revenue from **new vs. existing** customers.
- Analyze **coupon usage**, **delivery charges**, and **tax impact** on order behavior.
- Evaluate **marketing spend ROI** and campaign effectiveness.
- Segment customers using **RFM analysis** and define strategies for each tier.
- Discover **top-selling products** and **seasonal sales trends** by category/location.
- Conduct statistical tests on purchase behavior by **demographics** and **tenure**.

## 📌 Key Questions Answered

- When does customer acquisition peak or dip, and why?
- Which customer segments or cohorts offer the highest lifetime value?
- How do discounts influence revenue and transaction values?
- What pricing and promotional tactics work best across regions and age groups?
- How can marketing budgets be optimized for better ROI?

## 🔍 Techniques Used

- Cohort Analysis
- RFM Segmentation
- LTV Estimation
- Correlation & Statistical Testing
- Trend & Behavioral Analysis
- Marketing ROI Evaluation

---

> 🚀 This analysis helps align business strategy with customer behavior, empowering data-driven decisions that improve profitability and customer loyalty.



## 🗃️ Dataset Description

The dataset includes transactional and customer-level information from an e-commerce company, covering the period from **January 1, 2019 to December 31, 2019**. It is sourced from internal business records and consists of five CSV files. These datasets form the basis for customer, product, and marketing analytics.

### 📦 1. `Online_Sales.csv`  
Transaction-level data representing point-of-sale orders.  
**Key variables:**
- `CustomerID`: Unique identifier for customers  
- `Transaction_ID`: Unique transaction identifier  
- `Transaction_Date`: Date of the transaction  
- `Product_SKU`: Unique product SKU  
- `Product_Description`: Description of the product  
- `Product_Category`: Product category  
- `Quantity`: Number of items purchased  
- `Avg_Price`: Unit price of the product  
- `Delivery_Charges`: Charges applied for delivery  
- `Coupon_Status`: Whether a discount coupon was applied  

---

### 👤 2. `Customers_Data.csv`  
Customer demographic and tenure information.  
**Key variables:**
- `CustomerID`: Unique identifier for customers  
- `Gender`: Gender of the customer  
- `Location`: Customer's location  
- `Tenure_Months`: Customer tenure in months  

---

### 🎟️ 3. `Discount_Coupon.csv`  
Coupon data applied on products across different months.  
**Key variables:**
- `Month`: Month when coupon was valid  
- `Product_Category`: Category of the product  
- `Coupon_Code`: Code applied  
- `Discount_pct`: Discount percentage  

---

### 💰 4. `Marketing_Spend.csv`  
Daily marketing expenditure across online and offline channels.  
**Key variables:**
- `Date`: Calendar date  
- `Offline_Spend`: Spend on TV, radio, print, etc.  
- `Online_Spend`: Spend on digital ads like Google & Facebook  

---

### 🧾 5. `Tax_Amount.csv`  
GST tax details for each product category.  
**Key variables:**
- `Product_Category`: Category of the product  
- `GST`: Applicable GST percentage  

---

> This structured dataset enables deep insights into customer behavior, pricing strategies, marketing efficiency, and product performance.

# Business Questions:
## 1. Identify the months with the highest and lowest acquisition rates. What strategies could be implemented to address the fluctuations and ensure consistent growth throughout the year?
![image](https://github.com/user-attachments/assets/29e052e9-5086-4636-bcac-9049362b608d)

## Key Observations

### January Spike
- Possibly due to **New Year promotions** or **post-holiday shopping momentum**
- Check January's marketing spend and discounts to confirm

### Drop in November
- Likely due to seasonality or reduced campaigns
- Investigate whether marketing spend or coupon activity dropped here

## 2. Do certain months consistently show higher or lower acquisition rates? How can the company capitalize on high-performing months and improve performance during slower periods?
- September to November has low acquisition rates
- January, March and April has high acquisition rates
- ![image](https://github.com/user-attachments/assets/9c3498f6-09d5-4575-9cb7-aafd1d7fa122)

![image](https://github.com/user-attachments/assets/2a026654-64cd-4fa7-8c3d-980481a01f37)
- Looks like the marketing spends has increased during Oct Nov and December
- From the graph, I dont see a high correlation between marketing spends vs new customers acquisition
  
- Checking if the marketing has any correlation or any lagged correlation (this months marketing spend affecting next months customer acquisition)
- ![image](https://github.com/user-attachments/assets/bdf0c539-49b8-4136-b945-ab538630e834)
  
- ![image](https://github.com/user-attachments/assets/55438f5c-a1f8-4b56-b196-6414c1ba9f78)
- There seems to be no corrlation 

- Checking the discounts at a monthly level:
![image](https://github.com/user-attachments/assets/631e75a1-3e9c-48ff-b18e-5848abbae69b)
- The discounts seems to be randomly given like (10,20,30 percent repeated for each product for all months)
- We can have targeted discounts at during the peak months. Higher discounts during slow months might help with the new customer acquisition.

- Gender wise analysis:
- ![image](https://github.com/user-attachments/assets/70816d75-b2c2-4337-b909-f742ca981ac9)
- The campaigns seems to be attracting more women than men.
- We can target the current online marketing more towards Females and maybe change the marketing strategy for men

- Location wise analysis:
- ![image](https://github.com/user-attachments/assets/4981e0ad-dfd8-407f-8b69-4797df8d467d)
- Since we dont know the marketing spends by location, its hard to conclude. But if it is equally distributed across all locations:
- The marketing spends and discounts can be more concentrated on the California, chicago and New York.
- The Chicago customer acquisition seems to be consitant compared to other Locations. We can deep dive into the marketing and discounts in that location and try to extrapolate to other locations

- Product Category analysis:
- ![image](https://github.com/user-attachments/assets/ab196a99-11c0-4477-8189-b1b34b429ae7)
- Most important categories are Appralel and Bags (May be we can create marketing on Winter apparels and bags)
- Nest and Nest-USA has more customer acquistion during low acquisition months (Sept, Oct, Nov). We can try more marketing and discounts on these product categories

- ## Observations:
- 1. Jan Mar and Apr have high retemtion rates
  2. September to November has low acquisition rates
  3. There is very little correlation or a lagged correlation between Marketing spends and New customer acquisitions
  4. Based on Gender analysis, We can say that the marketing and discounts seems to be attracting new female cusomers than males. Atleast in online marketing, we can use the current campaign for females and cut the same marketing for men, We can create new customer acquisition strategies/marketing for men. (Charts attached above)
  5. It looks like no strategies has been added to discounts (It's random). We can create new discount strategies based on gender, location and product categories and do AB testing. (charts attached above)
 
 ## Q3. Identify periods with the strongest and weakest retention rates. What strategies could be implemented to improve retention during weaker months?
 - Created cohorts based on the months of purchase and cohort index based on the number of months after the first transaction and created the below retention matrix
 - ![image](https://github.com/user-attachments/assets/4fe392c9-e08e-41a3-863d-60cc77e73e44)
 - Since we have just one year of data, it's hard to conclude any insights from the above matrix

 - Tried using Dense rank by considering cust id and Transaction date as index and tried to get the repeat transaction by months.
 - ![image](https://github.com/user-attachments/assets/8da0ca68-0908-426e-8108-47fe5e7b8d77)
 - One interesting observation is that the We expect the repeat transactions to increase with the increase in the months. But we do observe a sharp decline from August to September.

 - Checking if the marketing spends or Discount % has anything to do with repeat customers:
 - ![image](https://github.com/user-attachments/assets/5843552f-3596-4dce-976f-b163344472e8)
 - It looks like the marketing spends doesnt have any correlation with the repeat customers
   
 - ![image](https://github.com/user-attachments/assets/109434d9-0c05-411a-aba8-d1657232b373)
 - It looks like the discounts spends doesnt have any correlation with the repeat customers

 - ![image](https://github.com/user-attachments/assets/fb59a971-21a1-4506-bbfd-c8f1d37991a8)
   -  California seems to have a dip in repeat customers after June 2019 and it did not improve over the subsequent months. We should concentrate on what caused the dip in California
   - Other locations had a dip in september but it improved or stayed same in the upcoming months
   -Washington's repeat customer count seems to be increasing over the same period. We can check what worked for Washington in terms of marketing or any other strategies

- Looking at the repeat customers product wise:
- ![Accessories](https://github.com/user-attachments/assets/a2fe81ad-ce87-4850-b3b3-c0605ea8d9a6)
- 



 - ## Insights: 
 - 1. Even with the increase in marketing spends during Sept to Nov, The number of repeat customers dropped.
   2. Even with the increase in discount % during Sept, The number of repeat customers dropped.
   3. California seems to have a dip in repeat customers after June 2019 and it did not improve over the subsequent months. We should concentrate on what caused the dip in California
   4. Other locations had a dip in september but it improved or stayed same in the upcoming months
   5. Washington's repeat customer count seems to be increasing over the same period. We can check what worked for Washington in terms of marketing or any other strategies
   6. 


     




