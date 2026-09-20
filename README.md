# Robotic Fault Diagnosis System (1D-CAE + 1D-CNN)

This repository contains the implementation of a two-stage hybrid robotic fault diagnosis framework using 9-channel IMU telemetry. The architecture combines an unsupervised 1D Convolutional Autoencoder (1D-CAE) for real-time anomaly screening with a supervised 1D Convolutional Neural Network (1D-CNN) for multi-class fault classification.

---

## epository Structure & Files

- **`Robotarm.ipynb`**: The primary Jupyter Notebook containing the complete source code, including telemetry data preprocessing, signal filtering, model architecture definition (Stage 1 CAE & Stage 2 CNN), training pipelines, and evaluation metrics.
- **`Data_Robotarm/`**: Directory containing the raw and preprocessed 9-channel IMU telemetry datasets used for training and evaluating the models.

---

## Getting Started

### 1. Download the Data
➡️ **[Download Dataset from Kaggle]([https://www.kaggle.com/datasets/YOUR-KAGGLE-USERNAME/YOUR-DATASET-NAME](https://www.kaggle.com/datasets/hkayan/industrial-robotic-arm-anomaly-detection/code))**

### 2. Run the Notebook
Open `Robotarm.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab to execute the diagnostic pipeline step-by-step:

1. **Preprocessing & Filtering:** Signal conditioning using a Median Moving Filter and Z-score scaling (`StandardScaler`).
2. **Stage 1 (1D-CAE):** Unsupervised baseline profiling on healthy 10 Hz telemetry and dynamic thresholding ($\tau$).
3. **Stage 2 (1D-CNN):** Multi-class fault classification ($y \in \{0..4\}$) triggered upon threshold breach ($\text{MSE} > \tau$).

---

##  Requirements

To run `Robotarm.ipynb`, install the required Python packages:

```bash
pip install numpy pandas matplotlib scikit-learn tensorflow
