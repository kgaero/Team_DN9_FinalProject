# Final Project - DIVE Analysis as Technology & Innovation Analyst

## Option B: Retail Chain Transformation

Client: Legacy retail chain losing market share

Dataset: Store performance and customer data

Question: How should we restructure operations to compete with digital disruptors?

# D - Discover

## Perform data quality validation

### Summary:

### Data Analysis Key Findings

* The dataset contains 100,000 records.
* Only the 'Month' column has missing values (1000 entries, or 1.0%).
* There are no duplicate rows in the dataset.
* Numerical variables like 'Unit price', 'Quantity', 'Tax 5%', 'Sales', 'cogs', and 'gross income' show strong positive correlations with each other.
* 'Rating' has very weak correlations with all other numerical variables.

### Insights or Next Steps

* Address the missing values in the 'Month' column, possibly by imputation or investigation into the data collection process.
* Investigate the factors that influence 'Rating' since it does not appear to be strongly correlated with sales or price metrics.

# I - Investigate

## Predict the next 6 months of sales using linear regression

### Summary:

### Data Analysis Key Findings

* The historical monthly sales data was successfully prepared for time series analysis by converting the date column to datetime objects and setting it as the index.
* A linear regression model was trained on the historical data using the time step as the independent variable and sales as the dependent variable.
* Sales predictions for the next 6 months were generated using the trained linear regression model, starting from time step 24 up to time step 29.
* The predicted sales show a decreasing trend over the next six months.

### Insights or Next Steps

* Consider using more advanced time series forecasting models (e.g., ARIMA, Prophet) that can capture seasonality and other time-series specific patterns, as linear regression might not fully capture the complexities of sales data.
* Analyze factors beyond just time that might influence sales (e.g., promotions, holidays, economic conditions) and include them in future forecasting models to potentially improve accuracy.

## Visualize total sales by Gender

### Summary:

### Data Analysis Key Findings

* The total sales for each payment method were calculated: Cash, Credit card, and Ewallet.
* A bar plot was generated showing the total sales for each payment method, with data labels displaying the exact sales values.

### Insights or Next Steps

* The visualization clearly shows the distribution of total sales across different payment methods, allowing for easy comparison.

## Visualize Total sales by time of the day (Morning, Afternoon, Evening and Night)

### Summary:

### Data Analysis Key Findings

* The 'Time' column was successfully processed to extract the hour and categorize each record into 'Morning', 'Afternoon', 'Evening', or 'Night'.
* The total sales for each time of day category were calculated by grouping the data and summing the 'Sales'.
* A bar plot was generated to visualize the total sales for each time of day, with data labels showing the exact sales figures.

### Insights or Next Steps

* The visualization clearly shows which time of day has the highest and lowest total sales, providing insights into customer shopping patterns throughout the day. This information could be used for staffing, marketing, or promotional strategies.

## Visualize total sales by products

### Summary:

### Data Analysis Key Findings

* The total sales for each product line were calculated by grouping the data by 'Product line' and summing the 'Sales'.
* A bar plot was generated to visualize the total sales for each product line, with data labels added to each bar showing the sales values.

### Insights or Next Steps

* "Fashion accessories" and "Food and beverages" are the top-performing product lines in terms of total sales.
* Further analysis could investigate the factors contributing to the sales performance of each product line.

## Visualize total sales by customer type

### Summary:

### Data Analysis Key Findings
* 'Member' customers generated higher total sales (\$323,680) compared to 'Normal' customers (\$299,006).

### Insights or Next Steps
* Investigate the reasons behind the higher sales from 'Member' customers.
* Develop strategies to encourage 'Normal' customers to become 'Member' customers to potentially increase overall sales.

## Sales Contribution by Various Factors

Here's a summary of how different factors are affecting sales, presented as percentage contributions based on our analysis:

**Payment Method:**
Based on the total sales by payment method, the approximate percentage contributions are:
- **Cash:** ~34.5%
- **Credit card:** ~30.5%
- **Ewallet:** ~35%
*Ewallet and Cash are the most preferred payment methods in terms of total sales.*

**Time of Day:**
Based on the total sales by time of day, the approximate percentage contributions are:
- **Morning:** ~19%
- **Afternoon:** ~45%
- **Evening:** ~35%
- **Night:** ~1%
*Afternoon is the peak time for sales, followed by Evening and Morning.*

**Customer Type:**
Based on the total sales by customer type, the percentage contributions are:
- **Member:** ~57%
- **Normal:** ~43%
*Member customers contribute significantly more to total sales.*

**Gender:**
Based on the total sales by gender, the approximate percentage contributions are:
- **Female:** ~57.5%
- **Male:** ~42.5%
*Female customers contribute more to total sales.*

## Technology and Innovation to Boost Sales

Here's how technology and innovation can potentially boost sales for each factor based on your analysis:

**Payment Method (Ewallet and Cash are most preferred):**

* **Enhanced Ewallet Experience:** Invest in a seamless and user-friendly mobile payment experience. This could include features like in-app purchasing, loyalty program integration, personalized offers based on purchase history, and faster checkout processes. Making the digital payment experience as convenient and rewarding as cash can encourage its adoption.
* **Digital Wallets and Contactless Payments:** Encourage the use of digital wallets (like Google Pay, Apple Pay) and contactless payment options in physical stores. This caters to tech-savvy customers and improves transaction speed, which can lead to a better customer experience and potentially higher sales volume during busy periods.
* **Cash Management Solutions:** For customers who prefer cash, implementing smart cash handling systems in-store can improve efficiency and reduce errors at the point of sale, leading to smoother transactions and happier customers.

**Time of Day Sales (Afternoon and Evening are peak):**

* **Targeted Promotions:** Implement dynamic pricing or targeted promotions through a mobile app or in-store displays that are active specifically during the peak Afternoon and Evening hours. This can incentivize purchases when traffic is highest, maximizing revenue during these key periods.
* **Optimized Staffing:** Use technology like predictive analytics to forecast staffing needs based on time of day sales trends. Ensuring adequate staff during peak hours improves customer service, reduces wait times, and can prevent lost sales due to long queues or lack of assistance.
* **Click and Collect/Delivery during Off-Peak:** Offer incentives for customers to use click and collect or delivery services during off-peak hours (Morning and Night). This can help distribute demand more evenly throughout the day, potentially increasing overall sales volume and operational efficiency.

**Customer Type (Members contribute significantly more):**

* **Personalized Member Experiences:** Leverage data analytics and AI to provide highly personalized product recommendations, offers, and loyalty rewards to members through a dedicated app or website. Tailoring the experience based on their purchase history and preferences can increase engagement and encourage them to spend more.
* **Gamification of Loyalty Programs:** Introduce gamification elements to the member program to make it more engaging and rewarding. This can increase member participation, encourage repeat purchases, and foster a stronger sense of loyalty.
* **Targeted Acquisition Campaigns:** Use data to identify potential new members who exhibit similar characteristics to your high-contributing member base. Running targeted digital marketing campaigns can be an effective way to acquire new, valuable customers.

**Gender (Female customers contribute more):**

* **Personalized Recommendations:** Use AI to provide personalized product recommendations based on browsing and purchase history. While being mindful of avoiding harmful stereotypes, tailoring suggestions based on individual preferences can be effective for all customers, including female customers who currently contribute more to sales.
* **Targeted Marketing:** Use data to inform targeted marketing campaigns that resonate with the purchasing behaviors observed in different gender groups. This doesn't necessarily mean gender-specific products, but rather tailoring the messaging and channels to reach relevant audiences effectively.
* **Optimized Product Placement (Online and In-Store):** Analyze purchasing patterns by gender to optimize product placement in both online stores and physical layouts. Making it easier for customers to find the products they are more likely to purchase can improve the shopping experience and boost sales.

## Visualize the sales prediction for the next 6 months, assuming a 50% increase

### Summary:

### Data Analysis Key Findings
* The average monthly sales from the historical data is \$71,161.90.
* A 50% increase on the average monthly sales amounts to \$35,580.95.
* The predicted sales for the next 6 months were adjusted by adding this \$35,580.95 increase to each original predicted value.
* The visualization clearly shows the historical sales trend, the original predicted sales trend, and the new predicted sales trend which is significantly higher due to the assumed 50% increase.

### Insights or Next Steps
* The visualization effectively demonstrates the potential impact of a 50% sales increase on future revenue.
* Further analysis could explore the feasibility and strategies required to achieve this assumed 50% increase in sales.

# V- Validate

## Validation Phase: Analyzing the Hypothesis and Potential Issues

**Hypothesis:** Technology and innovation can increase sales by 50% considering the impact of Payment Method, Time of Day, Customer Type, and Gender on sales.

**Analysis of Potential Issues with the Assumption and Hypothesis:**

While technology and innovation offer significant potential to increase sales, assuming a direct 50% increase based solely on the analyzed factors (Payment Method, Time of Day, Customer Type, Gender) has several potential pitfalls:

1. **Correlation vs. Causation:** Our analysis showed correlations between these factors and sales (e.g., higher sales from Members, peak sales in the afternoon/evening). However, correlation does not equal causation. Simply implementing technology related to these factors (like enhancing the e-wallet experience or targeted promotions) doesn't guarantee a proportional increase in sales. Other underlying factors might be driving these sales patterns.
2. **External Factors:** The hypothesis doesn't account for external factors that significantly impact retail sales, such as:
   * **Economic Conditions:** Recessions, inflation, or changes in consumer spending power can heavily influence sales regardless of technological advancements within the store.
   * **Competition:** Actions by competitors, including their own technological advancements or pricing strategies, can impact market share and sales.
   * **Seasonal Trends and Events:** While we looked at monthly trends, specific holidays, local events, or seasonal changes not explicitly captured in the current analysis can drive sales fluctuations.
   * **Changes in Consumer Preferences:** Evolving consumer tastes and preferences, independent of the current factors analyzed, can shift demand for certain product lines.
3. **Implementation Challenges:** The successful implementation of technology and innovation is not guaranteed. Issues such as:
   * **User Adoption:** Customers might not readily adopt new technologies (e.g., a new e-wallet feature).
   * **Technical Glitches:** Technology can fail, leading to frustrating customer experiences and lost sales.
   * **Integration Issues:** New systems might not integrate well with existing infrastructure.
   * **Cost of Implementation and Maintenance:** The cost of implementing and maintaining new technologies might outweigh the sales increase, impacting profitability.
4. **Over-reliance on Historical Data:** The 50% increase assumption might be based on historical trends and the current impact of the analyzed factors. Future market dynamics, technological shifts, and evolving consumer behavior might render historical patterns less predictive.
5. **Defining and Measuring "Technology and Innovation Impact":** It can be challenging to isolate the specific impact of technology and innovation on sales from other contributing factors. How will the "50% increase" be directly attributed to these initiatives?

**Testing the Hypothesis:**

To test the hypothesis more rigorously, a structured approach is needed, moving beyond simple correlation:

1. **Define Specific Initiatives:** Clearly define the specific technology and innovation initiatives to be implemented (e.g., launch a new loyalty app with personalized offers, introduce contactless payment in all stores, optimize staffing based on time-of-day analysis).
2. **Establish Baseline Metrics:** Measure current sales performance and the contribution of the analyzed factors *before* implementing the initiatives.
3. **Phased Rollout and A/B Testing:** If possible, implement initiatives in phases or use A/B testing in different store locations or customer segments to compare sales performance in groups exposed to the initiatives versus control groups.
4. **Collect Data on Implementation and Adoption:** Track the adoption rate of new technologies and any implementation challenges.
5. **Monitor Key Metrics:** Continuously monitor sales, customer behavior (e.g., e-wallet usage, time of visit), and other relevant metrics after implementation.
6. **Analyze and Attribute Impact:** Use statistical methods to analyze the collected data and attempt to isolate the impact of the technology and innovation initiatives on sales, accounting for external factors where possible.
7. **Iterate:** Based on the results, iterate on the initiatives, refine strategies, and adjust the hypothesis as needed.

In conclusion, while the analyzed factors highlight areas where technology and innovation can potentially drive growth, the 50% sales increase is a strong assumption. Rigorous testing and a comprehensive understanding of all influencing factors are crucial for validating this hypothesis.

# E-Extend

## Technology Investment and Strategy Recommendations (Based on DIVE Analysis)

Based on the insights gained from the Discover and Investigate phases, here are some technology investment and strategy recommendations for the legacy retail chain to compete with digital disruptors, with a focus on **Prioritization, Measurable Impact, and Phased Rollout**:

**Overarching Strategy:** Focus on creating a seamless, personalized, and engaging customer experience that leverages technology to bridge the gap between the physical and digital store. Prioritize initiatives that offer the highest potential for measurable impact on key business metrics (e.g., sales increase, customer acquisition/retention, operational efficiency). Implement changes in phases to allow for testing, learning, and optimization.

**Key Areas for Technology Investment and Strategy:**

1. **Enhance E-commerce and Omnichannel Capabilities:**
   * **Investment:** Develop or significantly upgrade the existing e-commerce platform. Invest in robust inventory management systems that provide real-time visibility across all channels (online and physical stores). Implement "buy online, pick up in-store" (BOPIS) and "ship from store" capabilities.
   * **Strategy:** Integrate the online and offline shopping experience. Allow customers to browse inventory online, check stock availability in nearby stores, purchase online for in-store pickup, or have online orders fulfilled from a local store for faster delivery. This caters to the convenience offered by digital disruptors while leveraging the physical store footprint.
   * **Prioritization & Measurable Impact:** **High Priority.** Directly impacts online sales, customer convenience, and inventory efficiency. Measure impact through online conversion rates, BOPIS/ship-from-store adoption rates, online revenue growth, and inventory accuracy.
   * **Phased Rollout:** Start with implementing real-time inventory visibility and a basic BOPIS system in a few pilot stores. Expand to more stores and introduce ship-from-store capabilities in later phases. Continuously refine the e-commerce user experience.
2. **Personalization and Customer Relationship Management (CRM):**
   * **Investment:** Implement a sophisticated CRM system and data analytics platform. Invest in AI and machine learning capabilities for customer segmentation and personalized recommendations (based on purchase history, browsing behavior, and demographics like gender and customer type).
   * **Strategy:** Use data to understand individual customer preferences and tailor product recommendations, promotions, and marketing messages. Create personalized experiences both online and in-store (e.g., through a mobile app that recognizes loyal customers and provides personalized offers upon entering the store). Strengthen the membership program with exclusive personalized benefits.
   * **Prioritization & Measurable Impact:** **High Priority.** Directly impacts customer loyalty, retention, and average transaction value. Measure impact through customer lifetime value, repeat purchase rate, personalized offer redemption rates, and conversion rates from personalized recommendations.
   * **Phased Rollout:** Begin with implementing a core CRM system and basic customer segmentation. Introduce personalized email marketing and website recommendations in an initial phase. Expand to in-app personalization and in-store personalized offers in later phases.
3. **In-Store Technology and Experience:**
   * **Investment:** Introduce in-store technology that enhances the shopping experience. This could include interactive digital displays, smart mirrors, mobile self-checkout options, and augmented reality (AR) features that allow customers to visualize products. Invest in reliable in-store Wi-Fi.
   * **Strategy:** Create a modern and engaging in-store environment that complements the online experience. Use technology to provide product information, offer personalized styling advice, reduce checkout times, and create a more interactive and enjoyable shopping journey.
   * **Prioritization & Measurable Impact:** **Medium to High Priority (depending on current state and budget).** Impacts in-store sales, customer satisfaction, and operational efficiency. Measure impact through average transaction value in stores with new tech, customer satisfaction scores, checkout times, and staff efficiency.
   * **Phased Rollout:** Start with providing reliable in-store Wi-Fi and introducing mobile self-checkout in a few high-traffic stores. Introduce interactive displays or smart mirrors in later phases based on pilot results and customer feedback.
4. **Optimizing Operations and Efficiency:**
   * **Investment:** Implement technology for workforce optimization and scheduling (potentially leveraging time-of-day sales data). Invest in automation for tasks like inventory counting and stock replenishment. Consider energy management systems for cost savings.
   * **Strategy:** Use technology to improve operational efficiency in stores and throughout the supply chain. Optimized staffing during peak hours (Afternoon and Evening) can improve service and capture more sales. Automation can reduce labor costs and improve accuracy.
   * **Prioritization & Measurable Impact:** **Medium Priority.** Primarily impacts cost savings and operational efficiency, indirectly impacting sales through improved service and inventory availability. Measure impact through labor costs, inventory shrinkage, and operational key performance indicators (KPIs).
   * **Phased Rollout:** Begin with implementing a workforce optimization tool for a few key stores. Introduce automation for specific inventory tasks in a pilot program. Expand successful initiatives across the chain.
5. **Data Analytics and Business Intelligence:**
   * **Investment:** Continuously invest in data analytics tools and expertise. Ensure the ability to collect, clean, and analyze data from all customer touchpoints (online, in-store, mobile app).
   * **Strategy:** Foster a data-driven culture. Use insights from data analysis (like the impact of payment methods, time of day, customer type, and gender on sales) to inform business decisions, refine strategies, and identify new opportunities for growth.
   * **Prioritization & Measurable Impact:** **High Priority (foundational).** Enables measurement of all other initiatives and informs strategic decisions. Measure impact through the adoption of data-driven decision-making, the ability to track KPIs for other initiatives, and the identification of new growth opportunities.
   * **Phased Rollout:** Establish a solid data infrastructure and reporting capabilities in the initial phase. Develop advanced analytics and predictive modeling capabilities in later phases. Provide training to staff on using data insights.
6. **Payment Technology:**
   * **Investment:** Continue to invest in secure and convenient payment options. Given the high contribution of Ewallet and Cash, ensure these are seamless. Explore newer technologies like contactless payments and integrated mobile payment solutions.
   * **Strategy:** Offer a variety of payment options that cater to customer preferences. Promote the benefits of digital payment methods for speed and convenience, potentially integrating them with loyalty programs.
   * **Prioritization & Measurable Impact:** **Medium to High Priority (depending on current payment infrastructure).** Impacts customer convenience, transaction speed, and potentially sales volume. Measure impact through transaction times, adoption rates of new payment methods, and customer feedback on payment options.
   * **Phased Rollout:** Ensure seamless integration and reliability of existing high-contributing payment methods (Ewallet, Cash). Introduce contactless payment options in phases across stores. Explore integrated mobile payment solutions in later phases.

By implementing these recommendations with a focus on measurable impact and a phased rollout, the legacy retail chain can strategically leverage technology and innovation to improve its competitiveness and drive sustainable growth in the face of digital disruption.

"""
