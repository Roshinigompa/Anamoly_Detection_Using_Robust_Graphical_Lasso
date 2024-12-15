# Anamoly_Detection_Using_Robust_Graphical_Lasso

## Project Overview
This repository implements anomaly detection in high-dimensional datasets using **Robust Graphical Lasso (RGlasso)**. It extends the traditional Graphical Lasso by integrating **Robust Principal Component Analysis (RPCA)** for improved handling of outliers and sparse covariance estimation.

Key features:
- Combines RPCA and Graphical Lasso.
- Detects anomalies while preserving sparse structures.
- Optimized for both synthetic and real-world datasets.

## Motivation
Traditional methods like Graphical Lasso are sensitive to outliers, making them unsuitable for noisy data. RGlasso addresses this by:
- Decomposing covariance matrices into clean and sparse components.
- Handling noise effectively while maintaining computational efficiency.

Applications include:
- **Finance**: Improved risk management and hedging.
- **Healthcare**: Identifying rare complications in genomic or imaging data.
- **Cybersecurity**: Detecting network anomalies and cyber threats.

## Methodology
The RGlasso model is formulated as:
\[
\text{minimize}_{\Theta \succ 0, F \succ 0, S} \, - \log |\Theta| + \text{tr}(F\Theta) + \rho \|\Theta\|_1 + \lambda \|S\|_1 \quad \text{subject to } M = F + S
\]
Where:
- \( \Theta \): Precision matrix.
- \( F \): Clean covariance matrix.
- \( S \): Sparse anomalies matrix.
- \( M \): Observed covariance matrix.

Optimization is solved using **Alternating Direction Method of Multipliers (ADMM)**.

## Repository Structure
```
.
├── Anomaly_Detection_via_Graphical_Lasso.pdf   # Project report
├── Anamoly__detection_SD.ipynb                # Synthetic data analysis
├── Anamoly_Detection_RD_.ipynb                # Real-world data analysis
```

## Implementation Details
### Synthetic Data
- Generated using scikit-learn with injected anomalies.
- Standardized using `StandardScaler`.
- Matrices visualized with heatmaps and network graphs.
- Evaluated using precision, recall, and F1 scores.

### Real-World Data
- Utilized CICIDS2017 dataset.
- Preprocessing with scaling and feature selection (Random Forest).
- Handled missing/noisy data with enhanced robustness.
- Evaluated against methods like MCD and RPCA.



## Getting Started
1. Clone the repository:
   ```bash
   git clone https://github.com/Roshinigompa/Anamoly_Detection_Using_Robust_Graphical_Lasso.git
   ```

2. Run the notebooks:
   - Synthetic Data: `Anamoly__detection_SD.ipynb`
   - Real-World Data: `Anamoly_Detection_RD_.ipynb`

## Dependencies
- Python 3.8+
- Scikit-learn
- NumPy
- Matplotlib
- Pandas
- Jupyter Notebook
