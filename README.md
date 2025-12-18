

# Business School Performance Analytics & Retention Strategy

## Project Overview

This project delivers a comprehensive, stakeholder-centric Power BI and Machine Learning solution designed to analyze five years of institutional data (2020–2025). The system integrates enrolment records, academic outcomes, and demographic profiles to empower University Executives, Course Directors, and Unit Convenors to visualize retention patterns and operationalize evidence-based interventions.

**Core Objective:** Drive a "Retain & Rebalance" strategy that protects high-yield programs while identifying inefficiencies in under-performing cohorts.

---

## 1. Executive Summary: The "Retain & Rebalance" Strategy
**Data Scope:** 52,000+ course enrolments and ~22,000 students analysed over a 5-year period.
**Key Recovery Metric:** Institutional retention recovered to **90% in 2024**, effectively rebounding from a low point in 2022.
**Strategic Pivot:** The analysis supports a shift from broad-spectrum support to targeted interventions for specific "at-risk" segments, optimizing the allocation of teaching resources.



---

## 2. Key Insights by Stakeholder Persona

### 🏛️ For University Executives: Financial Efficiency & Strategic Allocation

* **Revenue Protection:** The Bachelor of Commerce remains the central revenue engine, representing **37.6%** of total enrolments. Protecting retention in this program is critical for financial sustainability.
**The "High-Performance" Standard:** Students in **Combined Degrees, Full-Time, and Internal (On-Campus)** modes exhibit a superior retention rate of **97%** with a low drop-out rate of 2.28%.


* **The "At-Risk" Financial Drain:** The Single Degree, Part-Time, and External cohort retains at only **76%**. This segment drives the majority of attrition and requires urgent strategic review.
**Portfolio Inefficiency:** There is a "long tail" of resource dilution; the bottom 20 courses (primarily complex combined degrees) each contribute less than **0.02%** of enrolments, diffusing teaching capacity without delivering scale.



### 🎓 For Course Directors: Progression Bottlenecks & Transfer Risk

**Churn vs. Attrition:** The course transfer rate was **18.47%** in 2024. While some movement is natural, high internal churn indicates instability in specific pathways.

* **Identifying Transfer Triggers:** Analysis reveals that transfer decisions are often driven by life circumstances rather than academic failure. For example, high-performing domestic students often transfer when shifting from Full-Time to Part-Time study loads.

**Program-Specific Risk:** Certain programs, such as the Bachelor of Economics, show compounded risks with a **33.3% fail rate** and **43.8% drop-out rate**, significantly higher than the university average of 8%.



### 🏫 For Unit Convenors: Gateway Unit Interventions

* **The "Gateway" Risk:** First-year foundation units are critical points of failure.
*Example:* **ACST1001 (Finance 1A)** consistently ranks in the top 5 for enrolment but records a **34.21% "exit-after-withdrawal" rate**, significantly higher than the faculty average of 21.31%.

**Performance Gaps:** Core units account for **82%** of High Distinctions, yet they also harbor the highest volume of failures (203 withdrawals in core units vs. 41 in flexible units in 2024).

**Actionable Thresholds:** Interventions must target specific high-risk units (e.g., STAT1250, MGMT1002) that collectively account for nearly **18%** of total withdrawals.



---

## 3. Predictive Analytics (Machine Learning)

To move from retrospective reporting to proactive prevention, the solution utilises a supervised **XGBoost classifier** to predict withdrawal risk.

**Model Accuracy:** Achieved **93.4% accuracy** and **98.2% recall** for withdrawn students.


* **Behavior Over Demographics:** The model confirms that risk is driven by *behavioral signals*, not demographics.
**Top Predictors:** Progression momentum (Level 300 unit completion), Success Rate per EFTSL, and WAM.
**Low Predictors:** Age, Gender, and Equity status.
**Risk Segmentation:** The 2025 cohort is segmented into Low (52.5%), Medium (7.8%), and High Risk (39.7%) groups to facilitate automated alerts.



---

## 4. Recommendations & Next Steps

1. **Consolidate Portfolio:** Review and consolidate the bottom 20 under-enrolled combined degrees to reduce administrative burden.


2. **Operationalize Early Alerts:** Deploy automated alerts for students flagged as "High Risk" (Low progression momentum) within 48 hours of enrolment or grade release.


3. **Embed Support:** Mandate Supplemental Instruction (SI) and formative checkpoints for high-risk gateway units (e.g., ACST1001) to prevent early exits.


4. **Mentoring for Momentum:** Implement structured mentoring for part-time students to prevent the "drift" that leads to transfers and drop-outs.



---

## 5. Technical Architecture

* **Data Warehouse:** Snowflake Schema (Star Schema) connecting Fact tables (Enrolment, Retention) with Dimension tables (Student, Course, Unit, WAM).


* **Visualization:** Power BI with five targeted dashboard pages (University Overview, Course Performance, Unit Performance, What-If Scenarios).


* 
**Design System:** Built using official institutional branding and accessible colour palettes for consistency.
