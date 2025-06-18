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

### 1. Identify the months with the highest and lowest acquisition rates. What strategies could be implemented to address the fluctuations and ensure consistent growth throughout the year?
![image](https://github.com/user-attachments/assets/3689d35e-2e2c-4686-a7d0-a1f2c6e0a3cd)

#### Key Observations
- The new customer acquisition month on month is decreasing over time.
  
- **January Spike**  
  A significant increase in new customer acquisitions occurred in January. This may be attributed to:
  - New Year promotions
  - Post-holiday shopping momentum  

- **November Drop**  
  A noticeable decline in new customer acquisition was observed in November. Potential reasons could include:
  - Seasonality effects
  - Reduced marketing efforts or fewer discounts  

---

### 2. Do certain months consistently show higher or lower acquisition rates? How can the company capitalize on high-performing months and improve performance during slower periods?

1. **Monthly Trend of New Customer Acquisition:**
   - Extracted the first transaction date for each customer to determine their acquisition month.
   - Aggregated unique new customers per month and plotted the trend.
     ![image](https://github.com/user-attachments/assets/9c3498f6-09d5-4575-9cb7-aafd1d7fa122)
     
   - #### Key Observations & Insights:
     - Highest new customer acquisition occurred in **January 2019** (215 customers).
     - A general decline followed with some recovery in **March**, **June**, and **August**.
     - Lowest acquisition observed in **November 2019** (68 customers).
     - 

2. **Marketing Spend vs. Customer Acquisition:**
   - Combined online and offline marketing spend data with customer acquisition data by month.
   - Created dual-axis plots to compare trends visually.
   - Computed Pearson correlation between customer acquisition and marketing spend.
   - Also analyzed **lagged correlation** to understand delayed effects of marketing on acquisition.
     ![image](https://github.com/user-attachments/assets/2a026654-64cd-4fa7-8c3d-980481a01f37)
     
     ![image](https://github.com/user-attachments/assets/bdf0c539-49b8-4136-b945-ab538630e834)
     
     ![image](https://github.com/user-attachments/assets/55438f5c-a1f8-4b56-b196-6414c1ba9f78)

   - #### Key Observations & Insights:
     - No strong positive correlation observed:
        - **Online Spend Correlation:** -0.20 (weak negative)
        - **Offline Spend Correlation:** +0.05 (almost neutral)
    - **Lagged correlation** (next month’s acquisition) is even more negative:
        - **Offline:** -0.56
        - **Online:** -0.36
    - Indicates that **marketing spend did not significantly drive acquisition**, or there may be inefficiencies in targeting.
      

3. **Discount Impact:**
   - Calculated average discount % per month.
   - Performed correlation analysis with new customer acquisition.
     ![image](https://github.com/user-attachments/assets/631e75a1-3e9c-48ff-b18e-5848abbae69b)

   - #### Key Observations & Insights:
     - The correlation between **Discount %** and **New Customers** is **-0.15**, indicating a **very weak negative relationship**.
     - This suggests that **discounts have little to no effect** on new customer acquisition on a monthly basis.
     - Contrary to expectations, **discounting strategies may not be a significant acquisition driver**.
     - The discounts seems to be randomly given like (10,20,30 percent repeated for each product for all months)
     - We can have targeted discounts at during the peak months. Higher discounts during slow months might help with the new customer acquisition.

4. **Gender wise analysis:**
     - Identified the first purchase month for each customer to determine acquisition timing.
     - Grouped by month and gender to calculate new customer acquisition and visualized trends using a bar plot.
       ![image](https://github.com/user-attachments/assets/c4dab982-9aea-423f-b35c-b1facba1b3b1)
       
     - #### Key Observations & Insights:
        - January 2019 was the peak month for new customer acquisition, especially among females, indicating a strong start to the year possibly driven by promotions or campaigns.
        - Female customers consistently outnumber male customers in acquisition across most months, suggesting marketing efforts or product offerings may be more appealing to women.
        - There’s a noticeable decline in new acquisitions from mid-year (July) onward, with the lowest seen in October–November, highlighting a potential opportunity to boost engagement or revisit campaign effectiveness in the second half of the year.
          

5. **Location wise analysis:**
     - Grouped new customers by location and month.
     - Used a heatmap to highlight acquisition density across regions.
       ![image](https://github.com/user-attachments/assets/4981e0ad-dfd8-407f-8b69-4797df8d467d)

     - #### Key Observations & Insights:
        - Since we dont know the marketing spends by location, its hard to conclude. But if it is equally distributed across all locations:
        - **California and Chicago** consistently lead in new customer acquisition.
        - **Washington DC and New Jersey** show the lowest acquisition rates.
        - The marketing spends and discounts can be more concentrated on the California, chicago and New York.
        - The Chicago customer acquisition seems to be consitant compared to other Locations. We can deep dive into the marketing and discounts in that location and try to extrapolate to other locations
          

6. **Product Category Acquisition:**
   - Identified the first purchase product category of new customers.
   - Aggregated this by category and acquisition month and visualized using a heatmap.
     ![image](https://github.com/user-attachments/assets/93348520-b1c0-4166-8655-d8ba02a740b6)


     - #### Key Observations & Insights:
        - Top categories for customer acquisition:
          - **Apparel**, **Nest-USA**, **Office**, and **Drinkware**.
        - **Apparel** remained the most consistent driver of new customers across months.
        - Some categories (e.g., Android, Gift Cards, Waze) had very limited or no traction.
          

## Summary

    - **Discount strategy appears minimally impactful** for new customer acquisition (correlation = -0.15).
    - **Offline and online marketing show weak or negative correlation** with new customer growth.
    - Geographic and category-level trends reveal where customer interest and acquisition are strongest.
    - Businesses may benefit from **rethinking promotional strategies**, and instead focus on improving targeting and optimizing acquisition channels.
    - Based on Gender analysis, We can say that the marketing and discounts seems to be attracting new female cusomers than males. Atleast in online marketing, we can use the current campaign for females and cut the same marketing for men, We can create new customer acquisition strategies/marketing for men. (Charts attached above)
    - It looks like no strategies has been added to discounts (It's random). We can create new discount strategies based on gender, location and product categories and do AB testing. (charts attached above)

 --- 
 
 ## Q3. Identify periods with the strongest and weakest retention rates. What strategies could be implemented to improve retention during weaker months?
 - Created cohorts based on the months of purchase and cohort index based on the number of months after the first transaction and created the below retention matrix
 - ![image](https://github.com/user-attachments/assets/4fe392c9-e08e-41a3-863d-60cc77e73e44)
 - Since we have just one year of data, it's hard to conclude any insights from the above matrix

 - Tried using Dense rank by considering cust id and Transaction date as index and tried to get the repeat transaction by months.
 - ![image](https://github.com/user-attachments/assets/8da0ca68-0908-426e-8108-47fe5e7b8d77)
 - One interesting observation is that the We expect the repeat transactions to increase with the increase in the months. But we do observe a sharp decline from August to September.

 - Checking if the marketing spends or Discount % has anything to do with repeat customers:
 
1️⃣ Monthly Repeat Customers vs Marketing Spend
- ![image](https://github.com/user-attachments/assets/5843552f-3596-4dce-976f-b163344472e8)

July and August witnessed peak repeat customer activity (222 and 232 customers respectively).
These peaks coincide with low offline spend in July, suggesting repeat behavior is not purely spend-driven.
Online spend gradually increases toward December, aligning with the rise in repeat customers, possibly due to festive shopping behavior.
Offline spend spikes in April and December, but does not consistently correlate with repeat purchases.

## Insight: While both marketing channels influence behavior, repeat customers seem more responsive to timing and potentially promotional triggers, not just spend levels.
   
2️⃣ Monthly Repeat Customers vs Discount %
- ![image](https://github.com/user-attachments/assets/109434d9-0c05-411a-aba8-d1657232b373)
  Discount percentages peak in March, June, September, and December (at 30%), aligning partially with customer repeat spikes.
  Highest repeat customers (July & August) do not correlate with discount peaks, suggesting that discounts alone do not drive retention.
  Moderate discounts in high-repeat months hint at a potential sweet spot rather than aggressive discounting.

## Insight: Discounts might contribute to initial acquisition but have diminishing impact on long-term repeat behavior.

 
3️⃣ Monthly Repeat Customers by Location:
![image](https://github.com/user-attachments/assets/90856a7a-48ed-4d34-af7d-a6becee4b05f)
Chicago and California consistently lead in repeat customers throughout the year.
New York shows a steep increase until August but declines sharply afterward.
New Jersey and Washington DC have lower but relatively stable repeat counts.

## Insight: 
   - Location-based marketing should focus on sustaining growth in high-performance areas like Chicago and California, while re-engaging customers in New York post-August.
   -  California seems to have a dip in repeat customers after June 2019 and it did not improve over the subsequent months. We should concentrate on what caused the dip in California
   - Other locations had a dip in september but it improved or stayed same in the upcoming months
   - New Jersey's repeat customer count seems to be increasing over the same period. We can check what worked for New Jersey in terms of marketing or any other strategies

- Looking at the repeat customers product wise:


4️⃣ Heatmap: Repeat Customers by Product Category and Month:
- ![image](https://github.com/user-attachments/assets/654c3682-94b1-4a14-a841-10961810ab93)

Top Repeat Categories: Apparel, Nest-USA, Office, and Lifestyle lead in total repeat purchases.
Seasonal peaks: Apparel peaks in August (163).
Nest-USA and Office have consistent upward trends, peaking in Dec (125) and Jul-Aug (99-96) respectively.
Emerging categories like Drinkware and Notebooks & Journals show mid-year growth.

## 📊 Key Observations from Repeat Customer Heatmap (by Product Category & Month)

1. **Apparel** consistently leads in repeat purchases, peaking in **August** with **163** repeat customers.
2. **Nest-USA** demonstrates strong performance in the second half of the year, with peaks in **August (128)** and **December (125)**.
3. **Office** and **Lifestyle** categories show steady repeat customer engagement, especially during **mid-year months**.
4. **Drinkware** peaks in **August**, followed by a gradual decline—indicating potential **seasonal preference**.
5. **Nest (no suffix)** shows **sudden mid-year entry and rapid growth**, suggesting a **successful new product launch or promotion**.
6. **January and February** record the **lowest repeat purchases** across nearly all categories.
7. **July and August** emerge as **peak months** for repeat sales, possibly due to **seasonal campaigns or back-to-school/business needs**.
8. **Android**, **Google**, **Gift Cards**, and **More Bags** maintain **consistently low engagement**, signaling a need for **re-evaluation of marketing or product strategy**.

## Insight: Inventory planning and promotional targeting should favor Apparel, Office, and Nest-USA during mid-to-late year months.

📌 Overall Strategic Insights
- July–August are critical months for repeat sales – campaigns should capitalize on this window with targeted promotions.
- Location-specific strategies can yield higher ROI – e.g., personalized offers for New York customers post-August.
- Product categories like Apparel and Office supplies are repeat-purchase friendly, suggesting opportunity for bundling or subscription offers.
- Discounts and marketing spend should be optimized, not maximized – repeat behavior stems from value and relevance, not just pricing.

## Q4. Analyze customer behavior during high-retention months and suggest ways to replicate this success throughout the year.
✅ Key Observations (July & August)
🛍️ Product Trends:
Top Repeat Categories:
- Apparel: 139 in July, 163 in August
- Office: 99 in July, 96 in August
- Nest-USA: 114 in July, 128 in August
- Lifestyle and Drinkware also see significant repeat activity.
These are high-utility and daily-use products, indicating practical demand over luxury.

🎯 Discounts:
- Moderate average discounts (~20%) were applied.
- Unlike March or December (where 30% discounts were given), July & August did not rely on heavy discounting.
- Suggests that perceived value or relevance, not deep discounts, influenced repeat behavior.

💸 Transaction Behavior:
- Higher transaction volumes indicate bulk or bundle purchases (e.g., Office & Apparel).
- Likely back-to-school/back-to-work preparations contributed to higher demand.
- Potential presence of corporate or institutional buyers in July–August.

📈 Marketing Spend:
- Offline spend was at its lowest, especially in July (~$70,000), but repeat counts were highest.
- Online spend was stable, hinting that digital awareness and timing, rather than brute-force ad spend, led to repeat engagement.

🌍 Locations:
- California and Chicago led in repeat purchases.
- New York peaked in August and dropped sharply post-August.

#### 5. Compare the revenue generated by new and existing customers month-over-month. What does this trend suggest about the balance between acquisition and retention efforts?
#### 🛠️ Code Logic – Monthly Revenue Comparison

1. Classify each customer as "New" (first transaction) or "Repeat".
2. Group transactions by Month and Customer Type.
3. Calculate total revenue from New vs Repeat customers.
4. Create a line chart:
   - One line for New customer revenue
   - One line for Repeat customer revenue
  
#### Key Observations:
![image](https://github.com/user-attachments/assets/5d78d0bb-300f-4846-bd60-ffde09594b1c)

- Repeat customers consistently contributed higher revenue than new customers from May onwards, peaking in December.
- New customer revenue was strong in January and March, but then declined mid-year, suggesting a drop in acquisition or smaller first-time orders.
- The gap widened significantly in H2 of the year, implying successful retention strategies or higher-value purchases by returning customers.
## 🔍 Inference: Acquisition vs Retention Focus

### 💡 What the Trends Suggest:

#### 📌 Early-Year Focus on Acquisition
- In **January to March**, **new customer revenue is higher** than repeat customer revenue.
- This suggests the company **invested more in acquiring customers** early in the year—possibly through heavy marketing, discounts, or awareness campaigns.

#### 🔁 Shift Toward Retention in Mid-to-Late Year
- From **May onwards**, **repeat customer revenue surpasses** that from new customers.
- The company’s **retention strategies appear effective**, with **repeat revenue steadily growing** and eventually **dominating by Q4**.
- This indicates **better customer lifecycle management, loyalty, or satisfaction** among existing customers.

#### 💼 Revenue Dependence on Existing Customers
- In **Q3 and Q4**, the company seems to rely more heavily on **repeat buyers**.
- While this showcases **strong retention**, the **decline or stagnation in new customer revenue** may signal **slowed acquisition efforts**.

#### Q6: Analyze the relationship between coupon usage and revenue generation. How can discount strategies be optimized to maximize revenue while maintaining profitability?
🔍 Analysis: Coupon Usage vs Revenue Generation
![monthly_revenue_coupon_discount_trend](https://github.com/user-attachments/assets/d5b63026-6bfb-462f-80ea-a910bc1e6402)

📊 Graph: Monthly Revenue by Coupon Status + Average Discount %
🧠 Key Observations & Inference
- ## 1. Clicked vs Used Coupons
  - Revenue from "Clicked" coupons is consistently highest, even surpassing "Used".
  - Indicates that discount visibility/awareness (e.g., seeing or clicking a coupon) significantly impacts purchasing decisions, even if the coupon isn’t ultimately used.

- ## 2. Used Coupons
   - Revenue from "Used" coupons is stable but doesn't always spike with high discount percentages.
   - In months with 30% average discount (e.g., March, June, September, December), revenue increase is not proportional.
🔎 This implies higher discounts don’t necessarily yield higher revenue.

- ## 3. Not Used Coupons
  - Revenue from "Not Used" shows steady growth toward Q4.
  - Indicates that customers exposed to discounts may still purchase without applying them, likely due to:
  -   Product demand
  -   Urgency
  -   FOMO (fear of missing out)
  -   Pricing comfort

- 💡 Strategy Recommendations

✅ Optimize Discount Usage
- Implement targeted/personalized coupons instead of blanket high-percentage discounts.
- Cap discounts around 15–20%, as higher values may reduce profitability without added revenue gain.

✅ Leverage “Clicked” Behavior
- Customers who click but don’t redeem are high-potential targets.
- Retarget them with gentle nudges or limited-time smaller offers.
- Track and analyze drop-off after click for better funnel optimization.

✅ Avoid Over-Discounting
- No strong evidence supports that 30% discounts outperform moderate ones in revenue terms.
- Consider bundling offers, loyalty perks, or tiered discounts for better control over margins.

- ## 🧪 Hypothesis Test Results: Mann-Whitney U Test for Coupon Usage Categories

| **Comparison**           | **U-Statistic** | **p-Value** | **Interpretation**                            |
|--------------------------|----------------|-------------|-----------------------------------------------|
| Used vs Not Used         | 72,056,532     | 0.4742      | ❌ No significant difference in transaction values |
| Used vs Clicked          | 239,298,120    | 0.1939      | ❌ No significant difference in transaction values |
| Not Used vs Clicked      | 108,791,124    | 0.8230      | ❌ No significant difference in transaction values |

---

## 🔍 Summary & Interpretation

- All p-values are greater than 0.05, meaning we **fail to reject the null hypothesis** in each pairwise comparison.
- This indicates that the **value of individual transactions is statistically similar** regardless of coupon status:
  - Whether a coupon was **used**,
  - **Clicked** but not used,
  - Or **not used** at all.

---

## 💡 Key Insight

> Coupon usage does **not significantly impact** the invoice value per transaction.  
> The **effectiveness of coupons** may instead lie in **increasing order volume** or encouraging **repeat purchases**, rather than changing the amount spent per order.

## 7. Identify the top-performing products and analyze the factors driving their success. How can this insight inform inventory management and promotional strategies?
![image](https://github.com/user-attachments/assets/9eb7d119-1de7-4ed8-bc02-c2770e86e982)
![image](https://github.com/user-attachments/assets/17ec7a2b-2f8f-464a-83ec-134330a9deeb)
![image](https://github.com/user-attachments/assets/1393dc29-8a8c-4c18-bc18-4e88545462d7)

## Top-Performing Products: Key Takeaways

## Key Observations:
- "Nest" Brand Dominance: "Nest" products, especially from "Nest-USA" (e.g., thermostats, cameras), are top revenue generators due to high individual invoice values.
- High-Volume Categories: "Office," "Apparel," and "Drinkware" are high-volume sellers, indicating broad appeal and consistent demand, despite potentially lower individual prices.
- Revenue vs. Quantity Leaders: "Nest" devices drive significant revenue per unit, while "Office" products lead in total quantity sold, suggesting different market dynamics.
- Security & Convenience Appeal: Top "Nest" products are essential smart home devices, likely benefiting from strong brand trust and utility for modern homes.
- Diverse Product Success: Success is driven by both high-value specialized products ("Nest") and high-volume general consumer goods (Office, Apparel, Drinkware).

  
## Strategic Insights:
- Prioritize "Nest" for Profitability: Focus inventory and premium marketing on high-value "Nest" products to maximize revenue and profitability. Implement strict inventory control to avoid stockouts for these key items.
- Optimize Volume Categories for Market Share: For "Office," "Apparel," and "Drinkware," prioritize efficient bulk purchasing, rapid replenishment, and volume-driven promotions (e.g., bundles, BOGO) to capture market share and manage high turnover.


## 8. Analyze the relationship between monthly marketing spend and revenue. Are there any months where marketing efforts yielded disproportionately high or low returns? How can marketing strategies be adjusted to improve ROI?

📊 Analysis of Monthly Marketing Spend vs Revenue
![image](https://github.com/user-attachments/assets/cbc3bd74-7f5f-4ee4-9598-1afecac7bb01)

## ✅ Key Insights
- Strong Positive Correlation: The Pearson correlation coefficient between total marketing spend and monthly revenue is 0.83, indicating a strong positive relationship. Generally, higher marketing spend is associated with higher revenue.
- Effectiveness of Marketing: The positive trend line and tight clustering around it suggest that marketing efforts are broadly effective in driving revenue across most months.

Disproportionate Returns in Some Months
A few data points deviate noticeably from the trend:

One month with low marketing spend (~₹120,000) still achieved relatively high revenue (~₹450,000+), suggesting efficient performance or residual brand momentum.

Another month shows high marketing spend (~₹200,000) but only moderate revenue (~₹610,000), which may reflect diminishing returns or campaign inefficiency.

Consistent ROI in Mid-Spend Range
Months with marketing spend between ₹140,000–₹160,000 tend to show predictable revenue returns (~₹480,000–₹520,000), suggesting a reliable performance band.

🧠 Strategic Implications
Optimize Spend Efficiency
Investigate months where lower spend yielded higher revenue to understand what strategies or external factors drove performance.

Review High-Spend Months
Analyze campaign content, audience targeting, and external conditions in high-spend but underperforming months to reduce waste and improve ROI.

Maintain Momentum in Mid-Spend Zone
Consider doubling down on months with consistent returns in the ₹140k–₹160k marketing band, optimizing for reliable performance.

## Q8: Analyze the relationship between monthly marketing spend and revenue. Are there any months where marketing efforts yielded disproportionately high or low returns? How can marketing strategies be adjusted to improve ROI?
![image](https://github.com/user-attachments/assets/61fc2c4f-6750-4ea3-8d87-5de27443edcc)
![image](https://github.com/user-attachments/assets/a626c8b7-635c-4022-80a7-d004176a078a)

📊 Analysis: Monthly Marketing Spend vs Revenue
🔁 Overall Relationship
- Strong Positive Correlation: The heatmap reveals a high correlation (0.83) between Total Marketing Spend and Revenue, indicating that increased marketing investment generally leads to higher returns.
- Online Spend Impact: Online spend shows a higher correlation (0.85) with revenue than offline spend (0.79), suggesting digital marketing is slightly more effective in driving sales.

### 📅 Month-Wise ROI Insights:
## ✅ High ROI (High Revenue with Moderate Spend)
## Month 11 (November): Moderate spend (~161K) generated a high revenue (~586K).
- Suggests strong campaign performance or seasonal boost (pre-festive shopping).

## Month 1 (January): 
- Spend (~155K) generated over 500K in revenue.
- Efficient start to the year; campaigns likely well-targeted.

## ❌ Low ROI (Low Revenue Despite Moderate-High Spend)
- Month 2 (February) & Month 6 (June): Both months had similar or slightly lower spend than January but significantly underperformed in revenue.
- Indicates possible misalignment in campaign targeting or weak customer response.

## 💰 High Spend, High Return
- Month 12 (December): Highest spend (~199K) corresponded to highest revenue (~610K).
- Campaigns likely benefited from year-end or holiday shopping spikes.

## 💡 Strategic Recommendations to Improve ROI
- Reallocate Budget to High-Performing Months:
- Invest more in November, January, and December where returns are consistently high.

## Q9: Evaluate the effectiveness of marketing campaigns by comparing marketing spend to revenue generated. Are there opportunities to reallocate resources for better results?
### 📊 Step 1: Calculate Marketing Efficiency

We use the formula:

\[
\textbf{Marketing Efficiency Ratio (MER)} = \left( \frac{\text{Total Marketing Spend}}{\text{Revenue}} \right) \times 100
\]

This tells us how much was spent on marketing to earn ₹100 in revenue.

🔍 **Interpretation**:
- **Lower MER%** = **Better Efficiency**


![image](https://github.com/user-attachments/assets/822bf87d-0e5c-48d4-b0c8-f8c37db95081)

## ✅ High Efficiency Months (MER < 28%)
- July, August, March, November:
- Achieved high revenue with comparatively lower marketing costs.
- These campaigns should be analyzed for best practices (e.g., channel mix, timing, audience).

## ❌ Low Efficiency Months (MER > 32%)
- February, June, December:
- Marketing spend was high relative to the revenue generated.
- Indicates inefficient resource utilization — investigate campaign quality or seasonal demand mismatch.


## Q10: Segment customers into groups such as Premium, Gold, Silver, and Standard. What targeted strategies can be developed for each segment to improve retention and revenue? (Use RFM segmentation techniques)
## 📊 RFM Segmentation Overview

**RFM (Recency, Frequency, Monetary) Segmentation** is a powerful customer segmentation technique used in marketing and sales analytics to identify and prioritize high-value customers based on their purchasing behavior.

### 🔢 How RFM is Calculated:
1. **Recency (R)** – How recently a customer made a purchase.
   - Calculated as the number of days since the customer's last transaction.
2. **Frequency (F)** – How often a customer makes a purchase.
   - Count of total transactions made by the customer.
3. **Monetary (M)** – How much money a customer spends.
   - Total revenue generated by the customer.

Each metric is scored (e.g., from 1 to 4 or 5), where higher values generally indicate more desirable customer behavior.

---

### 🧠 Importance of RFM Segmentation:
- Helps identify **loyal and high-value customers** (e.g., Premium segment).
- Enables **personalized marketing strategies** for each customer segment.
- Improves **retention** by targeting at-risk or inactive customers.
- Assists in **resource allocation** by focusing efforts on high ROI segments.
- Supports **customer lifecycle analysis** and long-term growth planning.

---

### 🧩 Typical RFM Segments:
- **Premium**: High recency, high frequency, high spenders.
- **Gold**: Recent and frequent buyers with moderate spending.
- **Silver**: Occasional buyers with decent value.
- **Standard**: Low recency and frequency, low monetary contribution – may need re-engagement.

![image](https://github.com/user-attachments/assets/27addb77-d4a7-4ba6-b513-ca60cd673f3e)

### 🧮 RFM Segmentation: Thresholds Used and Rationale

RFM (Recency, Frequency, Monetary) segmentation was applied to group customers into meaningful segments based on their buying behavior. The thresholds for Recency, Frequency, and Monetary values were defined using **quartile-based scoring**, which splits the customer base into four equal parts for each metric. Here's how and why we used these specific thresholds:

---

#### 📌 **Threshold Logic**

1. **Recency (R):**
   - Measures how recently a customer made a purchase.
   - Customers with lower recency (i.e., more recent purchases) are considered more engaged.
   - We used `pd.qcut()` to divide customers into quartiles:
     - Score 4: Most recent 25% of customers
     - Score 1: Least recent 25%

2. **Frequency (F):**
   - Measures how often a customer purchased.
   - Higher frequency suggests loyalty.
   - Again, `pd.qcut()` was applied to frequency counts:
     - Score 4: Most frequent 25%
     - Score 1: Least frequent 25%

3. **Monetary (M):**
   - Captures the total spending by each customer.
   - Higher spenders are more valuable.
   - Quartiles were assigned where:
     - Score 4: Highest spending 25%
     - Score 1: Lowest 25%

---

#### 🧠 **Why These Thresholds?**

- **Standardized scoring**: Quartile-based segmentation helps create a balanced distribution and avoids bias due to outliers.
- **Simple interpretation**: A score of 4 means "top-performing" in that dimension.
- **Scalable approach**: This method works well for large datasets without requiring manual tuning.
- **Business alignment**: It ensures customers are grouped by behavior rather than arbitrary cutoffs, enabling more targeted strategies.

---

#### 🎯 **Outcome**

Customers were then classified into segments (Premium, Gold, Silver, Standard) based on combined RFM scores. For example:
- **Premium**: R ≥ 3, F ≥ 3, M ≥ 3
- **Standard**: R = 1, F = 1, M = 1

This enables precise targeting and optimized resource allocation for retention and revenue growth.

## 11. Analyze the revenue contribution of each customer segment. How can the company focus its efforts on high-value segments while nurturing lower-value segments?
![image](https://github.com/user-attachments/assets/d9d700fb-dea5-4d68-b5de-3536ae84eb0e)

## 🔍 Key Observations and Insights: Revenue by Customer Segment

### 📊 Segment-wise Average Revenue
| Segment   | Avg. Revenue (INR) |
|-----------|-------------------|
| Premium   | ₹7,254.45         |
| Gold      | ₹2,178.37         |
| Silver    | ₹961.10           |
| Standard  | ₹368.19           |

---

### 🎯 Strategic Insights

#### 🥇 Premium Segment
- **Highest average revenue** per customer.
- Represents your most valuable and engaged customers.
- ✅ *Strategy*: Focus on retention, personalized experiences, and VIP rewards to maximize lifetime value.

#### 🥈 Gold Segment
- Moderate revenue contribution with clear potential to upgrade.
- ✅ *Strategy*: Promote premium features, loyalty incentives, and targeted upselling.

#### 🥉 Silver Segment
- Contributes lower revenue, possibly due to infrequent purchases.
- ✅ *Strategy*: Improve engagement through regular communication, personalized offers, and repeat purchase nudges.

#### 🎗️ Standard Segment
- Lowest revenue per customer.
- Likely consists of new or inactive users.
- ✅ *Strategy*: Focus on onboarding, product education, and entry-level offers to convert them into repeat customers.

---

### 📌 Overall Takeaways
- **High-value segments (Premium, Gold)** should be prioritized for retention and upselling to maintain revenue momentum.
- **Low-value segments (Silver, Standard)** offer growth opportunities through nurturing and targeted marketing.
- Segmenting customers using RFM helps **optimize marketing efforts, improve ROI, and personalize customer experience** effectively.



## Q12: Group customers by their month of first purchase and analyze retention rates over time. Which cohorts exhibit the highest and lowest retention rates? What strategies can be implemented to improve retention for weaker cohorts?
![image](https://github.com/user-attachments/assets/d57f87a1-52b7-4f5a-baea-3d8c623bb125)
## 📌 Which Cohorts Exhibit the Highest and Lowest Retention Rates?

### ✅ Highest Retention Cohorts:

#### **February Cohort**:
- Shows strong retention across several months.
- Notable retention rates: **23% (month 6), 20% (month 7), 16% (month 8)**.

#### **March Cohort**:
- Solid performance early on.
- Notable retention rates: **20% (month 3), 18%, 19%, 12%**.

#### **January Cohort**:
- Decent long-term retention.
- Notable retention rates: **22% in month 8** and **16% even in month 12**.

---

### ❌ Lowest Retention Cohorts:

#### **July to October Cohorts**:
- Sharp drop-offs after month 2 or 3.
  
**Examples**:
- **July**: 14% → 4% → 6%
- **August**: 10% → 11% → 7%
- **September**: 8% → 4% → 3%

## Q13: Analyze the lifetime value of customers acquired in different months. How can this insight inform acquisition and retention strategies? 
- ![image](https://github.com/user-attachments/assets/64fccfa3-dbf7-4363-95dc-b4e1e04d3506)

## 📊 Customer Lifetime Value (LTV) Heatmap Analysis
Each cell shows the **average revenue per customer** from a particular **cohort (acquisition month)** over time (columns = months since acquisition).

---

### 📈 What This Heatmap Tells Us
- It reveals how much revenue customers bring in each month after acquisition.
- Helps identify **valuable cohorts** and **ineffective acquisition periods**.

---

### 🎯 How This Insight Can Inform Strategy

#### ✅ 1. Identify High-Value Cohorts for Acquisition Focus
- **February, October, and November** cohorts show **strong early LTV**.
  - *Feb Month 0 LTV:* ₹2988
  - *Oct Month 0 LTV:* ₹2778
- **Action**: Increase **marketing spend** and replicate the strategies used in these months.

---

#### ❗ 2. Spot Cohorts That Underperform
- **June and September** cohorts show **low and short-lived value**.
  - *June LTV drops to:* ₹95
  - *September LTV drops to:* ₹7
- **Action**:
  - Analyze campaign quality, targeting, or external factors.
  - Rethink or **pause acquisition campaigns** in these months.

---

#### 📊 3. Estimate Long-Term Customer Value
- Use monthly LTV growth to understand **how much a customer is worth over time**.
- **Action**:
  - If Jan cohort averages ₹2500–₹3000 over a year, acquisition cost (CAC) should be **less than ₹1500–₹2000**.

---

#### 💸 4. Optimize Retention Investment
- Cohorts like **Jan and Feb** maintain revenue even after several months.
- **Action**:
  - Focus **retention strategies** (emails, loyalty rewards) on these cohorts.
  - Use insights to shape future **customer engagement journeys**.

---

#### 🧠 5. Test and Improve Over Time
- Track LTV changes across cohorts to measure **impact of new strategies**.
- **Action**:
  - If LTV improves for future December cohorts after implementing changes, strategy is successful.

---

### ✅ Final Strategy Takeaways

| Focus Area            | Recommended Action                                                      |
|-----------------------|-------------------------------------------------------------------------|
| High-Value Cohorts    | Increase acquisition investment, replicate success                      |
| Low-Value Cohorts     | Investigate drop-offs, improve or pause campaigns                       |
| CAC Optimization      | Use LTV benchmarks to cap acquisition costs                             |
| Retention Planning    | Invest in cohorts with strong LTV beyond 3–6 months                     |
| Strategy Testing      | Monitor LTV trend to validate marketing and retention improvements      |

---

## Q14: 14. Do customers who use coupons have a different average transaction value compared to those who do not? Conduct a statistical test to validate this hypothesis. What implications does this have for the company's discount and coupon strategies?

### 🎯 Hypothesis Testing: Impact of Coupons on Average Transaction Value

#### 📌 Hypotheses:

- **Null Hypothesis (H₀):**  
  There is **no significant difference** in the average transaction value between customers who use coupons and those who do not.

- **Alternative Hypothesis (H₁):**  
  There **is a significant difference** in the average transaction value between customers who use coupons and those who do not.

---

#### 🔍 Which hypotest Testing method to use:

We used the **Independent Samples t-test** (also known as two-sample t-test) because:

- We are comparing the **means** of **two independent groups**:  
  1. Transactions with coupons  
  2. Transactions without coupons
- The **t-test** is suitable when:  
  - The dependent variable (Transaction Value) is **continuous**,  
  - The groups are **independent**,  
  - The sample size is reasonably large, and  
  - We want to check for a **statistical difference in means**.

---

#### 📊 Test Results:

- **T-statistic:** -1.4324  
- **P-value:** 0.1521

---

#### ✅ Conclusion:

- Since the **p-value (0.1521)** is **greater than 0.05**, we **fail to reject the null hypothesis**.
- This means there is **no statistically significant difference** in the average transaction value between **coupon users** and **non-coupon users**.

---

#### 💡 Business Implication:

- Coupon usage **does not significantly reduce or increase** transaction value.
- The company can continue using coupons as a **strategic tool** to:
  - Encourage **customer acquisition**
  - Improve **conversion rates**
  - Potentially impact **retention or lifetime value**
- Future analysis should explore whether **coupon usage affects repeat purchases or customer lifetime value (CLV)** rather than just per-order value.


## Q15: Do purchase behaviors (e.g., order frequency, order value) vary significantly across different demographic groups or pricing factors (e.g., delivery charges)? Test for differences in purchase behavior across locations, age groups, or delivery charge tiers. How can these insights inform personalized marketing and pricing strategies? 

## 🧪 Statistical Analysis: Purchase Behavior Across Groups

We conducted **One-Way ANOVA** tests to assess if average order values vary across:

1. 📍 Locations  
2. 🎂 Tenure Groups (proxy for age or customer maturity)  
3. 🚚 Delivery Charge Tiers  

---

### 📍 Location-based Avg Order Value Comparison

- **Null Hypothesis (H₀):** There is no significant difference in average order value across different locations.
- **Alternative Hypothesis (H₁):** At least one location has a significantly different average order value.

**F-statistic:** 2.9201  
**P-value:** 0.0199 ✅

> **Conclusion:** We reject the null hypothesis.  
> There is a **statistically significant difference** in average order value among different customer locations.

**🔍 Implication:**  
Location-specific pricing or promotional strategies can be effective. Consider offering tailored discounts or shipping incentives based on geographic performance.

---

### 🎂 Tenure Group-based Avg Order Value Comparison

- **Null Hypothesis (H₀):** No significant difference in average order value across tenure groups.
- **Alternative Hypothesis (H₁):** At least one tenure group has a significantly different average order value.

**F-statistic:** 0.6897  
**P-value:** 0.5582 ❌

> **Conclusion:** We fail to reject the null hypothesis.  
> There is **no statistically significant difference** in purchase behavior based on customer tenure.

**🔍 Implication:**  
New and old customers behave similarly in terms of transaction value. Marketing strategies should focus on uniform value propositions rather than tenure-based segmentation.

---

### 🚚 Delivery Tier-based Avg Order Value Comparison

- **Null Hypothesis (H₀):** Average order value does not differ across delivery charge tiers.
- **Alternative Hypothesis (H₁):** There is a significant difference in order value based on delivery charge tiers.

**F-statistic:** 249.5529  
**P-value:** 0.0000 ✅

> **Conclusion:** We reject the null hypothesis.  
> There is a **highly significant difference** in average order value across delivery charge tiers.

**🔍 Implication:**  
Customers paying higher delivery charges tend to have **significantly higher order values**.  
You can:
- Offer **free delivery thresholds** to increase cart size.
- Introduce **premium shipping options** for high-value customers.

---

### ✅ Why ANOVA?

We used **ANOVA (Analysis of Variance)** because:
- We were comparing **means across more than two independent groups**.
- ANOVA checks for **overall differences** and avoids inflating error rates compared to multiple t-tests.

---

## 📊 ANOVA Results: Order Frequency by Demographics & Pricing Tiers

### 📍 Location-based Order Frequency Comparison
- **F-statistic**: 1.1611  
- **P-value**: 0.3262  
🔍 **Interpretation**: There is **no statistically significant difference** in order frequency across different locations.

---

### 🎂 Tenure Group-based Order Frequency Comparison
- **F-statistic**: 1.1820  
- **P-value**: 0.3152  
🔍 **Interpretation**: Customers with different tenures **do not significantly differ** in how frequently they place orders.

---

### 🚚 Delivery Tier-based Order Frequency Comparison
- **F-statistic**: 0.8341  
- **P-value**: 0.4751  
🔍 **Interpretation**: Differences in delivery charges **do not significantly impact** customer order frequency.

---

### 📌 Conclusion
These results suggest that **order frequency is relatively consistent** across demographic segments and pricing tiers.  
💡 **Strategy Implication**: Efforts to boost order frequency may be better directed through personalized communication or loyalty programs rather than adjusting delivery pricing or targeting specific locations or tenure groups.


## Q16: Does customer tenure impact purchase frequency? Analyze the relationship between customer tenure and purchase frequency. How can this insight be used to improve customer engagement and retention strategies?

### 🎯 Statistical Test: ANOVA on Normalized Order Frequency by Tenure Group
![image](https://github.com/user-attachments/assets/b75b6407-3506-4671-9871-b31e4ff15927)

#### ✅ Hypotheses:
- **Null Hypothesis (H₀):** There is **no significant difference** in normalized order frequency across tenure groups.
- **Alternative Hypothesis (H₁):** There **is a significant difference** in normalized order frequency across at least one tenure group.

#### 📊 Test Used:
- **One-Way ANOVA**: Chosen because we are comparing the **means of a continuous variable** (normalized order frequency) across **more than two independent groups** (tenure bins).

#### 📈 Results:
- **F-statistic:** `197.5184`
- **P-value:** `0.0000`

#### 📌 Conclusion:
- Since the **p-value < 0.05**, we **reject the null hypothesis**.
- This suggests that **customers with different tenure lengths show significantly different purchasing frequencies**, even after adjusting for time.

#### 📉 Visual Insight:
- Customers in the **<6M (Low tenure)** group have **much higher normalized order frequency** compared to others.
- This could indicate high engagement or aggressive promotional activity shortly after acquisition.
  
#### 💡 Strategic Implications:
- **Early-tenure customers** are more active — consider targeting them with retention campaigns.
- **Longer-tenure customers** may need reactivation offers or loyalty programs.
- **Segment-specific marketing** can help maximize lifetime value across stages.

## Q17 Analyze the relationship between delivery charges and order behavior. Are there opportunities to optimize delivery pricing to increase order quantities or revenue?

## Relationship Between Delivery Charges and Order Behavior

### 🎯 Objective:
To assess whether **delivery charges influence the number of items (quantity) ordered**.

---

### 🧪 Statistical Analysis Summary

#### 🔗 **Correlation Test**
- **Correlation (r)** = `0.1914`
- ✅ Suggests a **weak positive relationship** — as delivery charges increase, quantity ordered slightly increases.

---

#### 📈 **Linear Regression Analysis**
```plaintext
Model: Quantity ~ Delivery_Charges
R-squared: 0.037 (3.7%)
P-value for Delivery_Charges: < 0.001 ✅

### 📊 Interpretation:

- The model is **statistically significant** (p < 0.001).
- However, **R-squared is low (3.7%)**, meaning delivery charges explain only a **small portion** of variation in quantity.
- The **coefficient is positive**, meaning:

  > Every 1-unit increase in delivery charge is associated with a ~0.2 unit increase in quantity ordered.

---

### 🧪 ANOVA Test by Delivery Charge Tier:

| Factor         | F-statistic | P-value     |
|----------------|-------------|-------------|
| Delivery_Tier  | 715.2999    | < 0.0001 ✅  |

✅ **Statistically significant differences** exist in **average quantity ordered** across delivery charge tiers.

---

### 🧠 Interpretation of Results:

- Although the **correlation is weak**, both the **linear regression** and **ANOVA** indicate that **delivery charges do influence order behavior**.
- Customers may **increase their order quantity** when delivery charges are higher:
  - Possibly to **feel the delivery fee is justified**.
  - Or to **reach a threshold** for **free delivery** or promotional benefits.

---

## Q18: Evaluate how taxes and delivery charges influence customer spending behavior. Are there opportunities to adjust pricing strategies to improve customer satisfaction and revenue?

## 🧪 ANOVA Test Results: Impact of Delivery Charges and Taxes on Customer Spending Behavior

### 🚚 Delivery Tier-based Spending Behavior
- **F-statistic**: 615.9777  
- **P-value**: 0.0000

✅ **Interpretation**: There is a statistically significant difference in average spending (Invoice Value) across different **Delivery Charge tiers**. This means that the amount customers spend varies meaningfully depending on the level of delivery fees they incur.

---

### 💸 Tax Tier-based Spending Behavior
- **F-statistic**: 2388.0759  
- **P-value**: 0.0000

✅ **Interpretation**: There is a statistically significant difference in customer spending across different **Tax tiers**. This suggests that the amount of tax associated with products meaningfully affects how much customers end up spending.

---

## 🔍 Strategic Insights

1. **Delivery Pricing Optimization**:
   - Since delivery charges significantly influence how much customers spend, consider testing reduced or tiered delivery fees to increase cart sizes or encourage higher frequency of orders.
   - Offering **free delivery** above a certain cart value could nudge customers to increase their purchase amount.

2. **Tax-sensitive Product Bundling**:
   - Customers appear responsive to tax differences. Lower-taxed product categories might perform better or be more price-sensitive.
   - You could **bundle high-tax items with discounts or low-tax products** to balance perceived cost and value.

3. **Personalized Offers**:
   - Use delivery and tax tier data to **segment customers** for targeted promotions. For example, high delivery tier users may respond well to **"free shipping weekend"** campaigns.

---

🧠 *These findings suggest that both delivery charges and tax rates play a significant role in shaping customer spending behavior. Fine-tuning these components can enhance both customer satisfaction and revenue potential.*

## Q19: Identify seasonal trends in sales by category and location. How can the company prepare for peak and off-peak seasons to maximize revenue?
![image](https://github.com/user-attachments/assets/2b330fe8-4e19-4b93-803d-8834018caac7)
![image](https://github.com/user-attachments/assets/7229ac63-7f70-4d13-97de-967443bf5613)

## 🔍 Seasonal Sales Analysis by Product Category and Location

### 📌 Objective:
To identify recurring seasonal patterns in sales by **product category** and **customer location** and recommend strategies to **optimize inventory**, **marketing efforts**, and **revenue generation** during peak and off-peak months.

---

### 📈 Key Observations from Product Category Heatmap:

1. **Consistent Peak Performers:**
   - **Office Supplies** dominate throughout the year, with exceptionally high sales in **Jan, Mar, Apr, Jul, and Aug**, likely due to business cycles and back-to-school trends.
   - **Drinkware** and **Apparel** also show strong sales in **spring (Mar–May)** and **late summer (Jul–Sep)**.

2. **Highly Seasonal Categories:**
   - **Notebooks & Journals** spike notably in **April, July, and August**, aligning with academic or office renewal cycles.
   - **Lifestyle** and **Headgear** peak in **Apr–Sep**, suggesting seasonal fashion preferences or climate-driven demand.
   - **Gift Cards** and **Accessories** surge in **Oct–Dec**, likely due to **holiday gifting behavior**.

3. **Low and Inconsistent Performers:**
   - Categories like **Google**, **Nest**, and **More Bags** exhibit sporadic or very limited sales, indicating either niche appeal or poor product-market fit.

---

### 🌍 Key Observations from Location-wise Trends:

1. **High-Performing Regions:**
   - **Office sales in California and Chicago** remain consistently strong, indicating high volume B2B/B2C markets.
   - **Chicago** shows significant peaks in **Mar, Apr, Jul, and Aug**, possibly aligned with fiscal calendars or seasonal campaigns.
   - **California** sales spike in **Jan, Apr, and Jul**, but decline toward the end of the year, hinting at early budget utilization.

2. **Emerging or Moderate Markets:**
   - **New York** and **New Jersey** show more volatile sales patterns but still peak during **Apr–Jul**, requiring better demand forecasting.
   - **Washington DC** exhibits minor but noticeable sales in **Feb, Jul, and Sep**, hinting at public sector or academic demand.

---

### 💡 Strategic Insights:

1. **📦 Inventory Management:**
   - Stock up on **Office, Drinkware, Apparel, and Notebooks** from **Feb to Aug** to meet expected peak demand.
   - Reduce inventory of **seasonally slow movers** like Bottles, Nest, and Google products during off-peak periods to avoid overstocking.

2. **📣 Targeted Promotions:**
   - Run **location-based campaigns** in **Chicago and California** around **fiscal peaks (Mar, Apr, Jul)**.
   - Promote **Gift Cards, Accessories, and Lifestyle** items during **Q4 holidays** to leverage gifting trends.

3. **📊 Budget Allocation:**
   - Allocate higher marketing and logistics budgets to **high-performing months** per category.
   - Use **seasonality insights** to time product launches, flash sales, and discount cycles effectively.

4. **🧠 Demand Forecasting:**
   - Leverage these patterns to develop **predictive models** for better supply chain and workforce planning in upcoming years.

---

### ✅ Conclusion:
Understanding the **seasonal behavior of customers across locations and categories** enables the business to **maximize revenue**, **minimize inventory holding costs**, and **strategically plan promotions** in alignment with actual demand cycles.

## Q20:

## 📅 Daily Sales Trend Analysis
![image](https://github.com/user-attachments/assets/40a0637f-31bb-44b9-9fb8-fb66b7fe47bc)

- **Peak Sales Days**: Friday, Thursday, and Wednesday are the top-performing days.
- **Moderate Sales Days**: Weekend days (Saturday & Sunday) see decent performance.
- **Low Sales Days**: Monday and Tuesday have the lowest revenue, indicating weak start-of-week performance.

---

### 💡 Insights & Recommendations:

#### 🔼 For High-Performing Days (Wed–Fri):
- Leverage these days for:
  - **New product launches**
  - **Email promotions or flash sales**
  - **Cross-sell and upsell campaigns**

#### 🔽 For Low-Performing Days (Mon–Tue):
- Implement strategies to boost sales:
  - **Limited-time discounts** or "Early Week Offers"
  - **Free delivery** or reduced charges on Mon–Tue
  - **Loyalty program incentives** (e.g., double points)
  - **Social media or influencer marketing** campaigns targeted on Sunday night to stimulate Monday traffic

#### 🛍️ For Weekend Shoppers (Sat–Sun):
- Consider:
  - **Bundle offers** for weekend family shopping
  - **Category-specific promotions** based on observed weekend preferences

---

### 📦 Strategic Implication:
- **Inventory Planning**: Ensure higher stock availability by midweek to support peak demand.
- **Operational Optimization**: Staff logistics and delivery operations should scale up on Thu–Fri.
- **Marketing Scheduling**: Concentrate awareness campaigns mid-week and run conversion campaigns at the start of the week.





     




