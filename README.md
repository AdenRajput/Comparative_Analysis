```markdown
# Architectural Selection Framework for Synthetic Network Traffic Generation

[![IEEE Access](https://img.shields.io/badge/IEEE%20Access-10.1109%2FACCESS.2025.3646769-blue.svg)](https://doi.org/10.1109/ACCESS.2025.3646769)
[![Paper PDF](https://img.shields.io/badge/Paper-Open%20Access%20PDF-red.svg)](https://doi.org/10.1109/ACCESS.2025.3646769)
[![Git LFS](https://img.shields.io/badge/Data%20Storage-Git%20LFS-orange.svg)](https://git-lfs.github.com/)

> 📄 **Official Implementation & Benchmark Repository**  
> This repository contains the source code, synthetic datasets, and evaluation pipelines supporting our published open-access research article in **IEEE Access**:  
> **"Architectural Selection Framework for Synthetic Network Traffic: Quantifying the Fidelity–Utility Trade-off"**  
>  
> *Dure Adan Ammara, Jianguo Ding, and Kurt Tutschku*  
> **DOI:** [10.1109/ACCESS.2025.3646769](https://doi.org/10.1109/ACCESS.2025.3646769) | **Volume 14, 2026 (pp. 468–485)**  
> [Download PDF](https://doi.org/10.1109/ACCESS.2025.3646769)

---

## Overview

Deploying synthetic tabular network traffic requires aligning the underlying generative architecture with the dataset's intrinsic structural properties. This framework evaluates generative performance across two heterogeneous benchmark domains:

* **NSL-KDD:** Categorical-heavy and discrete network telemetry.
* **CIC-IDS2017:** Continuous, highly skewed network flow metrics.

### Evaluation Criteria

* **Fidelity (Structural Realism):** Screened using gatekeeper checks—specifically Data Structure (DS) consistency and empirical Correlation (Corr) deviation matrices to reject structurally non-compliant distributions.
* **Utility (Machine Learning Efficacy):** Quantified using the Train on Synthetic, Test on Real (TSTR) protocol across standard downstream classifiers. Performance is reported via Accuracy and Macro F1-score across $N = 20$ independent Monte Carlo executions ($\text{mean} \pm \text{std}$).
* **Computational Complexity:** Assessed via training/sampling wall-clock latency, parameter stability, and convergence characteristics.

---

## Repository Structure

```plaintext
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

```

---

## Environment & Dependencies

### Prerequisites

* Python 3.8+
* Git LFS (Mandatory to download large CSV datasets)

### Installation

```bash
git lfs install
git clone [https://github.com/AdenRajput/Comparative_Analysis.git](https://github.com/AdenRajput/Comparative_Analysis.git)
cd Comparative_Analysis
git lfs pull

```

### Required Packages

```bash
pip install numpy pandas scipy scikit-learn imbalanced-learn torch pgmpy sdv matplotlib seaborn

```

---

## Reproduction Workflow

* **Preprocessed Feature Bases:**
* **NSL-KDD:** Baseline features are available in `NSL-KDD/imp_final_df_NSLKDD.csv`.
* **CIC-IDS2017:** Unzip `imp_final_df_CICIDS17.zip` into the `CICIDS-17/` directory before running downstream experiments.


* **Synthetic Data Synthesis:**
* Run `T1_<DATASET>.ipynb` for baseline resampling methods (SMOTE, ADASYN, ROS, Cluster Centroids) and standard generative models (GMM, CTGAN, TVAE).
* Run `T2_<DATASET>.ipynb` for specialized tabular networks (CopulaGAN, CastGAN, GANBLR-PP).


* **Benchmarking & Evaluation:**
* Run `Eval_T1_<DATASET>.ipynb` and `Eval_T2_<DATASET>.ipynb` to execute gatekeeper structural tests and downstream 20-run Monte Carlo TSTR evaluations.



---

## Citation

If you find this framework, datasets, or methodology useful in your research, please cite our paper:

```bibtex
@article{ammara2026architectural,
  author={Ammara, Dure Adan and Ding, Jianguo and Tutschku, Kurt},
  journal={IEEE Access}, 
  title={Architectural Selection Framework for Synthetic Network Traffic: Quantifying the Fidelity-Utility Trade-off}, 
  year={2026},
  volume={14},
  pages={468-485},
  doi={10.1109/ACCESS.2025.3646769},
  publisher={IEEE}
}

```

---

## Contact & Acknowledgements

This work was supported by the European Celtic+ and Swedish Vinnova Project through CISSAN (*Collective Intelligence Supported by Security Aware Nodes*) under Grant C2022/1-3.

* **Dure Adan Ammara** — [daf@bth.se](https://www.google.com/search?q=mailto%3Adaf%40bth.se)
* **Jianguo Ding** (*Corresponding Author*) — [jianguo.ding@bth.se](https://www.google.com/search?q=mailto%3Ajianguo.ding%40bth.se)
* **Institution:** Blekinge Institute of Technology (BTH), 37179 Karlskrona, Sweden
* **Profiles:** [LinkedIn](https://www.linkedin.com) | [GitHub](https://github.com/AdenRajput)

```

To update the repository:
1. Paste this into `README.md` and save (`Ctrl + S`).
2. Run in terminal:
```bash
git commit -am "Update full academic README with paper and workflow"
git push origin main

```
