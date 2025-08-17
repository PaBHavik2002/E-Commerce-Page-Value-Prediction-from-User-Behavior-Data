# Customer Sentiment Analysis

This document provides an overview of the data analysis and visualizations performed on the customer sentiment dataset. The goal of this analysis is to understand user behavior and its impact on revenue generation.

## Key Visualizations and Findings

### 1. Product Page Visits Per Month

This analysis explores the distribution of product page visits across different months.

- **Observation**: The number of product page visits varies significantly by month. Certain months show a higher engagement with product pages, which could be attributed to seasonal trends or marketing campaigns.
- **Highlight**: The months with the highest number of product page visits are highlighted in the plot to identify peak periods of user activity.

### 2. Revenue Generated Counts Per Month

This visualization focuses on the number of revenue-generating visits for each month.

- **Observation**: The plot reveals which months are most profitable. There is a clear correlation between the months with high product page visits and the months with high revenue generation.
- **Insight**: This helps in understanding the seasonality of sales and the effectiveness of monthly marketing strategies.

### 3. Bounce Rate vs. Informational Page Visits

This scatter plot examines the relationship between the bounce rate and the number of informational pages a user visits, segmented by whether the session generated revenue.

- **Observation**:
  - Visitors who generate revenue tend to have a lower bounce rate, even when they visit multiple informational pages.
  - A high bounce rate is often associated with sessions that do not generate revenue, especially when few informational pages are visited.
- **Threshold**: A bounce rate threshold is included in the plot to distinguish between high and low bounce rates, providing a clearer picture of user engagement.

### 4. Visitor Type (New vs. Existing) and Revenue

This analysis compares the purchasing behavior of new visitors versus returning visitors.

- **Observation**:
  - A significant portion of **new visitors** do not make a purchase on their first visit.
  - Similarly, a large percentage of **existing visitors** also do not generate revenue in their sessions.
- **Insight**: While new visitors are less likely to buy, the retention of existing customers and their conversion to buyers is a critical area for improvement. The analysis indicates that only about 13% of the existing customer base makes a purchase.

### 5. Behavior of Buyers vs. Non-Buyers

This scatter plot compares the behavior of visitors who generated revenue (buyers) against those who did not (non-buyers), focusing on the `ProductRelated` pages viewed and the `ProductRelated_Duration`.

- **Observation**:
  - **Buyers** tend to spend more time on product-related pages and view a higher number of these pages compared to non-buyers.
  - **Non-buyers** often have shorter session durations and interact with fewer product pages.
- **Conclusion**: Higher engagement with product-related content is a strong indicator of a user's intent to purchase.

This analysis provides valuable insights into user behavior, highlighting the factors that influence revenue generation. By understanding these patterns, we can better tailor marketing efforts and website design to improve customer retention and conversion rates.
