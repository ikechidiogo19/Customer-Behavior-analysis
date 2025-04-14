# 📊 Customer Behavior analysis

This analysis explores customer purchasing behavior across various demographics and behavioral segments including income level, age, marital status, social media influence, brand loyalty, and purchase preferences. The insights were derived from observed patterns in category purchases, revenue generation, engagement metrics, and device usage.

---

## 🧠 Project Overview

The objective of this project was to identify key drivers of consumer behavior and how different factors such as income, age, marital status, and digital engagement influence shopping preferences and loyalty.

---

## 📂 Dataset

- **Source:** [Link to dataset]
- **Format:** CSV
---

## ❓ Business/Research Questions
- How does income level influence purchase categories?
- What is the relationship between age and brand loyalty?
- Do married customers spend more than single customers?
- Which purchase categories generate the highest and lowest revenue?
- do customers with higher social media influence tend to spend more?
- Which purchase channel is most popular among different income levels?
- Does social media influence impact purchase intent?
- Is customer who engage more with ads more likely to be brand loyal?
- do loyalty program members have a higher purchase frequency than non-members?
- which shipping preference is most popular among high-income customers?
- Are customers who use mobile devices for shopping more likely to make impulse purchases?
   

---

## 🛠 Methodology

- **Data Cleaning**
- Handled missing values, checked for incorrect spelling in the purchase_category column
- standardized the datatypes
- **Exploratory Data Analysis (EDA)**
- Added a new column Age_category
- categorized the age column into 'Young adult','Adults', 'Middle-aged adults' and 'Older adults'


---

## 📈 Analysis and Visualizations
``` sql
-- How does income level influence purchase categories?
SELECT income_level, purchase_category, COUNT(purchase_category) as Purchase_count
FROM Ecommerce
GROUP BY income_level, purchase_category
ORDER BY purchase_count desc;
```
``` sql
-- What is the relationship between age and brand loyality
SELECT COUNT(brand_loyalty) AS countt, age_category
FROM Ecommerce
WHERE brand_loyalty >= 3
GROUP BY  age_category
Order BY countt desc;
```
``` sql
-- do married customers spend more than single customers?
SELECT marital_status, ROUND(SUM(purchase_amount)) AS Amount
FROM Ecommerce
group by marital_status
ORDER BY Amount desc;
```
``` sql
-- WHich purchase categories generate the highest and lowest revenue?
SELECT purchase_category, ROUND(SUM(purchase_amount)) AS Amount
FROM Ecommerce
group by purchase_category
ORDER BY Amount desc ;
```
``` sql
--do customers with higher social media influence tend to spend more?
SELECT social_media_influence, ROUND(SUM(purchase_amount)) AS Amount
FROM Ecommerce
GROUP BY social_media_influence
ORDER BY Amount desc;
```
``` sql
-- Which purchase channel is most popular among different income levels?
SELECT income_level, purchase_channel, COUNT(purchase_channel) AS countt
FROM Ecommerce
GROUP BY income_level, purchase_channel
ORDER BY countt desc;
```
---

## 📌 Findings

- High-income customers show strong preference for Electronics, while middle-income customers lean toward Sports & Outdoors.
- Jewelry & Accessories generate the highest revenue; Arts & Crafts the lowest.
- Married customers consistently spend more than singles.
- High-influence users spend the most and are more impulsive in their buying behavior.
- Mobile shoppers tend to make more impulse purchases, with less focus on need-based planning.
- High-income users prefer mixed channels; middle-income users opt for mixed and in-store.
- Ad engagement correlates with brand loyalty; however, loyalty program membership does not significantly impact purchase frequency.
- High-income customers show no strong shipping preference.
- Adults are the most brand-loyal age group.


---

## 🧾 Recommendation
- Target high-income users with premium electronics offers via mixed-channel strategies.
- Leverage in-store promotions for middle-income segments interested in sports and outdoor goods.
- Focus on ad-driven campaigns to nurture brand loyalty, especially among younger or undecided buyers.
- Design campaigns to tap into impulse buying behavior for users with high social media influence and mobile usage.
- Ensure a seamless mobile shopping experience, emphasizing urgency and exclusivity to stimulate impulsive purchases.



---

## ⚙️ Technologies Used

- SQL
- Excel / Power BI 

---


