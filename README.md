# Architectural Selection Framework for Synthetic Network Traffic Generation
### A Statistically Validated Guide to Architectural Selection in Cybersecurity
This repository contains the full source code and analysis supporting the paper: "Architectural Selection Framework for Synthetic Network Traffic Generation: An Empirical Comparative Study."
## Project Overview
This project systematically validates the claim that optimal synthetic data generation hinges on architectural compatibility with data structure, moving beyond simple performance comparisons. The final code includes the rigorous statistical validation required for the analysis. The key evaluation criteria, forming the basis of our Architectural Selection Framework, include:
- **Fidelity (Structural Realism)**: Assessed using Gatekeeper Metrics, specifically, the Data Structure (DS) and Correlation (Corr) checks, to disqualify structurally compromised synthetic data.
- **Utility (ML Efficacy)**: Quantified by TSTR Accuracy and F1-Score (mean $\pm$ standard deviation) across 20 independent runs.
- **Scalability**: Measured via computational cost and architectural failure rates (e.g., for Diffusion Models).

## Rigor and Reproducibility:
To account for model stochasticity, all TSTR (Train on Synthetic, Test on Real) Accuracy and F1-Scores are reported as the mean ($\bar{x}$) and standard deviation ($\sigma$) across 20 independent executions ($N=20$), supporting the statistical rigor outlined in Section IV of the paper.

## Scripting and Pacakges
This project was developed using **Python** with the following libraries:
- **Data Handling and Visualization**: `numpy`, `pandas`, `seaborn`, `matplotlib`
- **Machine Learning/Statistics**: `torch`, `sklearn`, `imblearn`, `scipy` (for statistical testing)
- **Bayesian Networks**: `pgmpy`
- **Synthetic Data Generation**: `sdv` (for CTGAN, CopulaGAN, TVAE)

## Files and Dataset

### Dataset
The analysis utilizes two heterogeneous network traffic datasets: NSL-KDD (categorical-heavy) and CIC-IDS2017 (continuous flow-heavy).

### File Descriptions
Below is a summary of the key files in both of the sub-repositories (i.e., NSL-KDD, CICIDS-17) and their purposes:

- **`T1_NSLKDD.ipynb`**: This script handls the synthetic data genration of the standard & AI models for NSLKDD dataset.
  
- **T1_CICIDS17.ipynb`**: This script handls the synthetic data genration of the standard & AI models for CICIDS 2017 dataset.
  
- **`T2_NSLKDD.ipynb`**: This script handls the synthetic data genration of the prominent GAN models for NSLKDD dataset.

- **T1_CICIDS17.ipynb`**: This script handls the synthetic data genration of the prominent GAN models for CICIDS 2017 dataset.
  
- **`Eval_T1_NSLKDD.IPYNB`**: Contains evalaution of the T1 file for NSLKDD dataset.
  
- **`Eval_T2_NSLKDD.IPYNB`**: Contains evalaution of the T2 file for NSLKDD dataset.

- **`Eval_T1_CICIDS17.IPYNB`**: Contains evalaution of the T1 file for CICIDS 2017 dataset.

- **`Eval_T1_CICIDS17.IPYNB`**: Contains evalaution of the T2 file for CICIDS 2017 dataset.

## Contact
For questions, feedback, or collaboration opportunities, feel free to reach out via:
- **Email**: [daf@bth.se](mailto:daf@bth.se)
- **Twitter/X**: [@Aden_Rajput_](https://x.com/Aden_Rajput_)
- **LinkedIn**: [Aden Rajput](https://www.linkedin.com/in/adenrajput/)
