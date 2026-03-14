# Privacy-Preserving Machine Learning with Differential Privacy

This project explores **privacy risks in machine learning models** and demonstrates how **Differential Privacy (DP)** can be used to protect sensitive training data. The experiments analyze how models can unintentionally memorize training data and how privacy-preserving training techniques can mitigate these risks.

The project includes:

- Training a **baseline neural network model**
- Implementing **Differentially Private Stochastic Gradient Descent (DP-SGD)**
- Evaluating **privacy vs utility trade-offs**
- Understanding **privacy leakage in machine learning**

The goal is to study how machine learning models can be trained while **protecting sensitive information in the dataset**.

---

# Project Overview

Machine learning models trained on sensitive datasets may **memorize private information**. Attackers can exploit this behavior through **membership inference attacks** or **data extraction attacks**.

Differential Privacy provides a mathematical guarantee that the **presence or absence of any individual training sample does not significantly affect the model’s output**.

This project compares:

1. **Standard model training**
2. **Differentially private training using DP-SGD**

and evaluates the **trade-off between model accuracy and privacy protection**.

---

# Dataset

The experiments use the **MNIST dataset**, a standard benchmark dataset for image classification.

Dataset characteristics:

- **70,000 grayscale images**
- Image size: **28 × 28 pixels**
- **10 classes (digits 0–9)**

The dataset is split into:

- **Training set**
- **Test set**

Each image represents a handwritten digit used to train and evaluate classification models.

---

# Baseline Model

A **neural network classifier** is trained on the dataset using standard stochastic gradient descent.

### Model Characteristics

- Input layer for **28 × 28 pixel images**
- Fully connected hidden layers
- Output layer for **10 digit classes**

This baseline model represents the **standard training pipeline without privacy protection**.

### Baseline Performance

| Metric | Score |
|------|------|
| Test Accuracy | High classification accuracy on MNIST |

The baseline model achieves strong performance but **does not provide any privacy guarantees**.

---

# Differential Privacy

Differential Privacy ensures that the model **does not reveal information about individual training samples**.

The training process modifies gradient updates so that no single data point significantly influences the model.

Key components of Differential Privacy:

- **Gradient Clipping** – limits the contribution of each training example
- **Noise Injection** – adds calibrated noise to gradients
- **Privacy Budget (ε)** – measures the strength of privacy protection

Lower ε → **stronger privacy protection**  
Higher ε → **better model accuracy but weaker privacy guarantees**

---

# DP-SGD Training

The project implements **Differentially Private Stochastic Gradient Descent (DP-SGD)**.

Training process:

1. Compute gradients for each training sample
2. Clip gradients to a fixed norm
3. Add Gaussian noise to gradients
4. Update model parameters

This prevents the model from memorizing specific training samples.

---

# Privacy vs Utility Trade-off

Differential privacy introduces a trade-off between:

- **Model accuracy**
- **Privacy protection**

Adding more noise improves privacy but reduces model performance.

Key observations:

- Standard training achieves **higher accuracy**
- DP-SGD reduces accuracy slightly
- DP-SGD provides **formal privacy guarantees**

This trade-off is central to privacy-preserving machine learning.

---

# Technologies Used

- Python
- PyTorch
- NumPy
- Matplotlib
- Jupyter Notebook

---

# Repository Structure

```
.
├── Sindhu-Pasupuleti-Exp3.ipynb
├── README.md
└── data/
    └── MNIST dataset
```

---

# How to Run

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/privacy-preserving-ml.git
cd privacy-preserving-ml
```

### 2. Install dependencies

```bash
pip install torch torchvision numpy matplotlib
```

### 3. Run the notebook

```bash
jupyter notebook Sindhu-Pasupuleti-Exp3.ipynb
```

---

# Key Learning Outcomes

This project demonstrates:

- Understanding **privacy risks in machine learning**
- Implementing **Differential Privacy**
- Training models using **DP-SGD**
- Evaluating **privacy vs accuracy trade-offs**
- Designing **privacy-preserving AI systems**

---

# Why Privacy in AI Matters

Machine learning models are increasingly trained on **sensitive data**, including:

- healthcare records
- financial transactions
- personal user data

Without privacy protections, models may leak sensitive information. Techniques such as **Differential Privacy** are essential for building **secure and trustworthy AI systems**.
