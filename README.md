# Customer-Retention-and-Churn-Analysis
## Project Background
In today’s competitive business environment, understanding customer retention and churn is critical for sustaining growth, optimizing marketing strategies, and maximizing customer lifetime value. With increasing customer acquisition costs, businesses must prioritize retaining existing customers to ensure long-term profitability. The Customer Retention and Churn Dataset provides a comprehensive view of customer purchase behavior, loyalty, and churn metrics, enabling businesses to identify at-risk customers, assess loyalty program effectiveness, and tailor strategies to improve retention.

This project was undertaken to develop a Power BI report that analyzes customer retention and churn metrics, focusing on recency, customer segmentation, loyalty program impact, and regional trends. The report leverages a dataset capturing key metrics such as Customer_ID, First_Purchase_Date, Last_Purchase_Date, Total_Purchases, Total_Spend, Churn_Flag, Loyalty_Program_Status, Satisfaction_Score, Customer_Segment, Region, and Preferred_Product_Category. The interactive Power BI dashboard empowers stakeholders to make data-driven decisions to enhance customer retention and reduce churn.

### Key Insights and Recommendations Focused On:
- **Retention and Churn Metrics**: Analysis of overall churn rate, retention rate, and satisfaction score to gauge customer loyalty and identify areas for improvement.
- **Retention Rate Trends Over Time**: Examination of monthly retention rates from 2019 to 2024 to identify patterns, seasonal effects, or critical periods of customer loss.
- **Customer Segmentation Analysis**: Comparison of churn rates and spending behavior across High-Value, Medium-Value, and Low-Value segments to prioritize retention efforts.
- **Customer Recency Distribution**: Evaluation of customers inactive for over a year versus those active within a year to quantify churn risk and target re-engagement.
- **Category Preferences**: Assessment of customer distribution across product categories to inform product-specific marketing strategies.
- **Regional Churn Analysis**: Analysis of churn rates by region to identify geographic disparities and tailor regional retention strategies.

An interactive Power BI dashboard was developed with visuals (e.g., pie charts, line charts, clustered bar charts, maps, tables) to explore retention trends, at-risk customers, and regional performance, with dynamic filters for segmentation and product categories.

## Data Structure & Initial Checks
The dataset forms the foundation of the Customer Retention and Churn Analysis Report, structured to support detailed analysis of customer behavior and loyalty.

### Table Columns:
- **Customer_ID**: Unique identifier for each customer (text).
- **Customer_Name**: Customer’s full name (text).
- **First_Purchase_Date**: Date of first purchase (date).
- **Last_Purchase_Date**: Date of most recent purchase (date).
- **Total_Purchases**: Number of transactions (numeric).
- **Total_Spend**: Lifetime spend (numeric, dollars).
- **Average_Purchase_Value**: Total spend divided by total purchases (numeric, dollars).
- **Purchase_Frequency**: Purchases per year (numeric).
- **Customer_Segment**: High-Value, Medium-Value, or Low-Value (categorical).
- **Churn_Flag**: 1 for churned, 0 for active (numeric).
- **Loyalty_Program_Status**: Enrolled or Not Enrolled (categorical).
- **Last_Interaction_Date**: Date of last contact (e.g., email, call; date).
- **Satisfaction_Score**: Survey-based score (1–100, numeric).
- **Region**: Geographic region (categorical).
- **Preferred_Product_Category**: Most frequently purchased category (categorical).

### Key Early Checks:
- **Data Type Validation**: Confirmed appropriate data types: Customer_ID and Customer_Name as text, First_Purchase_Date and Last_Purchase_Date as date, Total_Purchases, Total_Spend, Average_Purchase_Value, Purchase_Frequency, Churn_Flag, and Satisfaction_Score as numeric, and Customer_Segment, Loyalty_Program_Status, Region, and Preferred_Product_Category as categorical.
- **Missing or Null Values**: Checked for nulls in critical columns (e.g., Last_Purchase_Date, Total_Spend, Satisfaction_Score). Handled nulls by replacing with zeros for numeric fields or excluding records where necessary (e.g., null Last_Purchase_Date set to a placeholder date).
- **Duplicate Records**: Verified Customer_ID uniqueness to eliminate duplicates, removing any in Power Query to ensure accurate customer counts.
- **Categorical Consistency**: Standardized values in Customer_Segment (e.g., no variations like “High Value” vs. “High-Value”) and other categorical fields.
- **Outlier Detection**: Inspected numeric fields (e.g., Total_Spend, Satisfaction_Score) for outliers that might indicate data errors, flagging extreme values for review.
- **Date Consistency**: Ensured First_Purchase_Date and Last_Purchase_Date were uniformly formatted and covered the analysis period (2019–2024).
- **Derived Columns**: Created DaysSinceLastPurchase in Power Query (Duration.Days(Date.From(DateTime.LocalNow()) - Date.From([Last_Purchase_Date]))) to support recency analysis.

# Executive Summary

### Overview of Findings
The analysis reveals a significant churn challenge, with a 30.35% churn rate and 70.08% of customers (15,816) inactive for over a year, signaling a critical need for retention strategies. The average satisfaction score of 49.92/100 suggests poor customer experience as a potential driver of churn. Retention rates fluctuate between 62.45% and 75.28% from 2019 to 2024, with no clear long-term trend, indicating seasonal or external influences. Churn rates are nearly uniform across customer segments (High-Value: 30.55%, Medium-Value: 30.55%, Low-Value: 29.93%), suggesting retention issues are widespread. Product category preferences are evenly distributed (3,258–3,400 customers), with Sport leading slightly. Regionally, North America has the highest churn rate (32.13%), while Oceania has the lowest (29.47%).
![Image](https://github.com/user-attachments/assets/dfc5776a-3880-4ab2-8e49-786d15b42931)

## Insights Deep-Dive
**Retention Rate Trend Analysis**  
The monthly retention data from January 2019 to December 2024 exhibits pronounced volatility with recurring patterns and critical dips. Seasonality is evident, with consistent peaks in January-February (e.g., 75.28% in Jan 2024) and August-September (e.g., 74.09% in Aug 2019), likely tied to promotional cycles or contract renewals. However, severe drops punctuate this trend: April 2020 (65.78%) coincides with early COVID-19 disruptions, May 2021 (62.66%) may reflect post-pandemic economic strains, and most critically, July 2024 (62.45%) marks the lowest point in five years. This recent collapse suggests emerging threats like aggressive competitor tactics, service failures, or pricing missteps. The overall trend shows no sustainable improvement, with retention oscillating within a 62–75% band, indicating unresolved foundational issues.  
![Image](https://github.com/user-attachments/assets/e7d5fb85-4f58-4d94-8d49-7793ad172171) 

**Customer Segmentation Analysis**  
Churn rates across customer value segments reveal a critical insight: High-Value (30.55%), Medium-Value (30.55%), and Low-Value (29.93%) segments exhibit near-identical attrition. This uniformity implies that churn drivers transcend customer lifetime value (CLV) tiers, pointing to universal pain points such as product quality gaps, poor user experience, or ineffective communication strategies. The equal vulnerability of high-value customers is particularly concerning, as their departure disproportionately impacts revenue. This segmentation analysis underscores that retention strategies must address core experience flaws rather than targeting segments in isolation.  
![Image](https://github.com/user-attachments/assets/a2d9cea8-a55a-4522-9c90-6ec658886945)

**Category Preference Analysis**  
Category engagement is remarkably balanced across product lines: Sport (3,400 customers), Beauty (3,385), Electronics (3,338), Toys (3,311), Fashion (3,308), and Home and Garden (3,258). This parity suggests that churn is not driven by category-specific issues like product performance or inventory gaps. Instead, attrition likely stems from cross-category factors such as delivery experience, customer service responsiveness, or platform usability. The absence of category dominance reinforces the need for holistic experience improvements rather than category-level interventions.  
![Image](https://github.com/user-attachments/assets/f73d328d-9800-4941-9bd5-767f4d49334d) 

**Customer Recency Distribution Analysis**  
The recency analysis exposes a severe dormancy crisis: 79.08% of customers (15,816) have not made a purchase in over a year, while only 20.92% (4,184) remain active within the past year. This imbalance indicates failing retention mechanisms, where customers disengage rapidly after initial purchases. Potential causes include inadequate post-purchase engagement, weak loyalty programs, or insufficient win-back campaigns. The sheer scale of long-inactive customers represents both a risk (eroding revenue base) and opportunity (reactivation potential), demanding urgent intervention.  

