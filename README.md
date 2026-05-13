# Phytocure Open Research Dataset

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20143620.svg)](https://doi.org/10.5281/zenodo.20143620)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0005--8307--2353-green.svg)](https://orcid.org/0009-0005-8307-2353)
[![Dataset Version](https://img.shields.io/badge/Dataset-v1.0.0-blue.svg)](https://github.com/phytocure/research-data/releases)

> **Curator:** Conor William — ORCID: [0009-0005-8307-2353](https://orcid.org/0009-0005-8307-2353)
> **Platform:** [phytocure.xyz](https://phytocure.xyz) | **Protocol:** [phytocure/phytocure-protocol](https://github.com/phytocure/phytocure-protocol)

---

## Overview

This repository contains the open research datasets underpinning the Phytocure Protocol — a decentralized clinical cannabis medicine platform on Solana. All data is released under CC BY 4.0 for unrestricted academic and clinical use.

This dataset supports the manuscript:
> William, C. (2025). *Phytocure: A Decentralized Clinical Cannabis Medicine Protocol on the Solana Blockchain.* DOI: [10.5281/zenodo.20143620](https://doi.org/10.5281/zenodo.20143620). Under review at *Cannabis and Cannabinoid Research* (SAGE).

---

## Dataset Contents

| File | Records | Description |
|------|---------|-------------|
| [`data/cannabinoid-profiles.csv`](./data/cannabinoid-profiles.csv) | 120 | Verified cannabinoid content profiles by strain |
| [`data/strain-registry.csv`](./data/strain-registry.csv) | 85 | Strain registry with genetics, terpenes, and clinical notes |
| [`data/terpene-profiles.csv`](./data/terpene-profiles.csv) | 120 | Full terpene analysis per strain |
| [`data/clinical-references.csv`](./data/clinical-references.csv) | 200 | Curated clinical literature references |
| [`data/dosage-protocols.csv`](./data/dosage-protocols.csv) | 45 | Evidence-based dosage protocols by condition |
| [`methodology.md`](./methodology.md) | — | Data collection and verification methodology |

---

## Quick Start

```bash
# Clone the dataset
git clone https://github.com/phytocure/research-data.git
cd research-data

# Load in Python
import pandas as pd
profiles = pd.read_csv('data/cannabinoid-profiles.csv')
strains = pd.read_csv('data/strain-registry.csv')
print(profiles.head())
```

---

## Data Schema

### cannabinoid-profiles.csv
| Column | Type | Description |
|--------|------|-------------|
| `strain_id` | string | Unique strain identifier |
| `strain_name` | string | Common name |
| `thc_pct` | float | THC percentage (dry weight) |
| `cbd_pct` | float | CBD percentage |
| `cbg_pct` | float | CBG percentage |
| `cbc_pct` | float | CBC percentage |
| `cbn_pct` | float | CBN percentage |
| `thcv_pct` | float | THCV percentage |
| `thca_pct` | float | THCA percentage |
| `cbda_pct` | float | CBDA percentage |
| `lab_verified` | boolean | Third-party lab verified |
| `lab_id` | string | Certifying laboratory identifier |
| `analysis_date` | date | ISO 8601 date of analysis |

### strain-registry.csv
| Column | Type | Description |
|--------|------|-------------|
| `strain_id` | string | Unique strain identifier |
| `strain_name` | string | Common name |
| `chemotype` | string | Type I (THC), Type II (mixed), Type III (CBD) |
| `genetics` | string | Parent strains |
| `dominant_terpene` | string | Most prevalent terpene |
| `primary_indications` | string | Clinical indications (ICD-11 codes) |
| `entourage_score` | float | 0–10 synergy score |
| `therapeutic_score` | float | 0–100 overall therapeutic potential |
| `distributor_ids` | string | Phytocure distributor network IDs |

---

## Academic Use

If you use this dataset in your research, please cite:

```bibtex
@dataset{william2025phytocure,
  author       = {William, Conor},
  title        = {Phytocure Open Research Dataset},
  year         = 2025,
  publisher    = {GitHub},
  version      = {1.0.0},
  url          = {https://github.com/phytocure/research-data},
  doi          = {10.5281/zenodo.20143620},
  orcid        = {0009-0005-8307-2353}
}
```

---

## Contributing

Research contributions are welcomed under the Phytocure DAO research grant programme. See [`CONTRIBUTING.md`](./CONTRIBUTING.md) for submission guidelines.

All data contributions must:
- Include third-party laboratory verification
- Follow the schema defined in [`methodology.md`](./methodology.md)
- Be released under CC BY 4.0

---

## License

[![CC BY 4.0](https://i.creativecommons.org/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)

This dataset is licensed under [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).

---

*© 2025 Conor William. Phytocure Protocol — phytocure.xyz*
