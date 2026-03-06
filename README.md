# Artifact: Measuring Cybercriminal Operations from Victim Reports

This repository contains the **artifact and code implementation** accompanying the paper:

**“Measuring the Unobservable: Reconstructing Cybercriminal Operations from Victim Reports.”**

The artifact implements a framework for **inferring cybercriminal operational structure using victim-side complaint data**.

The system reconstructs attacker strategies indirectly by modeling cybercrime incidents as outcomes of a **latent adversarial process** observable through victim reports.

---

# 1. Artifact Overview

Cybercrime research often lacks direct visibility into attacker identities, infrastructure, or internal coordination mechanisms. This artifact provides a reproducible pipeline that reconstructs attacker operational patterns using only **victim-side observations**.

The framework extracts structured signals from complaint narratives and applies statistical and clustering methods to identify **recurring operational regimes of cybercriminal activity**.

The artifact supports the following **core claims of the paper**:

1. Cybercriminal operations exhibit **structured behavioral patterns** observable from victim reports.
2. Multi-dimensional capability modeling allows reconstruction of **latent attacker strategies**.
3. Cybercriminal activity organizes into **stable operational typologies** rather than isolated incidents.
4. The inferred typologies are **robust across clustering methods and statistical validation tests**.

---

# 2. Pipeline Architecture

The artifact implements a multi-stage analytical pipeline.

## Stage 1 — Data Standardization

Complaint narratives and structured metadata are normalized into a canonical format.

Key attributes include:

- financial loss
- fraud type
- interaction platform
- victim category
- geographic context
- narrative description

---

## Stage 2 — Platform Reconstruction

Many records lack explicit platform labels.

A reconstruction pipeline infers platforms using:

1. structured platform fields
2. regex extraction from narratives
3. heuristic inference from fraud modality

This produces full platform coverage while distinguishing **observed vs inferred platforms**.

---

## Stage 3 — Infrastructure Artefact Extraction

Operational artefacts are extracted from narratives using rule-based pattern matching.

Extracted artefacts include:

- phone numbers
- email identifiers
- payment identifiers
- domains and URLs
- application names
- messaging handles

These artefacts enable **infrastructure reuse analysis** across scam campaigns.

---

## Stage 4 — Behavioral Signal Extraction

The system detects **social engineering tactics** used by attackers.

Examples include:

- financial gain framing
- employment-based lures
- authority impersonation
- staged payments
- escalation tactics

These signals capture the **interactional dimension of cybercrime operations**.

---

## Stage 5 — Operational Clustering

Incidents are grouped into **operational contexts** based on stable contextual features.

Clusters represent **operational environments** rather than individual attackers.

This allows attacker behavior to be analyzed without requiring identity attribution.

---

## Stage 6 — Capability Modeling

Each cluster is represented as a capability vector capturing:

- financial efficiency
- platform specialization
- target selectivity
- geographic reach
- infrastructure reuse
- behavioral tactics

These dimensions approximate the **operational capabilities of cybercriminal groups**.

---

## Stage 7 — Typology Discovery

Clustering algorithms identify **recurring attacker typologies** within the capability space.

The paper identifies four primary operational regimes:

- wide-reach opportunistic campaigns
- high-yield targeted extraction
- platform-specialized operations
- infrastructure-coordinated campaigns

---

## Stage 8 — Strategy Landscape Analysis

Principal Component Analysis (PCA) visualizes the **strategic landscape of cybercriminal operations**.

Clusters occupy distinct regions corresponding to different operational strategies.

---

# 3. Validation and Robustness

The artifact includes extensive validation tests to ensure reliability.

## Extraction Reliability

Platform reconstruction achieves:
Precision = 1.00
Recall ≈ 0.91
F1 ≈ 0.95

This indicates highly reliable platform detection with minimal false positives.

---

## Behavioral Signal Validation

All tested behavioral detectors correctly identify their corresponding tactic patterns in controlled validation samples.

---

## Clustering Quality

Clustering structure is evaluated using standard metrics:
Silhouette Score ≈ 0.51
Davies–Bouldin Index ≈ 1.06
Calinski–Harabasz Score ≈ 70.6


These values indicate strong cluster separation in real-world data.

---

## Cross-Method Consistency

Clustering results remain stable across multiple algorithms.


Adjusted Rand Index (ARI)

GMM vs K-means ≈ 0.93
DP-GMM vs K-means ≈ 0.85


This confirms that the inferred typologies are **not artifacts of a specific clustering algorithm**.

---

## Bootstrap Stability

Cluster centroid stability under bootstrap resampling:


Mean coefficient of variation < 0.05


This indicates highly stable operational regimes.

---

## Measurement Validity

A **Convergent Validity Index (CVI) ≈ 0.52** confirms strong identifiability of latent attacker strategies.

---

## Permutation Tests

Permutation tests confirm that the clustering structure is **statistically significant and not due to random data arrangement**.

---

# 5. Reproducing the Experiments

Install dependencies:


pip install -r requirements.txt


Run the main notebook:


jupyter notebook notebooks/cybercrime_framework.ipynb


The notebook reproduces the complete pipeline, including:

- data preprocessing
- signal extraction
- clustering
- capability modeling
- validation experiments
- figure generation

---

# 6. Expected Outputs

Running the notebook will generate:

- operational typology visualizations
- infrastructure reuse networks
- strategy landscape projections
- validation statistics
- clustering robustness metrics

All figures used in the paper can be reproduced using the artifact.

---

# 7. Data Availability

The original dataset contains sensitive information and cannot be publicly released.

To support reproducibility, this repository includes:

- anonymized schema examples
- synthetic validation datasets
- complete analysis code

The artifact therefore enables **methodological reproduction without exposing sensitive data**.

---

# 8. Research Context

This artifact contributes to **computational criminology and cybercrime measurement** by demonstrating that attacker behavior can be reconstructed from victim-side observations under conditions of **partial adversarial observability**.

The approach shifts cybercrime analysis from **incident-centric descriptions** toward **structured measurement of offender strategies**.

---

# 9. Artifact Status

The artifact is intended to support the evaluation of:

- experimental reproducibility
- robustness of measurement methodology
- validity of inferred attacker typologies

The authors encourage artifact reviewers to execute the notebook and verify the reported results.

---

# 10. License

This artifact is released for **academic and research use**.

Please cite the associated paper if using this repository in academic work.
