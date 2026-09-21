# 🛠️ AI-Powered Predictive Maintenance & Multi-Fault Diagnosis
> **NASA Intelligent Maintenance Systems (IMS) Bearing Dataset Analysis**

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.3%2B-orange)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-red)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📌 Project Overview
Unplanned machinery breakdowns cause billions in industrial downtime. This project implements an end-to-end Machine Learning and Deep Learning pipeline for **Predictive Maintenance (PdM)** and **Prognostics and Health Management (PHM)** using real-world high-frequency sensor recordings from the NASA IMS Bearing Dataset.

The pipeline processes continuous vibration signals to:
1. **Classify Health States**: Identify baseline normal operation, warning stages, and failure conditions with **99.7% Accuracy**.
2. **Diagnose Multi-Fault Types**: Distinguish between **Outer Race Faults**, **Inner Race Faults**, and **Roller Element Faults**.
3. **Sequence-Based LSTM Degradation Dashboard**: Predict real-time Fault Severity ($0\% \rightarrow 100\%$) with automated 80% Early Warning Alerts and 100% Emergency Shutdown Callouts.

---

## 📂 Repository Structure
```text
├── data/                        # Extracted dataset subfolders
├── bearing_features.csv         # Processed features for Test Set 2 (Outer Race Fault)
├── test1_features.csv           # Processed features for Test Set 1 (Inner Race & Roller Faults)
├── new2.ipynb                   # Main Jupyter Notebook (Complete Analysis & Models)
├── README.md                    # Project Documentation
└── .gitignore                   # Excludes heavy raw archives (.7z, .rar)
```

---

## 🔬 Dataset Overview
The dataset contains accelerometer recordings from bearings operating under constant speed (2000 RPM) and radial load (6000 lbs) sampled at **20.48 kHz**:
- **Test Set 2**: Single bearing outer race failure across 984 1-second snapshots.
- **Test Set 1**: Dual failure (Bearing 3 Inner Race Fault & Bearing 4 Roller Element Fault) across 2,156 1-second snapshots over 35 days.

---

## 📊 Feature Engineering & Domain Metrics
From 20,480 raw data points per snapshot, the following physics-based features were derived:
- **RMS (Root Mean Square)**: Measures overall vibration energy and power.
- **Peak-to-Peak (P2P)**: Measures maximum physical shock impact stroke.
- **Kurtosis**: Detects impulsive spikiness caused by early micro-cracks.

---

## 🏆 Model Benchmarks & Results

| Dataset | Failure Type | Model Architecture | Accuracy / F1-Score |
| :--- | :--- | :--- | :---: |
| **Test Set 2** | Outer Race Fault | Random Forest Classifier | **100.0%** |
| **Test Set 2** | Outer Race Fault | LSTM Sequential Severity Model | **Fault Trigger Active** |
| **Test Set 1** | Inner Race & Roller Faults | Random Forest Classifier | **99.7%** |
| **Test Set 1** | Inner Race & Roller Faults | Multi-Layer Perceptron (ANN) | **99.0%** |

---

## 🚀 How to Run the Project

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/YOUR_USERNAME/Predictive-Maintenance-NASA-Bearing.git
   cd Predictive-Maintenance-NASA-Bearing
   ```

2. **Install Required Packages**:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn tensorflow tqdm
   ```

3. **Open Notebook**:
   Launch `new2.ipynb` in Jupyter Notebook or VS Code and execute the cells sequentially!

---

## 📄 License
Distributed under the MIT License. See `LICENSE` for more information.
