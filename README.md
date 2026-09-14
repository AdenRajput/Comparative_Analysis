# Architectural Selection Framework for Synthetic Network Traffic Generation

[![IEEE Access](https://img.shields.io/badge/IEEE%20Access-10.1109%2FACCESS.2025.3646769-blue.svg)](https://doi.org/10.1109/ACCESS.2025.3646769Download PDF)
[![Paper PDF](https://img.shields.io/badge/Paper-Open%20Access%20PDF-red.svg)](https://doi.org/10.1109/ACCESS.2025.3646769)
[![Git LFS](https://img.shields.io/badge/Data%20Storage-Git%20LFS-orange.svg)](https://git-lfs.github.com/)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

> 📄 **Official Implementation & Benchmark Repository**  
> This repository contains the source code, synthetic datasets, and evaluation pipelines supporting our published open-access research article in **IEEE Access**:
>
> **"Architectural Selection Framework for Synthetic Network Traffic: Quantifying the Fidelity–Utility Trade-off"**  
> *Dure Adan Ammara, Jianguo Ding, and Kurt Tutschku*  
> **DOI**: [10.1109/ACCESS.2025.3646769Download PDF](https://doi.org/10.1109/ACCESS.2025.3646769)[cite: 1] | **Volume 14, 2026** (pp. 468–485)

---

## Overview

Deploying synthetic tabular network traffic requires aligning the underlying generative architecture with the dataset's intrinsic structural properties. This framework evaluates generative performance across two heterogeneous benchmark domains:
- **NSL-KDD**: Categorical-heavy and discrete network telemetry.
- **CIC-IDS2017**: Continuous, highly skewed network flow metrics.

### Evaluation Criteria
* **Fidelity (Structural Realism)**: Screened using gatekeeper checks—specifically Data Structure (DS) consistency and empirical Correlation (Corr) deviation matrices to reject structurally non-compliant distributions.
* **Utility (Machine Learning Efficacy)**: Quantified using the Train on Synthetic, Test on Real (TSTR) protocol across standard downstream classifiers[cite: 1]. Performance is reported via Accuracy and Macro F1-score across $N = 20$ independent Monte Carlo executions ($\text{mean} \pm \text{std}$)[cite: 1].
* **Computational Complexity**: Assessed via training/sampling wall-clock latency, parameter stability, and convergence characteristics[cite: 1].

---

## Repository Structure

```text
Comparative_Analysis/
├── .gitattributes
├── README.md
│
├── CICIDS-17/
│   ├── imp_final_df_CICIDS17.zip          # Preprocessed baseline CIC-IDS2017 data
│   ├── T1_CICIDS17.ipynb                  # Tier 1 Generative Models (Baselines & Standard AI)
│   ├── T2_CICIDS17.ipynb                  # Tier 2 Generative Models (Specialized Deep Architectures)
│   ├── Eval_T1_CICIDS17.IPYNB             # TSTR and structural fidelity evaluation for T1
│   ├── Eval_T2_CICIDS17.IPYNB             # TSTR and structural fidelity evaluation for T2
│   └── Synthetic_Datasets/                # Generated data (Tracked via Git LFS)
│       ├── df_adasyn.csv
│       ├── df_cc.csv
│       ├── df_ctgan.csv
│       ├── df_gmm.csv
│       ├── df_ros.csv
│       ├── df_smote.csv
│       ├── df_tvae.csv
│       ├── data_castgan.csv
│       ├── data_copula_gan.csv
│       ├── data_ctgan_T2.csv
│       └── data_ganblrpp.csv
│
└── NSL-KDD/
    ├── NSL_KDD_Train.csv                  # Processed training partition
    ├── imp_final_df_NSLKDD.csv            # Feature-selected baseline data
    ├── T1_NSLKDD.ipynb                    # Tier 1 Generative Models (Baselines & Standard AI)
    ├── T2_NSLKDD.ipynb                    # Tier 2 Generative Models (Specialized Deep Architectures)
    ├── Eval_T1_NSLKDD.ipynb               # TSTR and structural fidelity evaluation for T1
    ├── Eval_T2_NSLKDD.IPYNB               # TSTR and structural fidelity evaluation for T2
    └── Synthetic_Datasets/                # Generated data (Tracked via Git LFS)
        ├── data_castgan.zip
        ├── data_copula_gan.csv
        ├── data_ctgan.csv
        ├── data_ganblrpp.csv
        ├── synthetic_df_adasyn.csv
        ├── synthetic_df_bn.csv
        ├── synthetic_df_cc.csv
        ├── synthetic_df_ctgan.csv
        ├── synthetic_df_gmm.zip
        ├── synthetic_df_ros.csv
        ├── synthetic_df_smote.csv
        └── synthetic_df_tvae.csv
