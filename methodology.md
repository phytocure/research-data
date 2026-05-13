# Data Collection & Verification Methodology

**Version:** 1.0.0
**Author:** Conor William (ORCID: [0009-0005-8307-2353](https://orcid.org/0009-0005-8307-2353))
**Last Updated:** May 2025

---

## Overview

This document describes the standards and procedures used to collect, verify, and publish all data in the Phytocure Open Research Dataset. Adherence to these standards ensures data quality and reproducibility for clinical and academic users.

---

## 1. Cannabinoid Profile Data

### 1.1 Sources

Cannabinoid percentage data is sourced from:

1. **Third-party ISO/IEC 17025-accredited laboratories** — primary source
   - ACS Laboratory (Tampa, FL) — ISO/IEC 17025:2017 accredited
   - SC Labs (Santa Cruz, CA) — ISO/IEC 17025:2017 accredited
   - Steep Hill (Berkeley, CA) — ISO/IEC 17025 accredited
2. **Published peer-reviewed literature** — for clinically validated cultivars (Bedrocan series, Charlotte's Web, ACDC)
3. **Manufacturer certificates of analysis (CoAs)** — secondary verification only

### 1.2 Analytical Methods

All laboratories use validated methods consistent with the following standards:

| Analyte Class | Method | Standard |
|---------------|--------|----------|
| Cannabinoids | HPLC-UV or HPLC-DAD | AOAC 2018.11 |
| Cannabinoids (confirmation) | LC-MS/MS | USP <561> |
| Terpenes | GC-MS or GC-FID | AOAC 2018.11 |

### 1.3 Inclusion Criteria

A cannabinoid profile is included in the dataset if:

- Sample analysed by a qualified ISO/IEC 17025 laboratory
- Full panel of ≥8 cannabinoids reported (THC, THCA, CBD, CBDA, CBG, CBN, CBC, THCV minimum)
- Certificate of Analysis (CoA) available and linked to batch number
- Terpene panel reported (≥10 terpenes)

### 1.4 Exclusion Criteria

- Self-reported or unverified data
- Analyses >24 months old (degradation risk)
- Samples failing identity verification (macroscopic or microscopic)

### 1.5 Data Transformation

- Percentages expressed as dry-weight basis
- THCA and CBDA reported both as acids and converted totals:
  `Total THC = THCA × 0.877 + THC`
  `Total CBD = CBDA × 0.877 + CBD`
- Values rounded to two decimal places

---

## 2. Strain Registry Data

### 2.1 Genetic Information

Genetic lineage (parent strains) sourced from:
- Published breeders' documentation
- Seedfinder.eu database (cross-referenced)
- Peer-reviewed cannabis genetics literature

Unverifiable parentage is annotated as "unknown" or "undisclosed."

### 2.2 Clinical Indication Coding

All indications coded using **ICD-11** (International Classification of Diseases, 11th Revision):
- Chronic pain: G89
- Anxiety disorders: F41
- Sleep disorders: G47
- Epilepsy: G40
- Depression: F32
- PTSD: F43.1
- Nausea: R11

### 2.3 Therapeutic Score Calculation

Therapeutic Score (0–100) is calculated as a weighted composite:

```
Therapeutic Score = (
  0.40 × Clinical_Evidence_Score +   # RCT/review evidence for chemotype
  0.25 × Entourage_Score +           # Cannabinoid:terpene synergy
  0.20 × Safety_Score +              # Adverse event profile
  0.15 × Consistency_Score           # Lot-to-lot cannabinoid variance
)
```

**Clinical_Evidence_Score** is derived from GRADE evidence levels:
- Level A (RCT) = 90–100
- Level B (observational) = 60–89
- Level C (case series/expert) = 30–59

### 2.4 Psychoactivity Index

Psychoactivity Index (0–10) is calculated from:

```
Psychoactivity Index = (Total_THC × 0.6) + (THCV × 0.3) + (CBD × -0.1)
```
Capped at 10. CBD has a modest antagonistic effect on THC-mediated psychoactivity.

---

## 3. Clinical References

### 3.1 Search Strategy

Literature searches conducted in:
- PubMed/MEDLINE
- Embase
- Cochrane Library
- ClinicalTrials.gov (for ongoing trials)

**Search terms:** cannabis, cannabidiol, THC, phytocannabinoid, endocannabinoid, combined with condition-specific MeSH terms.

**Date range:** 1990–2025 (systematic reviews), 2000–2025 (primary studies)

### 3.2 Inclusion Criteria

- Human studies (in vivo preclinical for mechanistic papers)
- Published in peer-reviewed journals
- Sample size ≥ 10 (for clinical studies)
- Full-text accessible for verification
- DOI or PMID available

### 3.3 Evidence Grading

Evidence graded using the Oxford Centre for Evidence-Based Medicine (OCEBM) levels:

| Grade | Study Type |
|-------|-----------|
| Ia | Systematic review of RCTs |
| Ib | Individual RCT |
| IIa | Systematic review of cohort studies |
| IIb | Individual cohort study |
| III | Case-control or cross-sectional |
| IV | Case series or expert opinion |

---

## 4. Dosage Protocol Data

### 4.1 Sources

Dosage protocols synthesised from:
- Approved product monographs (Sativex, Epidyolex, Dronabinol)
- Published clinical practice guidelines
- Expert consensus statements from:
  - International Association for Cannabinoid Medicines (IACM)
  - Australian TGA cannabis prescribing guidelines
  - Health Canada cannabis clinical guidance

### 4.2 Dose Nomenclature

| Abbreviation | Meaning |
|--------------|---------|
| QD | Once daily |
| BID | Twice daily |
| TID | Three times daily |
| QID | Four times daily |
| PRN | As needed |

### 4.3 Limitations

- Dosage protocols represent evidence-informed guidance, not medical advice
- Individual patient factors (weight, metabolism, tolerance, genetics) significantly affect optimal dosing
- All clinical use requires supervision by a qualified healthcare practitioner
- Protocols should be reviewed against current national guidelines for the relevant jurisdiction

---

## 5. Data Governance

### 5.1 Version Control

- All datasets are version-controlled in this GitHub repository
- Major version increments (1.x → 2.x) indicate schema changes
- Minor versions (1.0.x → 1.1.x) indicate data additions
- Patch versions (1.0.0 → 1.0.1) indicate corrections

### 5.2 Corrections Policy

Errors should be reported via GitHub Issues. All corrections are:
- Documented in the CHANGELOG
- Attributed to the reporting contributor
- Applied within 14 days of verification

### 5.3 Data Attribution

All contributors are attributed in the CHANGELOG with their ORCID ID where provided.
Contributors retain no intellectual property rights over contributions (CC BY 4.0 applies).

---

## 6. Ethics

This dataset contains no patient-identifiable information. All clinical outcome data referenced in therapeutic scores is drawn from published, anonymised literature. No human subjects research was conducted in compiling this dataset.

---

*© 2025 Conor William. CC BY 4.0. phytocure.xyz*
