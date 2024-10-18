# Synthetic Data Generation in Cybersecurity: A Comparative Analysis

## Project Overview
This project focuses on comparing prominent methods for generating synthetic tabular data, particularly in the context of cybersecurity network traffic data. It evaluates both statistical non-AI methods and AI-driven approaches, with a special emphasis on leading GAN models in this domain. The key evaluation metrics include:
- **Fidelity**: The statistical similarity between the synthetic and real data.
- **Utility**: The ability of the generated data to support machine learning tasks.
- **Class Balance**: The model’s capability to balance classes within the dataset.

## Scripting and Pacakges
This project was developed using **Python** with the following libraries:
- **Data Handling and Visualization**: `numpy`, `pandas`, `seaborn`, `matplotlib`
- **Machine Learning**: `torch`, `sklearn`, `imblearn`
- **Bayesian Networks**: `pgmpy`
- **Synthetic Data Generation**: `sdv`
- **Statistical Methods**: `scipy`

## Files and Dataset

### Dataset
The project used NSLKDD (Training .csv file) & CICIDS 2017 for generating and evaluating synthetic tabular data in the context of cybersecurity network traffic.


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
