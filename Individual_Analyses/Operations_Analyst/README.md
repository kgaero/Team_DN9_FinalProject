# Final Project - DIVE Analysis as Operational Excellence Analysis

## Option B: Retail Chain Transformation

Client: Legacy retail chain losing market share
Dataset: Store performance and customer data


This document presents an in-depth operational excellence analysis using the DIVE framework.
It draws from data outputs (branch transactions, hours, sales) and Gemini recommendations.

## Discover: Process Efficiency, Resource Utilization, Operational Metrics

The initial phase focuses on uncovering baseline performance.

### 1. Process Efficiency  
From the transaction outputs and branch-level summaries:  

- **Peak hour inefficiency**: Sales and transactions peak at **13:00 and 19:00**, but throughput per transaction dips, suggesting stress on checkout capacity.  
- **Evening rush misalignment**: Resource coverage appears weaker in the 19:00 slot, creating potential bottlenecks.  
- **Consistency across mid-day**: Between **10:00–15:00**, process flow is more stable, indicating smoother operations.  

| Hour | Transactions | Total Sales | Avg Sale per Txn | Notes |
|------|--------------|-------------|------------------|-------|
| 10:00 | 3426 | 58,332 | 17.0 | Stable throughput |
| 13:00 | 3507 | 58,415 | 16.7 | Midday peak |
| 15:00 | 3412 | 58,594 | 17.2 | Balanced |
| 19:00 | 3821 | 63,090 | 16.5 | Evening spike, strain visible |

**Insight:** The 19:00 peak shows the **highest traffic but lowest efficiency per transaction** (AOV dips). This is a sign of bottlenecks at checkout or staff coverage mismatch.  

---

### 2. Resource Utilization  
From the branch-level breakdown:  

- **Alex Branch dominates**: Generates the highest transactions and sales volume, but shows signs of throughput inefficiency at peak.  
- **Cairo Branch**: Slightly lower sales per transaction, potentially due to product mix skewed toward low-margin goods.  
- **Giza Branch**: Stronger balance between transactions and sales, indicating better per-resource utilization.  

| Branch | Transactions | Total Sales | Avg Sale per Txn | Efficiency Signal |
|--------|--------------|-------------|------------------|------------------|
| Alex   | 17,337 | 287,148 | 16.6 | High volume, slightly low yield |
| Cairo  | 12,482 | 204,997 | 16.4 | Lower basket size |
| Giza   | 13,107 | 218,504 | 16.7 | Balanced performance |

**Insight:** Cairo may be underutilizing resources (same effort, lower yield), while Alex is overburdened during peak hours.  

---

### 3. Operational Metrics  
Key system-wide KPIs from the dataset:  

- **Average basket size**: ~1.9 items per transaction, relatively flat across branches.  
- **Sales per transaction**: Range 16.4–17.2, showing narrow dispersion (consistent pricing & promotions).  
- **Transaction growth**: Evening and mid-day peaks drive ~35% of daily sales volume.  

| Metric | Value | Observation |
|--------|-------|-------------|
| Basket Size | 1.9 items | Flat across branches — opportunity for cross-sell/upsell |
| Sales/Txn | 16.4 – 17.2 | Narrow band, suggests stable price architecture |
| Peak Share | 35% of daily | Concentrated in two windows (13:00, 19:00) |

**Insight:** Stability across operational metrics is good, but it also indicates **limited differentiation strategies** — no branch is standing out in customer yield.  



# Investigate: Operational Factors and Bottlenecks  

The **Investigate** phase digs into *why* the observed inefficiencies exist and what operational factors drive success, using branch comparisons, temporal patterns, and product-line margins.  

---

## Key Drivers of Success (Highlights)  

- **Staffing Consistency (Cairo):** Peak-hour resilience shows that well-timed staffing prevents ticket erosion.  
- **Efficient Tender Mix:** Branches with higher e-wallet usage avoid checkout slowdowns.  
- **Margin Discipline (Giza):** Focusing on profitable categories drives sustainable performance even at lower revenue.  
- **Timely Replenishment:** Proactive restocking during peaks sustains basket size and customer satisfaction.  

---

## 1. Root Causes and Success Drivers  

- **Staffing misalignment at peaks (Alex):**  
  Average ticket *drops −$0.49* during 13:00–19:00, suggesting long queues and incomplete baskets. Cairo actually improves (+$0.22), highlighting stronger staffing coverage as a success driver.  

- **Checkout tender mix (Alex):**  
  Cash share increases **+1.1%** during peaks, slowing checkout speed. Cairo/Giza show <0.4% change, suggesting that efficient tender adoption is a driver of smoother throughput.  

- **Margin trade-offs:**  
  Alex generates the **highest revenue (~$263K)** but lowest margin (**14.05%**). Giza demonstrates the opposite: lower revenue (~$149K) but highest margin (**20.36%**). This indicates that disciplined product mix management is a driver of margin success.  

- **Inventory timing (Alex):**  
  Dips in units/transaction for **Food & Beverages (−0.013)** and **Electronics (−0.010)** during peak hours suggest stock-outs or late replenishment. In contrast, Cairo’s steadier units/txn suggests well-timed replenishment is a driver of peak performance.  

- **Product line leverage:**  
  Health & Beauty yields ~18.25% margin in Alex, but contribution to sales share is not dominant. Giza, with a higher relative share of high-margin categories, shows that success is driven by maximizing placement and bundling of profitable product lines.  

- **Consistent peak performance (Cairo):**  
  Cairo stands out as a “success case” in handling peaks. Despite heavy volume, it maintains stable average ticket, suggesting that operational consistency (staffing, checkout flow, replenishment) directly drives resilience.  

---

## 2. Supporting Metrics  

| Branch | Revenue ($) | Avg Ticket ($) | Margin % | Peak Δ Avg Ticket | Cash Share Δ | Key Signals |
|--------|-------------|----------------|----------|-------------------|--------------|-------------|
| Alex   | 263,192 | 22.70 | 14.05% | −0.49 | +1.1% | High rev, weak peak perf, slow checkout |
| Cairo  | 257,839 | 23.00 | 13.98% | +0.22 | +0.4% | Stable perf, resilient peaks |
| Giza   | 149,576 | 13.90 | 20.36% | −0.12 | +0.2% | Low rev, high margin |

---

## 3. Testable Hypotheses  

1. **Staffing Alignment (Alex)**  
   - *Hypothesis:* Adding staff 16:00–19:00 increases throughput and average ticket.  
   - *Metrics:* Transactions/hour, avg ticket, queue length.  
   - *Test:* Two-sample t-test or OLS regression.  
   - *Decision Rule:* If avg ticket ↑ >5% and queue time <3 min, scale staffing change.  

2. **E-Wallet Adoption (Alex)**  
   - *Hypothesis:* Incentivizing e-wallet use reduces service time.  
   - *Metrics:* % e-wallet share, transaction time, throughput.  
   - *Test:* t-test on throughput before vs after promotion.  
   - *Decision Rule:* If e-wallet share ↑ 2–3% and throughput ↑ 5–10%, scale promotion.  

3. **Planogram Transfer (Giza)**  
   - *Hypothesis:* Replicating Alex’s Health & Beauty planogram in Giza raises margin mix.  
   - *Metrics:* Health & Beauty sales and margin contribution.  
   - *Test:* Before/after t-test or ANOVA on product-line sales.  
   - *Decision Rule:* If margin ↑ ≥2 points, roll out to other branches.  

4. **Inventory Timing (Alex)**  
   - *Hypothesis:* Earlier replenishment of Food & Beverages + Electronics boosts units/txn.  
   - *Metrics:* Units/txn during 13:00–19:00, OOS rate.  
   - *Test:* t-test on units/txn peak vs off-peak after change.  
   - *Decision Rule:* If units/txn ↑ ≥5% and OOS ↓, make replenishment permanent.  

---

## 4. Targeted Experiments  

| Pilot | Branch | Intervention | Expected Outcome | KPIs | Guardrails |
|-------|--------|--------------|------------------|------|------------|
| Staffing boost | Alex | +2–3 staff at checkout (16:00–19:00) | Higher throughput & avg ticket | Txns/hr, Avg ticket | Queue <3min; stop if >5min |
| E-wallet promo | Alex | 5% discount/loyalty points for e-wallet at peak | Faster checkout, ↑ throughput | Txns/hr, E-wallet % | Guard avg ticket; stop if margin erodes |
| Planogram test | Giza | Health & Beauty placement/bundle pilot | ↑ share of high-margin line | Margin %, Line sales | Stop if no +2pt margin lift |
| Replenishment | Alex | Add F&B & Electronics deliveries at 14:00 | ↑ units/txn, fewer OOS | Units/txn, OOS rate | Halt if no gain or ↑ shrinkage |

---

## 5. Insights  

- **Revenue vs margin is a trade-off.** Alex proves high volume can erode profitability without margin discipline.  
- **Bottlenecks compound at peaks.** Staffing gaps, slower tender mix, and stockouts all converge 13:00–19:00, especially in Alex.  
- **Success factors are replicable.** Cairo shows that operational consistency in staffing, checkout flow, and replenishment can sustain performance under pressure.  
- **Margin leverage is underutilized.** Giza’s high-margin model highlights the potential for other branches to emphasize profitable categories without sacrificing throughput.  



## Executive Summary
This report presents an extensive analysis of a legacy retail chain’s operational performance, 
customer behavior, and revenue distribution based on the provided dataset outputs. 
The primary goal is to restructure operations to compete with digital disruptors while optimizing 
process efficiency, resource utilization, and customer engagement. 
The analysis integrates transaction patterns, revenue contributions, customer segmentation, 
product line performance, and time-based trends to provide actionable recommendations. 

The report focuses on four key pillars:
1. Discover – Identifying inefficiencies and underutilized opportunities.
2. Investigate – Understanding drivers of performance and bottlenecks.
3. Validate – Testing operational improvement hypotheses.
4. Extend – Building a roadmap for sustainable optimization.

Our findings reveal that while the retail chain maintains relatively balanced customer traffic 
throughout the week, certain hours and product lines significantly outperform others, creating 
opportunities for targeted promotions and improved resource allocation. 
High-margin product categories and peak transaction windows can be leveraged for maximizing 
profitability, while underperforming segments can be addressed with strategic interventions.

## Dataset Overview
The dataset consists of sales transactions containing details such as invoice ID, branch, city, 
customer type, gender, product line, unit price, quantity, tax, sales, date, time, payment method, 
cost of goods sold (COGS), gross margin percentage, gross income, rating, and month.

This rich dataset enables multi-dimensional analysis, providing insight into sales patterns 
across demographic segments, time intervals, product categories, and payment preferences.

## Key Tables and Insights
### 1. Customer Type Distribution
| Customer Type | Transactions (%) | Revenue (%) |
|---------------|------------------|-------------|
| Member        | 50.1             | 50.3        |
| Normal        | 49.9             | 49.7        |

Insight: The distribution between Member and Normal customers is nearly even, suggesting that 
both groups are equally important to revenue generation. Loyalty programs should be tailored 
to encourage repeat purchases from Members while simultaneously converting Normal customers 
into Members to boost retention rates.

Recommendation: Implement segmented loyalty incentives that reward Members with exclusive 
discounts and early product access while offering Normal customers targeted promotions 
to drive sign-ups.

### 2. Hourly Transaction Share by Customer Type
| Hour | Member (%) | Normal (%) |
|------|------------|------------|
| 10   | 10.27      | 10.04      |
| 11   | 8.93       | 9.11       |
| 12   | 8.89       | 9.17       |
| 13   | 10.11      | 10.55      |
| 14   | 8.35       | 8.42       |
| 15   | 10.07      | 10.23      |
| 16   | 7.89       | 7.50       |
| 17   | 7.34       | 7.39       |
| 18   | 9.58       | 9.06       |
| 19   | 11.11      | 11.24      |
| 20   | 7.47       | 7.29       |

Insight: Transactions peak during late morning (10 AM - 1 PM) and evening hours (6 PM - 8 PM). 
This aligns with consumer shopping habits before work, during lunch breaks, and after work hours.

Recommendation: Adjust staffing schedules to align with peak hours, ensuring faster service 
and improved customer experience during high-traffic periods. Introduce time-bound offers 
during slower hours to spread foot traffic more evenly.

### 3. Weekday Transaction Share by Customer Type
| Day       | Member (%) | Normal (%) |
|-----------|------------|------------|
| Monday    | 14.26      | 14.19      |
| Tuesday   | 14.37      | 14.37      |
| Wednesday | 14.23      | 14.13      |
| Thursday  | 14.32      | 14.50      |
| Friday    | 14.08      | 14.15      |
| Saturday  | 14.36      | 14.35      |
| Sunday    | 14.38      | 14.30      |

Insight: Transaction distribution is remarkably stable across the week, indicating 
consistent daily customer engagement.

Recommendation: Since no single day dominates, weekend-specific promotions should focus 
on increasing average transaction value (ATV), while weekday promotions could aim at 
driving incremental visits from local working professionals.

## Operational Efficiency Opportunities
From the provided outputs, several operational improvement opportunities emerge:
- **Product Affinity Optimization**: Introduce bundled deals for top-affinity products 
to encourage cross-selling.
- **Targeted Promotions**: Launch promotions aligned with peak transaction hours to 
maximize conversion rates.
- **Staff Allocation**: Reallocate staffing resources based on hourly and daily transaction 
patterns to reduce wait times and improve service.
- **Inventory Management**: Synchronize stock replenishment schedules with demand peaks 
to avoid stockouts and overstock situations.

## Extended Recommendations
1. **Digital Transformation** – Develop a robust e-commerce platform integrated with 
loyalty programs, enabling omnichannel sales and personalized offers.
2. **Data-Driven Decision Making** – Invest in analytics infrastructure to monitor 
real-time sales and customer behavior, enabling agile responses to demand shifts.
3. **Customer Retention** – Implement AI-driven churn prediction models to proactively 
engage at-risk customers with personalized incentives.
4. **Operational Automation** – Leverage automation tools for demand forecasting, 
inventory restocking, and workforce scheduling.
5. **Employee Training** – Equip staff with training in upselling, cross-selling, 
and customer engagement to maximize revenue per interaction.

## Conclusion
The data indicates that this retail chain has strong fundamentals in customer engagement 
and consistent traffic throughout the week. However, strategic adjustments in promotions, 
staffing, and product bundling can enhance both revenue and customer satisfaction.
By focusing on operational excellence and leveraging analytics-driven insights, 
the chain can strengthen its market position against digital disruptors while improving 
profit margins and brand loyalty.
# Retail Chain Operational Excellence Analysis
