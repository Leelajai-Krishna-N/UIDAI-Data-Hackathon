# Aadhaar Temporal Echo Analysis  
### Cohort-Based Detection of Lifecycle-Driven Update Demand

## Overview
Aadhaar is often treated as a one-time identity enrolment system. In practice, it functions as a **long-term digital identity infrastructure**, where enrolment at early life stages generates **delayed biometric and demographic update demand** over time.

This project introduces the concept of **Temporal Echoes** in Aadhaar data—delayed effects where earlier enrolment activity manifests as future update pressure. Due to the absence of publicly available multi-year district-level data, we adopt a **cohort-based temporal proxy approach**, using spatial variation across districts to approximate different lifecycle stages within a single-year snapshot.

The analysis uncovers clear, lifecycle-driven patterns in Aadhaar update behaviour and proposes a **Lifecycle-Aware Capacity Planning Framework** to support informed administrative decision-making.

---

## Key Idea: Temporal Echo
**Temporal Echo** refers to a delayed relationship where Aadhaar enrolment activity in earlier life stages leads to increased biometric or demographic update demand in later stages.

Instead of relying on long historical time series, this project leverages **district-level lifecycle composition** (child-heavy vs adult-heavy districts) as a proxy for temporal progression.

---

## Datasets Used
All datasets are aggregated and anonymised, sourced from UIDAI via data.gov.in:

1. **Aadhaar Enrolment Dataset**
   - Age groups: 0–5, 5–17, 18+
   - Granularity: District–month

2. **Aadhaar Demographic Update Dataset**
   - Age groups: 5–17, 17+
   - Granularity: District–month

3. **Aadhaar Biometric Update Dataset**
   - Age groups: 5–17, 17+
   - Granularity: District–month

---

## Methodology

### 1. Data Preparation
- Standardised column names across datasets
- Aggregated all data to **district–month level**
- Aligned enrolment and update datasets using geographic and temporal keys

### 2. Lifecycle Cohort Construction
Districts were classified into three lifecycle cohorts based on the share of child enrolments (age 5–17):

- **Early-stage**: Child-heavy districts  
- **Mid-stage**: Balanced lifecycle composition  
- **Late-stage**: Adult/update-heavy districts  

These cohorts act as **implicit temporal stages** of the Aadhaar lifecycle.

### 3. Echo Intensity Metrics
Three indicators were defined to quantify delayed update demand:

- **Biometric Echo Intensity (BEI)**  
  Ratio of adult biometric updates to child enrolments

- **Demographic Echo Intensity (DEI)**  
  Ratio of adult demographic updates to child enrolments

- **Combined Echo Pressure Index (CEPI)**  
  Overall Aadhaar system pressure relative to total enrolment base

### 4. Validation
Cohort-wise comparisons were used to test whether echo intensity increases systematically from Early-stage to Late-stage districts.

---

## Key Findings

- **Strong Temporal Echo Detected**  
  Both BEI and DEI increase monotonically across lifecycle cohorts, validating delayed demand effects.

- **Biometric Updates Are the Primary Stressor**  
  Biometric echo intensity grows significantly faster than demographic echo intensity.

- **Stable Overall Load, Changing Composition**  
  While total system pressure remains relatively stable, demand shifts from enrolment to updates as lifecycle maturity increases.

- **Spatial Variation Enables Predictive Insight**  
  Even with single-year data, cohort-based analysis provides forward-looking intelligence.

---

## Solution Framework: Lifecycle-Aware Aadhaar Planning

Based on the findings, the project proposes:
- Lifecycle-aware allocation of biometric infrastructure
- Early identification of future demand zones using child-heavy districts
- Composition-based service planning instead of volume-based scaling
- Cohort-based monitoring dashboards for proactive decision-making

---

## Impact & Applicability
- Supports **evidence-based capacity planning**
- Reduces reactive overload management
- Improves citizen experience by anticipating update demand
- Scalable across states and districts
- Applicable to other Digital Public Infrastructure (DPI) systems

---

## Tools & Technologies
- Python
- Pandas
- Matplotlib
- Jupyter Notebook

---

## Project Status
✔ Data cleaning and harmonisation  
✔ Cohort-based temporal analysis  
✔ Echo validation and visualisation  
✔ Policy-ready insights and recommendations  

---

## Authors
Hackathon Submission Team  
1.Leelajai Krishna N
2.Adithya D J
3.Dishanth P I
4.Pranav L P

---

## Disclaimer
This project uses aggregated, anonymised public datasets and does not involve any personal or identifiable information. All interpretations are analytical and intended to support policy and system improvement discussions.

