# Customer-Segmentation-RFM-Analysis

## Project Overview

Customer retention and customer value are critical factors for the success of any retail business. Understanding purchasing behavior helps organizations identify their most valuable customers, improve marketing strategies, and increase customer lifetime value.

In this project, I performed an end-to-end customer analytics workflow using the Online Retail Dataset. The data was cleaned and transformed using Python, followed by Exploratory Data Analysis (EDA), RFM (Recency, Frequency, Monetary) Analysis, and Cohort Retention Analysis to uncover meaningful customer insights.

Based on the RFM scores, customers were segmented into groups such as Champions, Loyal Customers, Potential Loyalists, At Risk, and Hibernating, enabling a deeper understanding of customer behavior and engagement. Cohort analysis was then used to evaluate customer retention patterns over time and identify opportunities to improve long-term customer relationships.

To communicate the findings effectively, an interactive three-page Power BI dashboard was developed. The dashboard provides an executive overview of customer segments, customer purchasing behavior, sales performance, and retention trends, enabling stakeholders to make informed, data-driven business decisions.

This project demonstrates the complete data analytics lifecycle—from data cleaning and transformation to business analysis, visualization, and actionable recommendations—using industry-standard tools and techniques.

## Business Problem

Retail businesses often struggle to answer questions such as:

- Who are the most valuable customers?
- Which customers are likely to stop purchasing?
- How frequently do customers return?
- Which products and countries generate the highest revenue?
- What strategies can improve customer retention?

This project answers these questions using data-driven analysis.

## Project Objectives

The primary objectives of this project are to:

- Clean and preprocess raw retail transaction data to ensure data quality and consistency.
- Perform Exploratory Data Analysis (EDA) to identify sales patterns, customer behavior, and business trends.
- Calculate **Recency, Frequency, and Monetary (RFM)** metrics to evaluate customer purchasing behavior.
- Segment customers into meaningful groups based on their RFM scores to identify high-value, loyal, and at-risk customers.
- Conduct **Cohort Retention Analysis** to measure customer retention and understand repeat purchasing patterns over time.
- Develop an interactive **Power BI dashboard** that enables stakeholders to monitor customer segments, sales performance, and retention metrics.
- Generate actionable business insights and recommendations to support customer retention, targeted marketing campaigns, and data-driven decision-making.
- Demonstrate an end-to-end data analytics workflow using Python and Power BI, from data preparation to visualization and business reporting.

## Dataset Description

This project uses the **Online Retail Dataset** available on Kaggle (https://www.kaggle.com/datasets/vijayuv/onlineretail), which contains transactional records from a UK-based online retail company specializing in unique all-occasion gifts. The dataset includes customer purchases made between **December 2010 and December 2011** and is commonly used for customer segmentation, sales analytics, and retention analysis.

Each record represents an individual product purchased within a transaction and contains information about the customer, product, quantity, price, purchase date, and country.

### Dataset Features

| Feature | Description |
|---------|-------------|
| InvoiceNo | Unique invoice number for each transaction. Cancelled transactions begin with the letter **'C'**. |
| StockCode | Unique identifier assigned to each product. |
| Description | Name or description of the purchased product. |
| Quantity | Number of units purchased in a transaction. |
| InvoiceDate | Date and time when the transaction occurred. |
| UnitPrice | Price per unit of the product (GBP). |
| CustomerID | Unique identifier assigned to each customer. |
| Country | Country where the customer is located. |

## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Power BI
- Jupyter Notebook
## Project Workflow

```
Raw Data
      │
      ▼
Data Cleaning
      │
      ▼
Feature Engineering
      │
      ▼
Exploratory Data Analysis
      │
      ▼
RFM Analysis
      │
      ▼
Customer Segmentation
      │
      ▼
Cohort Retention Analysis
      │
      ▼
Power BI Dashboard
```

---

## Data Cleaning

To ensure accurate and reliable analysis, several data preprocessing steps were performed to improve data quality and remove inconsistencies.

- **Removed Duplicate Transactions:** Eliminated duplicate records to prevent double-counting of sales and customer purchases.
- **Handled Missing Customer IDs:** Removed transactions with missing `CustomerID` values, as customer identification is essential for RFM and cohort analysis.
- **Excluded Cancelled Orders:** Filtered out cancelled transactions (identified by invoice numbers beginning with **'C'**) to analyze only completed purchases.
- **Removed Invalid Values:** Excluded records with non-positive quantities and unit prices to eliminate returns, data entry errors, and invalid transactions.
- **Converted Date Format:** Converted the `InvoiceDate` column to a datetime format, enabling time-based analyses such as monthly sales trends, recency calculations, and cohort analysis.
- **Created Total Revenue Feature:** Calculated the `Total Price` for each transaction by multiplying **Quantity × Unit Price**, providing the basis for revenue and monetary value analysis.

---

## Feature Engineering

Additional features were created to extract meaningful business insights and support customer segmentation.

- **Total Price:** Calculated the total value of each transaction using **Quantity × Unit Price**, representing the revenue generated per purchase.
- **Recency:** Measured the number of days since a customer's most recent purchase relative to the analysis date. Lower recency values indicate more recently active customers.
- **Frequency:** Counted the total number of unique purchases made by each customer, helping identify repeat buyers and customer engagement levels.
- **Monetary:** Calculated the total amount spent by each customer across all transactions, representing their overall contribution to revenue.
- **RFM Score:** Assigned scores to Recency, Frequency, and Monetary metrics using quintiles and combined them into a single RFM score for customer evaluation.
- **Customer Segment:** Categorized customers into business-oriented segments such as **Champions**, **Loyal Customers**, **Potential Loyalists**, **At Risk**, and **Hibernating** based on their RFM scores, enabling targeted marketing and retention strategies.
- **Cohort Month:** Identified the month of each customer's first purchase, allowing customers to be grouped into acquisition cohorts for retention analysis.
- **Cohort Index:** Calculated the number of months since a customer's first purchase, making it possible to measure customer retention and repeat purchasing behavior over time.

## RFM Analysis

RFM (Recency, Frequency, Monetary) Analysis is a customer segmentation technique used to evaluate customer purchasing behavior based on three key metrics. It helps businesses identify their most valuable customers, understand customer engagement, and develop targeted marketing and retention strategies.

The RFM metrics were calculated for each customer as follows:

- **Recency (R):** Measures the number of days since a customer's most recent purchase. Customers with lower recency values have purchased more recently and are generally more engaged with the business.

- **Frequency (F):** Represents the total number of unique purchases made by a customer. Customers with higher purchase frequency are typically more loyal and actively engaged.

- **Monetary (M):** Calculates the total amount spent by each customer across all transactions. Customers with higher monetary values contribute more significantly to overall business revenue.

Each customer was assigned R, F, and M scores based on quintile rankings, and these scores were combined to classify customers into meaningful business segments.

### Customer Segments

The following customer segments were identified:

- **Champions:** Recently active customers with high purchase frequency and high spending. These are the business's most valuable customers and should be rewarded to maintain loyalty.

- **Loyal Customers:** Customers who purchase frequently and contribute consistently to revenue. They are ideal candidates for loyalty programs and personalized offers.

- **Potential Loyalists:** Customers showing promising purchasing behavior who have the potential to become long-term loyal customers with appropriate engagement.

- **New Customers:** Recently acquired customers with limited purchase history. Providing a positive initial experience can encourage repeat purchases.

- **Promising:** Customers who have recently made purchases but have not yet developed consistent buying patterns. Targeted promotions can help increase engagement.

- **Need Attention:** Customers whose purchasing activity has started to decline. Timely marketing campaigns can help prevent customer churn.

- **About to Sleep:** Customers who have not purchased recently and show decreasing engagement. Re-engagement efforts may encourage them to return.

- **At Risk:** Previously valuable customers who have become inactive. Personalized retention campaigns and special offers can help recover these customers.

- **Can't Lose Them:** Historically high-value customers who have significantly reduced their purchasing activity. Retaining these customers is critical due to their past contribution to revenue.

- **Hibernating:** Customers with low recency, low frequency, and low monetary value who have been inactive for an extended period. Businesses may choose to re-engage them through targeted campaigns or focus marketing efforts on more active segments.

By segmenting customers using RFM Analysis, businesses can better understand customer value, improve marketing effectiveness, increase customer retention, and optimize resource allocation for long-term growth.

# Power BI Dashboard

An interactive **three-page Power BI dashboard** was developed to transform the analytical findings into an intuitive and business-friendly reporting solution. The dashboard enables users to explore customer segments, purchasing behavior, sales performance, and customer retention through interactive visualizations and KPIs.

---

# Dashboard 1 – Executive Customer Segmentation

The first dashboard provides a high-level overview of customer segments and their contribution to the business. It enables stakeholders to quickly identify the most valuable customer groups and understand how revenue is distributed across different customer segments.

### Dashboard Highlights

- KPI Cards displaying key business metrics
- Customer Segment Distribution
- Revenue by Customer Segment
- Revenue Contribution Treemap
- Customer Segment Performance Matrix

### Business Insights

- Identify the largest customer segments within the business.
- Compare revenue contribution across different customer segments.
- Recognize high-value customers such as **Champions** and **Loyal Customers**.
- Detect customer groups requiring retention strategies, including **At Risk** and **Hibernating** customers.
- Support data-driven marketing and customer engagement decisions.

### Dashboard Preview
<img width="1312" height="732" alt="Screenshot 2026-07-20 010053" src="https://github.com/user-attachments/assets/e34cbea8-5e2f-4407-879b-1efd8eff578f" />



---

# Dashboard 2 – Customer Behavior Analysis

The second dashboard focuses on customer purchasing behavior by analyzing spending patterns, purchase frequency, and customer value. It helps identify high-value customers and provides deeper insights into customer engagement across different RFM segments.

### Dashboard Highlights

- Spending vs Purchase Frequency Scatter Plot
- Top 15 Customers by Revenue
- Average Recency by Segment
- Average Frequency by Segment
- Average Monetary Value by Segment
- Customer Segment Summary Matrix

### Business Insights

- Identify customers contributing the highest revenue.
- Analyze the relationship between purchase frequency and customer spending.
- Compare purchasing behavior across customer segments.
- Understand which segments generate the greatest business value.
- Recognize opportunities for personalized marketing and customer retention.

### Dashboard Preview
<img width="1320" height="738" alt="Screenshot 2026-07-20 010232" src="https://github.com/user-attachments/assets/25b361d2-fd5c-42ba-8882-5b44c12d3aad" />


---

# Dashboard 3 – Sales & Customer Retention Analysis

The third dashboard focuses on business performance over time and customer retention. It combines sales analysis with cohort analysis to evaluate repeat purchasing behavior and long-term customer engagement.

### Dashboard Highlights

- Monthly Revenue Trend
- Top Revenue-Generating Countries
- Top Selling Products
- Cohort Retention Heatmap
- KPI Cards

### Business Insights

- Monitor monthly sales performance and identify seasonal trends.
- Identify countries contributing the highest revenue.
- Discover the best-performing products based on sales.
- Analyze customer retention using cohort analysis.
- Understand customer drop-off patterns and repeat purchasing behavior.
- Support strategies to improve customer retention and long-term customer value.

### Dashboard Preview
<img width="1305" height="736" alt="Screenshot 2026-07-20 010327" src="https://github.com/user-attachments/assets/269d83be-45ce-4515-8a91-c941e770e3a7" />


---

# Dashboard Features

The Power BI dashboard includes several interactive features to enhance data exploration:

- Interactive slicers and filters for dynamic analysis
- Cross-filtering between visuals
- KPI cards for quick business summaries
- Drill-down capabilities for detailed exploration
- Conditional formatting for improved data interpretation
- Cohort heatmap for visualizing customer retention trends

The dashboard is designed to provide business users with an intuitive and interactive reporting experience, enabling them to explore customer behavior, monitor sales performance, and make informed, data-driven decisions.

# Key Insights

The analysis uncovered several valuable insights into customer purchasing behavior, sales performance, and customer retention. These findings can help businesses develop targeted marketing strategies, improve customer loyalty, and increase overall revenue.

---

## Customer Segmentation

The RFM Analysis revealed distinct customer groups with varying levels of engagement and purchasing behavior.

- **Champions** are the most valuable customers, exhibiting recent purchases, high purchase frequency, and the highest spending. They contribute a significant portion of overall revenue and represent the business's strongest customer base.

- **Loyal Customers** consistently make repeat purchases and generate stable revenue over time. Their continued engagement makes them ideal candidates for loyalty programs and personalized promotions.

- **Potential Loyalists** demonstrate promising purchasing behavior and have the potential to become long-term loyal customers if nurtured through targeted marketing efforts.

- **At Risk** customers were previously active but have reduced their purchasing activity. Without timely intervention, these customers are likely to churn.

- **Hibernating** customers have remained inactive for an extended period and contribute very little to revenue, indicating low customer engagement.

---

## Customer Behavior

Customer purchasing patterns provide valuable insights into overall business performance.

- Customers with higher purchase frequency generally spend more, indicating a positive relationship between customer engagement and revenue generation.

- A relatively small percentage of customers contributes a significant share of total revenue, highlighting the importance of identifying and retaining high-value customers.

- Customer segments display distinct purchasing behaviors, allowing businesses to implement personalized marketing strategies rather than adopting a one-size-fits-all approach.

---

## Sales Performance

Sales analysis identified important business trends and revenue drivers.

- Revenue is concentrated among a limited number of countries, indicating that certain geographical markets contribute disproportionately to business growth.

- A small group of products accounts for a large portion of total sales, demonstrating the importance of monitoring product performance and inventory planning.

- Monthly sales trends reveal fluctuations in customer demand, helping businesses identify seasonal patterns and plan promotional activities more effectively.

---

## Customer Retention

Cohort Analysis provided valuable insights into customer retention and repeat purchasing behavior.

- Customer retention gradually declines after the first purchase month, suggesting that many customers do not continue purchasing over the long term.

- The highest customer drop-off occurs during the initial months following acquisition, emphasizing the importance of engaging customers early in their lifecycle.

- Improving post-purchase communication, personalized recommendations, and loyalty initiatives can significantly enhance customer retention and long-term customer value.

---

# Business Recommendations

Based on the analytical findings, the following recommendations can help improve customer engagement, increase revenue, and strengthen long-term customer relationships.

---

## Champions

Champions are the business's most valuable customers and should be prioritized for retention.

**Recommendations:**

- Introduce exclusive loyalty rewards and premium membership programs.
- Offer early access to new products and special promotions.
- Encourage referrals through customer referral programs.
- Maintain regular engagement with personalized communication.

---

## Loyal Customers

Loyal customers consistently contribute to revenue and represent strong long-term business value.

**Recommendations:**

- Provide personalized product recommendations.
- Reward repeat purchases with loyalty points or discounts.
- Encourage cross-selling and upselling opportunities.
- Recognize customer loyalty through exclusive offers and appreciation campaigns.

---

## Potential Loyalists

These customers have demonstrated positive purchasing behavior but require additional engagement to become loyal customers.

**Recommendations:**

- Send personalized follow-up emails after purchases.
- Offer targeted discounts on products similar to previous purchases.
- Encourage repeat purchases through limited-time promotions.
- Introduce loyalty programs early in the customer journey.

---

## New Customers

The first few interactions significantly influence future purchasing behavior.

**Recommendations:**

- Deliver a positive onboarding experience.
- Send welcome emails and introductory offers.
- Provide product recommendations based on initial purchases.
- Encourage second purchases through personalized incentives.

---

## Promising Customers

These customers have recently started engaging with the business and show potential for increased purchasing activity.

**Recommendations:**

- Maintain regular communication through email campaigns.
- Recommend complementary products.
- Offer incentives to increase purchase frequency.

---

## Need Attention

These customers exhibit declining engagement and should be monitored closely.

**Recommendations:**

- Send reminder emails highlighting new arrivals or promotions.
- Offer personalized discounts to encourage another purchase.
- Monitor purchasing behavior for early signs of churn.

---

## About to Sleep

Customer activity has significantly declined, indicating a risk of losing engagement.

**Recommendations:**

- Launch re-engagement campaigns with attractive offers.
- Highlight recently added products or seasonal collections.
- Personalize communications based on previous purchase history.

---

## At Risk Customers

These customers previously generated strong revenue but have become inactive.

**Recommendations:**

- Implement win-back campaigns using targeted discounts.
- Send personalized emails reminding customers of previous purchases.
- Gather customer feedback to understand reasons for inactivity.
- Prioritize retention efforts before focusing on acquiring new customers.

---

## Can't Lose Them

Historically valuable customers require immediate attention due to declining engagement.

**Recommendations:**

- Assign high-priority retention campaigns.
- Provide exclusive offers and premium customer support.
- Re-establish engagement through personalized outreach.
- Monitor their purchasing behavior closely.

---

## Hibernating Customers

These customers have remained inactive for an extended period and contribute minimal revenue.

**Recommendations:**

- Conduct cost-effective win-back campaigns.
- Offer limited-time discounts to encourage reactivation.
- If customers remain inactive after multiple campaigns, reduce marketing expenditure and focus resources on higher-value customer segments.

---

## Overall Business Impact

The insights generated through RFM Analysis, Cohort Analysis, and interactive Power BI dashboards enable businesses to better understand customer behavior, identify revenue opportunities, and make data-driven decisions. By implementing targeted retention strategies and personalized marketing campaigns, businesses can improve customer satisfaction, increase repeat purchases, maximize customer lifetime value, and drive sustainable business growth.

# Future Improvements

- Predict customer churn using machine learning
- Customer Lifetime Value (CLV) analysis
- Market Basket Analysis
- Sales forecasting
- Interactive forecasting dashboard

---

# Author

**Geetika R**

Aspiring Data Analyst | Python | SQL | Power BI | Excel | Data Visualization
LinkedIn: *www.linkedin.com/in/geetika-ramesh-1b2448225*

GitHub: *https://github.com/GEETIKA-R*

## Contact

If you have any suggestions or feedback, feel free to connect with me through LinkedIn or GitHub.
