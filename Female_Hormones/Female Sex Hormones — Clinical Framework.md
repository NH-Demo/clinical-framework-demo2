# Female Sex Hormones — Clinical Framework

**Document Version:** 1.0.0-DRAFT  
**Status:** In Review  
**Target Panel:** SANGRA Extended Panel[cite: 1]  
**Lead Authors:** Clinical Working Group  

---

## Table of Contents
1. [Purpose & Scope](#1-purpose--scope)
2. [Reference: Risk Types and Labels](#2-reference-risk-types-and-labels)
3. [Reference: GP Communication Tiers (T0-T5)](#3-reference-gp-communication-tiers-t0-t5)
4. [FSH (Follicle Stimulating Hormone)](#4-fsh-follicle-stimulating-hormone)
5. [LH (Luteinising Hormone)](#5-lh-luteinising-hormone)
6. [LH:FSH Ratio](#6-lhfsh-ratio)
7. [Oestradiol (E2)](#7-oestradiol-e2)
8. [Progesterone](#8-progesterone)
9. [Testosterone (Female)](#9-testosterone-female)
10. [SHBG (Sex Hormone Binding Globulin, Female)](#10-shbg-sex-hormone-binding-globulin-female)
11. [DHEAS](#11-dheas)
12. [Prolactin](#12-prolactin)
13. [Document Control](#13-document-control)
14. [Appendix: Menstrual Cycle Phase Mapping](#appendix-menstrual-cycle-phase-mapping)

---

## 1. Purpose & Scope

This clinical framework governs the evaluation, interpretation, and automated triaging of female sex hormones within the diagnostic panels. The scope encompasses:

* Standardized adult female biological reference intervals across standard cycle phases (Follicular, Ovulatory, Luteal, Postmenopausal)[cite: 1].
* Triage escalation paths mapped to clear GP communication urgency levels (T0 through T5).
* Algorithmic interpretation rules combining biochemical values with participant demographic inputs (age, cycle day, exogenous hormone use).

---

## 2. Reference: Risk Types and Labels

To support programmatic triage and user interface displays, every reported biomarker value evaluates to one of the following canonical risk definitions:

| Risk Code | Display Label | Definition | Action Trigger |
| :--- | :--- | :--- | :--- |
| **R0** | Optimal | Within physiological reference limits for stated phase[cite: 1]. | Informative only; routine maintenance. |
| **R1** | Borderline | Minor variance; within 10% of lower or upper bounds. | Retest in 3 to 6 months if symptomatic. |
| **R2** | Moderate Risk | Out-of-range value suggestive of endocrine dysregulation. | Secondary review; lifestyle and primary care follow-up. |
| **R3** | High Risk | Significant abnormality indicating potential pathology. | Physician consultation recommended within 14 days. |
| **R4** | Critical | Acute or extreme endocrine derangement. | Urgent communication (T4/T5 escalation). |

---

## 3. Reference: GP Communication Tiers (T0-T5)

Automated notifications and provider communications follow standard clinical escalation tiers:

* **T0 (No Action Required):** Findings are fully within anticipated baseline parameters[cite: 1]. No outbound GP letter generated.
* **T1 (Routine Communication):** Mild incidental variations. Summary report made available to the member for routine primary care sharing.
* **T2 (GP Advisory):** Findings warrant evaluation (e.g., persistent anovulatory cycles, suspected PCOS). Standard letter dispatched to the registered GP within 5 business days.
* **T3 (Priority GP Review):** Markedly deranged profiles (e.g., severe hypogonadotropic hypogonadism, unexpected postmenopausal bleeding markers). Letter delivered within 48 hours.
* **T4 (Urgent Direct Contact):** Highly abnormal result requiring clinical verification within 24 hours. Clinical operations outreach initiated.
* **T5 (Emergency Clinical Action):** Critical physiological threat requiring same-day physician contact and immediate escalation protocol.

---

## 4. FSH (Follicle Stimulating Hormone)

### 4.1 Biomarker Overview
Glycoprotein hormone synthesized and secreted by the anterior pituitary gland. Regulates the development, growth, pubertal maturation, and reproductive processes of the body.

### 4.2 Reference Intervals (IU/L)

| Cohort / Cycle Phase | Reference Lower | Reference Upper | Flagging Rule |
| :--- | :--- | :--- | :--- |
| Follicular Phase | 3.5 | 12.5 | Flag R2 if > 18.0 |
| Ovulatory Peak | 4.7 | 21.5 | Physiological spike expected |
| Luteal Phase | 1.7 | 7.7 | Flag R1 if > 10.0 |
| Postmenopausal | 25.8 | 134.8 | Flag R2 if < 20.0 (unconfirmed) |

### 4.3 Escalation Pathway
* If FSH > 30 IU/L in individuals under 40 years of age with amenorrhea > 3 months: **Escalate to T3 (Primary Ovarian Insufficiency pathway)**.
* If FSH < 1.0 IU/L accompanied by low LH and low Estradiol: **Assign T2 (Hypothalamic/Pituitary suppression check)**.

---

## 5. LH (Luteinising Hormone)

### 5.1 Biomarker Overview
Synthesized by gonadotropic cells in the anterior pituitary. Triggers ovulation and development of the corpus luteum.

### 5.2 Reference Intervals (IU/L)

| Cohort / Cycle Phase | Reference Lower | Reference Upper | Flagging Rule |
| :--- | :--- | :--- | :--- |
| Follicular Phase | 2.4 | 12.6 | Flag R1 if > 13.0 |
| Mid-Cycle Surge | 14.0 | 95.6 | Contextualized against Day 12-16 |
| Luteal Phase | 1.0 | 11.4 | Baseline suppressive window |
| Postmenopausal | 7.7 | 58.5 | Normal elevated post-cessation |

### 5.3 Escalation Pathway
* Isolated mid-cycle surge elevation: **T0 (Physiological)**.
* Persistent follicular LH elevation with irregular cycles: Trigger algorithmic evaluation for **LH:FSH Ratio (Section 6)**.

---

## 6. LH:FSH Ratio

### 6.1 Clinical Utility
Calculated derived ratio assessed exclusively in the early follicular phase (Day 2 to Day 5 of the menstrual cycle). Utilized as a supporting diagnostic marker for Polycystic Ovary Syndrome (PCOS).

### 6.2 Ratio Interpretation Matrix

| Calculated Ratio | Clinical Interpretation | Action Tier |
| :--- | :--- | :--- |
| **< 1.5** | Normal physiological baseline | T0 |
| **1.5 – 2.0** | Equivocal / Mildly elevated | T1 |
| **> 2.0** | Strongly suggestive of PCOS pattern when accompanied by hyperandrogenism | T2 |
| **> 3.0** | Marked gonadotropin dysregulation | T2 (Recommend pelvic ultrasonography) |

---

## 7. Oestradiol (E2)

### 7.1 Biomarker Overview
Primary bioactive estrogen produced primarily by the granulosa cells of the ovarian follicles and the corpus luteum.

### 7.2 Reference Intervals (pmol/L)

| Phase | Minimum | Maximum | Triage Trigger |
| :--- | :--- | :--- | :--- |
| Early Follicular | 45.4 | 854.0 | R1 if < 45.0 |
| Pre-Ovulatory Peak | 151.0 | 1461.0 | Expected surge |
| Luteal | 82.0 | 1251.0 | R1 if < 80.0 |
| Postmenopausal | < 37.0 | 103.0 | R3 if > 150.0 (Unscheduled bleeding risk) |

### 7.3 Escalation Pathway
* Postmenopausal participant not on Hormone Replacement Therapy (HRT) presenting with E2 > 150 pmol/L: **Assign T3 priority review**.

---

## 8. Progesterone

### 8.1 Biomarker Overview
Steroid hormone produced by the corpus luteum following ovulation. Key marker for confirming ovulatory function and luteal phase sufficiency.

### 8.2 Reference Intervals (nmol/L)

| Phase | Target Range | Interpretation |
| :--- | :--- | :--- |
| Follicular | < 0.6 – 4.7 | Baseline |
| Mid-Luteal (Day 21 / 7 days pre-menses) | 16.0 – 60.0 | Confirms ovulation (> 30 nmol/L optimal) |
| Postmenopausal | < 0.6 – 2.0 | Physiological suppression |

### 8.3 Algorithmic Rules
* If mid-luteal progesterone is < 15.0 nmol/L in a cycle where ovulation was suspected: **Flag R2 (Anovulatory or luteal phase defect pattern)**.
* Elevated progesterone without pregnancy context: Re-verify assay bounds against analytical measuring intervals.

---

## 9. Testosterone (Female)

### 9.1 Biomarker Overview
Circulates primarily bound to SHBG and albumin. Used in evaluating hyperandrogenism, hirsutism, alopecia, and virilizing pathologies.

### 9.2 Reference Intervals (nmol/L)

| Age Cohort | Normal Range | Elevated (R2) | Severe Elevation (R3/R4) |
| :--- | :--- | :--- | :--- |
| Premenopausal (18–49) | 0.29 – 1.67 | 1.68 – 3.50 | > 3.50 nmol/L |
| Postmenopausal (50+) | 0.10 – 1.42 | 1.43 – 2.50 | > 2.50 nmol/L |

### 9.3 Escalation Pathway
* Total Testosterone > 5.0 nmol/L: **Trigger T3 review (rule out androgen-secreting ovarian or adrenal neoplasms)**.

---

## 10. SHBG (Sex Hormone Binding Globulin, Female)

### 10.1 Biomarker Overview
High-affinity binding protein synthesized by the liver. Regulates bioavailable fractions of circulating androgens and estrogens.

### 10.2 Reference Intervals (nmol/L)

| Cohort | Lower Limit | Upper Limit | Clinical Note |
| :--- | :--- | :--- | :--- |
| Non-pregnant Adults | 32.4 | 128.0 | Low levels indicate insulin resistance/PCOS |

### 10.3 Free Androgen Index (FAI) Derivation
$$\text{FAI} = \left( \frac{\text{Total Testosterone (nmol/L)}}{\text{SHBG (nmol/L)}} \right) \times 100$$

* Normal: < 4.5%
* Elevated: > 7.0% (Strong indication of functional hyperandrogenism)

---

## 11. DHEAS

### 11.1 Biomarker Overview
Dehydroepiandrosterone sulfate is a circulating steroid prohormone primarily produced by the adrenal cortex (zona reticularis).

### 11.2 Age-Adjusted Reference Intervals ($\mu\text{mol/L}$)

| Age Range | Minimum | Maximum | Flagging Threshold |
| :--- | :--- | :--- | :--- |
| 18 – 29 years | 2.68 | 9.23 | High: > 10.5 |
| 30 – 39 years | 1.82 | 7.50 | High: > 8.5 |
| 40 – 49 years | 1.30 | 5.80 | High: > 6.5 |
| 50 – 59 years | 0.90 | 4.10 | High: > 5.0 |

### 11.3 Escalation Pathway
* Marked elevation (> 2x upper limit of age normal): **Assign T3 (Adrenal screening workup required)**.

---

## 12. Prolactin

### 12.1 Biomarker Overview
Secreted by lactotroph cells in the anterior pituitary. Critical for identifying hyperprolactinemia, galactorrhea, pituitary adenomas, or medication side effects.

### 12.2 Reference Intervals (mIU/L)

| Patient Cohort | Lower Bound | Upper Bound | Diagnostic Interpretation |
| :--- | :--- | :--- | :--- |
| Non-pregnant Adult Female | 102 | 496 | Normal physiological window |
| Mild Hyperprolactinemia | 500 | 1000 | Stress, venipuncture artifact, subclinical |
| Significant Elevation | 1000 | 2500 | Pharmacological review or microadenoma |
| Marked Elevation | > 2500 | — | Macroprolactinoma investigation |

### 12.3 Escalation Pathway
* Prolactin > 1500 mIU/L without known pharmacological etiology: **Escalate to T3 / Direct Clinical Notification**.

---

## 13. Document Control

| Version | Date | Section Revised | Summary of Change | Approved By |
| :--- | :--- | :--- | :--- | :--- |
| **0.1.0** | 2026-06-15 | All | Initial structural draft created. | Clinical Lead |
| **0.2.0** | 2026-07-20 | §4, §5, §7 | Cycle phase boundary standardization. | Working Group |
| **1.0.0** | 2026-10-05 | All | Baseline framework ratified for pilot. | Medical Director |

---

## Appendix: Menstrual Cycle Phase Mapping

When assigning risk ranges dynamically, user-reported menstrual history must map onto standard physiological windows:

1. **Early Follicular:** Days 1 through 5 of regular bleeding.
2. **Mid-Late Follicular:** Days 6 through 11.
3. **Periovulatory:** Days 12 through 16 (or LH surge detection date).
4. **Luteal Phase:** Days 17 through cycle end (typically Day 28).
5. **Postmenopausal:** $\ge 12$ consecutive months of spontaneous amenorrhea in individuals over age 45 without alternative pathological or physiological cause.
