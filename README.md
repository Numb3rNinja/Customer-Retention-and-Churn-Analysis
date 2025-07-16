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
