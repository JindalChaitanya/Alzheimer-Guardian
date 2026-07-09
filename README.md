# 🧠 Alzheimer's Guardian: A Comprehensive CNN Approach for MRI Classification

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange?logo=tensorflow)
![Keras](https://img.shields.io/badge/Keras-2.x-red?logo=keras)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter)
![Accuracy](https://img.shields.io/badge/Max%20Accuracy-99.4%25-brightgreen)

## 📖 Table of Contents
- [Abstract](#-abstract)
- [Motivation](#-motivation)
- [Dataset & Preprocessing](#-dataset--preprocessing)
- [Models & Architecture](#-models--architecture)
- [Results & Performance](#-results--performance)
- [How to Run](#-how-to-run)
- [Future Scope](#-future-scope)
- [Contributors](#-contributors)

---

## 📝 Abstract

Alzheimer’s disease (AD) is a progressive neurodegenerative disorder that severely impacts memory, cognitive ability, and independence. Early and precise diagnosis is critical, offering a chance for early intervention and personalized treatment.

**Alzheimer’s Guardian** is a deep learning-based diagnostic tool designed to classify Alzheimer's Disease from MRI scans. By leveraging powerful Convolutional Neural Networks (CNNs), the project identifies subtle changes in brain structure (such as atrophy in memory-related regions) that precede physical symptoms. This repository explores multiple architectures, ranging from custom Sequential models to advanced transfer-learning approaches like ResNet and Xception, pushing the boundaries of automated medical image analysis.

---

## 💡 Motivation

The traditional diagnosis of Alzheimer's often relies on identifying symptoms that are already in advanced stages. By utilizing modern Deep Learning and neuroimaging (MRI/PET scans), we can detect microscopic changes much earlier. The goal of this project is to assist healthcare professionals by providing a highly accurate, robust, and interpretable AI tool, acting as a "Guardian" against the progression of Alzheimer's.

---

## 📊 Dataset & Preprocessing

The models are trained using the **Augmented Alzheimer MRI Dataset** (sourced from platforms like Kaggle, building upon standardized protocols like ADNI).

The data undergoes rigorous preprocessing to ensure high-quality training:
- **Skull-Stripping:** Employing hybrid techniques (BET, ROBEX) to isolate brain tissue.
- **Bias Field Correction:** Utilizing N4 bias field correction to eliminate MRI intensity variations.
- **Spatial Normalization:** Aligning scans to the MNI 152 template for standardized comparison.

**Classes included:**
- Mild Demented
- Moderate Demented
- Non Demented
- Very Mild Demented

---

## 🏗️ Models & Architecture

This project investigates several CNN architectures to find the optimal solution for MRI classification. We used transfer learning with pre-trained weights from `ImageNet`.

The following models were developed and analyzed across multiple Jupyter Notebooks:

1. **Custom Sequential CNN**
   - A standard multi-layer Convolutional Neural Network built from scratch.
2. **ResNet50**
   - A 50-layer deep Residual Network used for baseline transfer learning.
3. **ResNet50V2**
   - An improved version of ResNet50 with pre-activation of weight layers.
4. **Xception (Extreme Inception)**
   - A highly efficient architecture relying on depthwise separable convolutions. This model served as the core of our breakthrough performance.

*Note: Optimization was done using the Adam optimizer and Categorical Cross-Entropy loss. Overfitting was mitigated through Early Stopping, Dropout, and data augmentation.*

---

## 📈 Results & Performance

The models were rigorously evaluated based on metrics such as Accuracy, Sensitivity (Recall), and Confusion Matrices. To ensure interpretability, techniques like **Grad-CAM** (Gradient-weighted Class Activation Mapping) were proposed to visually highlight the brain regions (e.g., hippocampus) triggering the model's decision.

| Model Architecture | Test Accuracy | Note |
| :--- | :---: | :--- |
| **ResNet50** | 26.4% | Baseline comparison (underperformed without fine-tuning) |
| **ResNet50V2** | 90.4% | Significant improvement over base ResNet50 |
| **Custom Sequential** | 93.2% | Excellent performance for a non-transfer learning model |
| **Xception** | **99.4%** | 🏆 **Best Performing Model** - Highly robust and accurate |

---

## 🚀 How to Run

1. **Clone the repository:**
   ```bash
   git clone <your-repo-url>
   cd <repo-folder>
   ```

2. **Install dependencies:**
   Make sure you have Python 3.8+ installed. You will need the following key libraries:
   ```bash
   pip install tensorflow keras pandas numpy scikit-learn matplotlib seaborn
   ```

3. **Download the Dataset:**
   Ensure you have the `augmented-alzheimer-mri-dataset` available and update the dataset paths in the Jupyter Notebooks accordingly.

4. **Run the Jupyter Notebooks:**
   Launch Jupyter Notebook in your terminal and open any of the provided `.ipynb` files to run the code cell by cell.
   ```bash
   jupyter notebook
   ```

---

## 🔮 Future Scope

- **Multimodal Data Fusion:** Integrating MRI data with PET scans, genetic data (e.g., APOE-e4 allele), and clinical biomarkers (blood tests, cognitive testing, EEG) to build a comprehensive patient risk profile.
- **Real-world Clinical Validation:** Testing the model on independent, heterogeneous datasets from diverse hospital environments to ensure broader generalizability.
- **Improved Interpretability:** Further integrating visual explainability (like Grad-CAM) into a clinical user interface to build trust with physicians.

---

## 🎓 Contributors

This project was developed as a Final Year Project for the degree of Bachelor of Technology in Computer Science and Engineering at **JSS Academy of Technical Education, Noida (Dr. APJ Abdul Kalam Technical University)**.

**Authors:**
- Arnav Gupta
- Chaitanya Jindal
- Devesh Sharma

**Under the Supervision of:**
- Vimal Gupta, Department of Computer Science and Engineering

---
*Created with 💙 to aid in the fight against Alzheimer's.*
