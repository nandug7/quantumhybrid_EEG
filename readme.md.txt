Hybrid Quantum Hilbert-Space Feature Expansion Framework for EEG Seizure Classification
Overview

This project presents a Hybrid Quantum–Classical Framework for EEG seizure classification using Quantum Hilbert-Space Feature Expansion combined with a classical machine learning classifier.

The proposed approach transforms PCA-reduced EEG features into a 4096-dimensional quantum probability representation (2¹²) using a 12-qubit ZZFeatureMap, followed by classification using XGBoost.

The framework demonstrates improved performance compared to classical machine learning and baseline quantum machine learning models.

Dataset

This project uses the Epileptic Seizure Recognition Dataset available on Kaggle:

🔗 https://www.kaggle.com/datasets/harunshimanto/epileptic-seizure-recognition

Dataset Description

EEG recordings segmented into time-series samples

Originally consists of 5 classes

Converted into binary classification:

Seizure (Class 1)

Non-Seizure (Classes 2–5)

Preprocessing Steps

Removed unnecessary columns

Balanced dataset: 250 seizure + 250 non-seizure samples

Train/Test split: 300 / 200

Standardization

PCA reduction to 12 components

Proposed Methodology
1️⃣ Classical Preprocessing

Feature scaling

Principal Component Analysis (PCA-12)

2️⃣ Quantum Hilbert-Space Feature Expansion

12-qubit ZZFeatureMap

reps = 2

Full entanglement

Statevector simulation

Probability feature vector of dimension 4096

3️⃣ Classical Classification

Extreme Gradient Boosting (XGBoost)

Probability-based prediction

Threshold = 0.5

Model Comparison

The proposed hybrid model is compared against:

Classical Machine Learning

SVM (RBF)

ExtraTrees

Gradient Boosting

AdaBoost

Baseline Quantum Machine Learning

QSVM

VQC

QNN

Performance Summary
Model	Accuracy	F1-score	ROC-AUC
Best Classical (SVM-RBF)	0.945	0.944	0.9926
Best Quantum Baseline (QSVM)	0.790	0.826	0.9158
Proposed Hybrid Model	0.955	0.955	0.9889

The proposed framework achieves the highest overall classification performance.

Installation

Create a virtual environment:

conda create -n hqhf_eeg python=3.10
conda activate hqhf_eeg

Install required libraries:

pip install numpy pandas matplotlib scikit-learn xgboost
pip install qiskit qiskit-machine-learning
How to Run

Run the data preprocessing notebook.

Run the classical ML baseline notebook.

Run the QML baseline notebook.

Run the proposed hybrid model notebook.

Computational Consideration

Quantum feature expansion uses statevector simulation with exponential complexity:

2
12
=
4096
 dimensional Hilbert space
2
12
=4096 dimensional Hilbert space

This increases computational cost but enhances nonlinear feature representation.

Limitations

Simulation-based quantum execution

Exponential feature expansion complexity

Scalability depends on qubit count

Future Work

Evaluate on real quantum hardware

Optimize qubit usage

Extend to multi-class seizure detection

Validate on larger clinical EEG datasets

Acknowledgment

Dataset obtained from Kaggle:
Epileptic Seizure Recognition Dataset
https://www.kaggle.com/datasets/harunshimanto/epileptic-seizure-recognition