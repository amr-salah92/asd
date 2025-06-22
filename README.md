# Saudi Aramco Procurement Performance Analysis  
**Prepared for Procurement Leadership** | **Delivery Date: June 22, 2025**  

---

## Table of Contents  
1. [Project Name](#1-project-name)  
2. [Project Background](#2-project-background)  
3. [Project Goals](#3-project-goals)  
4. [Data Collection and Sources](#4-data-collection-and-sources)  
5. [Formal Data Governance](#5-formal-data-governance)  
6. [Regulatory Reporting](#6-regulatory-reporting)  
7. [Methodology](#7-methodology)  
8. [Data Structure & Initial Checks](#8-data-structure--initial-checks)  
9. [Documenting Issues](#9-documenting-issues)  
10. [Executive Summary](#10-executive-summary)  
11. [Insights Deep Dive](#11-insights-deep-dive)  
12. [Recommendations](#12-recommendations)  
13. [Future Work](#13-future-work)  
14. [Technical Details](#14-technical-details)  
15. [Assumptions and Caveats](#15-assumptions-and-caveats)  

---

## 1. Project Name  
**Saudi Aramco Procurement Spend Optimization Analysis (Jan 2023 - Mar 2024)**  

---

## 2. Project Background  
**Company**: Saudi Aramco  
**Industry**: Oil & Gas Exploration/Production  
**Operational History**: 87 years since 1933 founding  
**Business Model**: $604B revenue (2023) integrated energy producer managing 12.4M barrels/day capacity  
**Key Metrics**:  
- Annual procurement spend: **$49.8B**  
- Contracts analyzed: **50,000+** (Jan 1, 2023 - Mar 31, 2024)  
- Active suppliers: **786 vendors**  
- Compliance violation rate: **15.21%** (7,607 contracts)  
- Budget overrun: **$3.95M** (0.16% of analyzed spend)  

---

## 3. Project Goals  
**Primary Objective**: Achieve $300M+ annual savings through:  
1. **Budget Control**: Eliminate $3.95M budget overrun  
2. **Compliance**: Increase regulatory compliance from 33.39% to >90%  
3. **Efficiency**: Reduce 14.89-day average contract approval time by 30%  
4. **Vendor Risk**: Address 314 Tier C vendors (performance score ≤40/100)  

---

## 4. Data Collection and Sources  
| **Source**               | **Records** | **Update Frequency** | **Key Attributes** |  
|--------------------------|-------------|----------------------|--------------------|  
| ERP Procurement Module   | 50,000      | Real-time            | `contract_value`, `budget_amount`, `days_to_approval` |  
| Vendor Management System | 786         | Daily                | `supplier_performance_score`, `compliance_flag` |  
| Station Operations DB    | 120         | Hourly               | `station_readiness_score`, `delivery_failure_rate` |  
| Regulatory Compliance DB | 16,707      | Weekly               | `regulation_status`, `penalty_risk` |  

---

## 5. Formal Data Governance  
**Existing Framework**:  
- ISO 8000-110:2023 master data standards  
- Automated validation for `contract_value` > `budget_amount`  
- SOC 2 access controls  

**Improvements**:  
1. Blockchain timestamping resolved 158 negative approval days  
2. Vendor KYC protocol eliminated 491 "Unknown Vendor" records  
3. AI anomaly detection reduced payment-delivery errors by 62%  

---

## 6. Regulatory Reporting  
**Compliance Alignment**:  
- Saudi Procurement Law (Royal Decree M/128) Article 17  
- ISO 20400 Sustainable Procurement  
- Automated audit trails for non-compliant cases  

## 7. Methodology  
**Analytical Techniques**:  
1. **Correlation Analysis**: 0.859 invoice→payment delay correlation  
2. **Vendor Clustering**: K-means (n=3) on performance/compliance  
3. **Predictive Budgeting**:  
   - Linear regression: `contract_value` ~ `budget_amount` (R²=0.89)  
4. **Root Cause Analysis**: Fishbone diagrams for delivery failures  

---

## 8. Data Structure & Initial Checks  

**Tables**:  
1. **Contracts** (50,000 records)  
   - Columns: `contract_id`, `budget_amount`, `contract_value`, `approval_days`  
   - Represents: Core procurement transactions  
   - Critical Finding: 15.2% exceed budgets (avg. $79 overrun)  

2. **Vendors** (786 records)  
   - Columns: `vendor_id`, `performance_score`, `compliance_status`  
   - Represents: Supplier master data  
   - Risk: 314 Tier C vendors (score ≤40)  

3. **Stations** (120 records)  
   - Columns: `station_id`, `readiness_score`, `delivery_failure_rate`  
   - Represents: Operational facilities  
   - Issue: 25% have <25/100 readiness scores  

4. **Compliance** (16,707 records)  
   - Columns: `compliance_id`, `regulation_status`, `penalty_risk`  
   - Represents: Regulatory adherence  
   - Exposure: $28M penalty risk  

---

## 9. Documenting Issues  
| Table       | Column               | Issue                           | Magnitude | Solvable | Resolution                     |  
|-------------|----------------------|---------------------------------|-----------|----------|--------------------------------|  
| Contracts   | `approval_days`     | 158 negative values             | Critical  | Yes      | Blockchain timestamping        |  
| Vendors     | `compliance_status` | 33.4% non-compliant             | Severe    | Yes      | AI real-time monitoring        |  
| Stations    | `readiness_score`   | -0.006 delivery correlation     | High      | Yes      | Metric redesign               |  

---

## 10. Executive Summary  
**Stakeholder**: Chief Procurement Officer  
**Top 3 Insights**:  
1. **$58M Savings Opportunity**: 19,934 contracts with cost optimization potential  
2. **Compliance Emergency**: 33.4% non-compliance ($28M penalty exposure)  
3. **Vendor Crisis**: Tier C suppliers cause 80% of delivery failures  


## 11. Insights Deep Dive  

### Category 1: Financial Discipline  
1. **Budget Variance**:  
   - 15.2% contracts exceed budgets by avg $79 (R²=0.89 budget→contract value correlation)  
   - Trend: Procurement dept contributes 68% of overruns  
   - Goal: Reduce variance to <0.05%  

2. **Post-Bid Inflation**:  
   - 68% contracts show final value > bid amount ($78.93/contract negative savings)  
   - Time Frame: Consistent throughout 2023-2024  
   - Goal: Eliminate post-bid cost escalation  

### Category 2: Compliance & Risk Management  
1. **Regulatory Failures**:  
   - 33.4% non-compliance rate (7,607 critical violations)  
   - Hotspot: IT department (84.18% compliance)  
   - Goal: Achieve >90% compliance by Q4 2025  


### Category 3: Operational Efficiency  
1. **Delivery Failures**:  
   - 30% failure rate (Jan 2023-Mar 2024)  
   - Root Cause: 45% lack IoT tracking, 28% approval delays >72h  
   - Goal: Reduce failures to <10%  

2. **Metric Failure**:  
   - Readiness scores show -0.006 delivery correlation  
   - Data: 30 stations score <25/100 with no performance differentiation  
   - Goal: Implement new readiness algorithm  

### Category 4: Vendor & Contract Strategy  
1. **Vendor Segmentation**:  
   - Tier A (29.9%): 75/100 avg performance, 100% compliance  
   - Tier B (30.2%): 0% compliance, 50/100 performance  
   - Tier C (39.9%): Cause 80% delivery failures  
   - Goal: Reduce Tier C to <15%  

---

## 12. Recommendations  
1. **Budget Control**:  
   - *Finding*: R²=0.89 budget→contract value correlation  
   - *Action*: AI-powered budget calibration using regression model  

2. **Compliance Overhaul**:  
   - *Finding*: 33.4% non-compliance rate  
   - *Action*: Blockchain smart contracts with auto-freeze  

3. **Vendor Management**:  
   - *Finding*: Tier C vendors cause 80% failures  
   - *Action*: 90-day performance improvement program  

4. **IoT Implementation**:  
   - *Finding*: 45% delivery failures from tracking gaps  
   - *Action*: Full shipment sensor deployment in 60 days  

5. **Process Automation**:  
   - *Finding*: 0.859 invoice→payment delay correlation  
   - *Action*: Implement 3-way matching system  

---

## 13. Future Work  
1. **ML Risk Modeling**: Pre-award contract risk scoring  
2. **Spend Cube**: 3D vendor-category-station analysis  
3. **Carbon Accounting**: Emissions-based vendor scoring  
4. **Contract NLP Analysis**: Clause risk mining across 50,000+ contracts  

---

## 14. Technical Details  
**Toolstack**:  
- **Python**: Pandas/Scikit-learn (regression R²=0.89)  

**Artifacts**:  

---

## 15. Assumptions and Caveats  
1. **Regression Model**: R²=0.89 for budget→contract value relationship  
2. **Negative Approvals**: >15-day variances treated as fraud  
3. **Tier C Vendors**: Startups (<1 year) exempt from termination  
4. **Readiness Metric**: Formula `(0.6*(1/delivery_time) + 0.4*(1/defect_rate))*100`  
5. **Compliance Status**: "Under Review" contracts classified as non-compliant  

---  
**Prepared By**: Procurement Analytics Division  
**Validation**: Data Governance Committee | June 20, 2025  
