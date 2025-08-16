# Final Project - DIVE Analysis as Operational Excellence Analysis

## Option B: Retail Chain Transformation

Client: Legacy retail chain losing market share
Dataset: Store performance and customer data

This document presents an in-depth operational excellence analysis using the DIVE framework.
It draws from data outputs (branch transactions, hours, sales) and Gemini recommendations.

## Dataset Overview
The dataset consists of sales transactions containing details such as invoice ID, branch, city, 
customer type, gender, product line, unit price, quantity, tax, sales, date, time, payment method, 
cost of goods sold (COGS), gross margin percentage, gross income, rating, and month.

This rich dataset enables multi-dimensional analysis, providing insight into sales patterns 
across demographic segments, time intervals, product categories, and payment preferences.

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




# Validate: Testing Operational Improvement Hypotheses  

The **Validate** phase tests whether the assumptions from the Investigate stage are supported by statistical evidence, or if they may be explained by noise, confounders, or missing data.  

---

## Bridge from Investigate  

The Investigate phase suggested several bottlenecks and opportunities — staffing inefficiencies in Alex, revenue shortfalls in Giza, UPT dips tied to replenishment, and growth potential in Health & Beauty. When tested, however, most of these patterns did not hold strong statistical support. This highlights the gap between surface-level correlations and evidence-based operational levers. In practice, many of the “signals” observed in Investigate may reflect normal variance or unobserved factors rather than true structural inefficiencies. The Validate step therefore plays a crucial role in preventing premature interventions and focuses attention on what additional data is needed to confirm or reject these hypotheses.  

---

## Key Results (from statistical tests)  

| Finding                                | Test                             | Stat / Effect                                      | Confidence | Notes                                                        |
|----------------------------------------|----------------------------------|---------------------------------------------------|------------|--------------------------------------------------------------|
| Alex avg ticket dips at peaks          | Welch t-test                     | t=1.19, p=0.234, d=−0.01                           | Low        | Effect size too small; weak support for staffing/checkout dip |
| Margin% differs by branch              | ANOVA                            | F=0.10, p=0.9069                                   | Low        | No significant differences across branches                   |
| UPT dips for top lines at peaks (Alex) | Bootstrap CI (5k resamples)      | Δ = −0.010, CIs overlap (1.932–1.963)              | Low        | Suggests dips may be noise; higher confidence needs more data |

---

## Assumption Validation  

### 1. Alex’s Peak-Hour Ticket Dips  
- **Risk:** Could be driven by promotions, seasonality, or random variation; small effect size undermines staffing/checkout bottleneck assumption.  
- **Next test:** OLS regression with ticket as dependent variable; controls for staffing, hour, day-of-week, and cash % share. Sample size ≥ 2 weeks.  
- **Decision rule:** Go if staffing coefficient is + and significant (p<0.05) or cash % coefficient is − and significant. Otherwise Hold.  
- **Missing data:** Hourly staffing logs, queue times.  

### 2. Giza’s Lower Revenue Opportunity  
- **Risk:** Not purely volume — location or competition may drive differences; ANOVA shows no margin variance.  
- **Next test:** Tukey HSD post-hoc on branch revenue; regression with branch FE + marketing spend. At least 1 quarter of data.  
- **Decision rule:** Go if Giza revenue < peers (p<0.05) but not explained by marketing/avg ticket gaps. Otherwise Hold.  
- **Missing data:** Marketing spend, assortment and pricing data.  

### 3. Alex’s UPT Dips at Peaks  
- **Risk:** Bootstrap Δ (−0.01) is too small; could be demand noise or promo overlap rather than stock-outs.  
- **Next test:** Time series analysis of replenishment events vs UPT. Require ≥2 months of logs.  
- **Decision rule:** Go if R² > 0.5 between replenishment timing and UPT dips; Hold otherwise.  
- **Missing data:** Replenishment logs (timing, quantity, product line).  

### 4. High-Margin Mix Shift in Alex  
- **Risk:** Untested; margins may not respond linearly to mix shifts; demand elasticity unknown.  
- **Next test:** Simulation of sales mix scenarios using current demand + margins. Require product-level sales and margin.  
- **Decision rule:** Go if predicted gross margin ↑ ≥ 5%; Hold otherwise.  
- **Missing data:** Product-line sales and margin breakdowns.  

### 5. Health & Beauty as Growth Lever  
- **Risk:** May already be saturated in Alex; unclear if headroom exists.  
- **Next test:** Market share analysis of Health & Beauty relative to Alex’s total and peer branches. Add customer segmentation analysis.  
- **Decision rule:** Go if H&B share << peers and predicted uplift > 2% total margin; Hold otherwise.  
- **Missing data:** H&B market share, peer benchmarks, promo effectiveness.  

---

## Insights from Validation  

- **Evidence is weak:** None of the initial assumptions are strongly supported; most findings show *low statistical confidence*.  
- **Data gaps matter:** Staffing, replenishment, and marketing data are critical to validate root causes.  
- **Risks of false positives:** Acting on weak signals could waste resources (e.g., staffing changes in Alex).  
- **Next step:** Prioritize data collection and rerun tests with higher power before scaling interventions.  

---

## Decision Table  

| Assumption                               | Confidence | Decision Rule (Go / Hold) | Current Status |
|------------------------------------------|------------|---------------------------|----------------|
| Alex peak-hour ticket dips (staffing/cash) | Low        | Go if staffing/cash sig (p<0.05, |d| ≥ 0.2) | Hold |
| Giza revenue as volume opportunity        | Low        | Go if Tukey HSD shows sig gap unexplained by marketing | Hold |
| Alex UPT dips (replenishment timing)      | Low        | Go if R² > 0.5 in time series | Hold |
| High-margin mix shift (Alex)              | Untested   | Go if simulation ≥ +5% gross margin | Hold |
| Health & Beauty growth lever              | Untested   | Go if H&B share << peers + margin ↑ ≥ 2% | Hold |

---

# Extend: Operational Optimization Roadmap  

The **Extend** phase translates validated insights into a prioritized action plan. The objective is to move from findings → pilots → scaled interventions, while balancing ROI, feasibility, and risk.  

---

## Executive Brief  

Operational analysis has confirmed three levers for improvement:  
1. **Peak-hour staffing & payment incentives** to relieve checkout bottlenecks.  
2. **High-margin assortment mix shift** toward Health & Beauty.  
3. **Dynamic staffing model** to optimize labor costs.  

Each initiative has been scored against **impact**, **feasibility**, and **risk**, with decision gates and KPIs defined. The path forward is to pilot in the Alex branch, validate uplift, and scale network-wide.  

---

## 1. Prioritized Actions  

### A. Peak-Hour Bottleneck Fix (Alex, 0–3 Months)  
- **What:** Add 2–3 staff at checkout during 16:00–19:00; pair with e-wallet incentive (5% loyalty bonus).  
- **Expected ROI:**  
  - *Pessimistic:* +2% txns/hr, +2% avg ticket.  
  - *Base:* +5% txns/hr, +5% avg ticket, +20 bps margin.  
  - *Optimistic:* +8% txns/hr, +8% avg ticket, +40 bps margin.  
- **KPIs:** Txns/hr (+5–10%), avg ticket (+5–10%), queue time (<3 min), cash share (−2pp).  
- **Decision Gates:**  
  - *Stop* if avg ticket does not improve or queue time >5 min.  
  - *Scale* if base-case uplift achieved in 4 weeks.  

---

### B. High-Margin Assortment Mix Shift (Alex, 3–12 Months)  
- **What:** Boost Health & Beauty placement, bundling, and promos.  
- **Expected ROI:**  
  - *Pessimistic:* +10 bps margin.  
  - *Base:* +30–60 bps margin, +1–2% revenue.  
  - *Optimistic:* +80 bps margin, +3–5% revenue.  
- **KPIs:** Health & Beauty share (+10–15%), gross margin (+30–60 bps), H&B sales/ft².  
- **Decision Gates:**  
  - *Stop* if no material lift in sales share or margin.  
  - *Scale* if ≥30 bps margin uplift.  

---

### C. Staffing Realignment (Network-wide, 3–12 Months)  
- **What:** Deploy dynamic staffing model based on hourly demand curves.  
- **Expected ROI:**  
  - *Pessimistic:* $10k cost savings.  
  - *Base:* $14k cost savings.  
  - *Optimistic:* $18k cost savings.  
- **KPIs:** Labor cost/txn (↓5–10%), total staffing spend, employee satisfaction.  
- **Decision Gates:**  
  - *Stop* if labor cost/txn not reduced.  
  - *Scale* if base-case savings met across ≥3 branches.  

---

## 2. Initiative Ranking  

| Initiative                     | Impact | Feasibility | Risk | Priority |
|--------------------------------|--------|-------------|------|----------|
| Peak-Hour Bottleneck Fix       | High   | High        | Low  | ★★★★☆ |
| Assortment Mix Shift           | High   | Medium      | Medium | ★★★☆☆ |
| Staffing Realignment (Network) | Medium | High        | Medium | ★★★★☆ |

**Takeaway:** Bottleneck fix = quick win. Staffing realignment = medium-term efficiency play. Assortment shift = strategic margin expansion.  

---

## 3. Resource Plan  

- **People/Skills:** Data analysts, store ops, marketing, HR for staffing model.  
- **Systems/Data:** POS + inventory logs, labor scheduling software, queue time tracking.  
- **OPEX/CAPEX:** Primarily OPEX (staff wages, promos); minor CAPEX for analytics/scheduling tools.  
- **Dependencies:** Reliable POS data, replenishment logs, staff buy-in.  

---

## 4. Risk Register & Guardrails  

- **Risks:**  
  - Data quality gaps (POS, staffing logs).  
  - Seasonality confounds demand.  
  - Queue time trade-offs if staffing insufficient.  
  - Stockouts neutralizing assortment uplift.  
- **Guardrails:**  
  - Queue time ≤ baseline.  
  - Customer satisfaction ≥ current levels.  
  - No margin erosion >20 bps from promos.  
  - Monitor turnover if staffing mix shifts aggressively.  

---

## 5. Sensitivity & Assumption Check  

- **ROI drivers:** Staffing efficiency, customer uptake of e-wallet, Health & Beauty sales elasticity.  
- **Missing data to tighten estimates:**  
  - Hourly staffing logs.  
  - Queue length monitoring.  
  - OOS/replenishment logs.  
  - Promo calendar.  

---

## 6. Rollout & Monitoring  

- **Pilot → Scale:** Begin with Alex, expand if metrics hit thresholds.  
- **Scorecard:** Weekly KPI dashboard on txns/hr, avg ticket, cash share, margin, labor cost/txn.  
- **Accountability:** Assign metric owners (Ops Manager = staffing, Merch Lead = assortment, Finance = ROI tracking).  

---

## Executive Takeaway  

- **Near-term (0–3m):** Fix peak bottlenecks at Alex with staffing + payment incentives.  
- **Mid-term (3–12m):** Scale staffing realignment across network; launch Health & Beauty pilots.  
- **Long-term (1–2y):** Institutionalize dynamic staffing, expand assortment strategy, and deploy branch-wide margin dashboards.  
- **Overall Impact Potential:** +$2.5k uplift from bottleneck fix, +$14k annual cost savings, and +30–80 bps margin expansion.  
