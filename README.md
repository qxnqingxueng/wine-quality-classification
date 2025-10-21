# wine-quality-classification

# 🍷 Wine Quality Classification — CPC152

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1599SYZq-zMO2-u14mMU3Ey7r2J-M-1Dp?usp=sharing)

This repository contains a **machine learning project** focusing on **wine quality classification**.  
The objective is to develop and evaluate several classification models (**KNN, Naive Bayes, Decision Tree, and SVM**) to predict whether a wine is considered **"Good Quality"** or **"Bad Quality"** based on its physicochemical properties.

---

## 💾 Dataset

The project uses the **`winequality.csv`** dataset.

### Data Attributes (Features)

The input features describe the chemical properties of wine, including:

- Fixed acidity  
- Volatile acidity  
- Citric acid  
- Residual sugar  
- Chlorides  
- Free sulfur dioxide  
- Total sulfur dioxide  
- Density  
- pH  
- Sulphates  
- Alcohol  

### Target Variable

The original `quality` score was transformed to create a **binary classification label** `quality_binary`:

- **Good Quality (1):** Original quality score ≥ 7  
- **Bad Quality (0):** Original quality score < 7  

---

## ✨ Methodology and Pipeline

The analysis pipeline follows a structured approach: data cleaning, feature engineering, model selection, and evaluation.

### 1. Data Cleaning and Preprocessing
- **Null Value Check:** The dataset contained no missing values.  
- **Duplicate Handling:** Duplicate rows were identified and removed.  
- **Data Splitting:** Dataset divided into training (70%) and testing (30%).  
- **Feature Scaling:** `StandardScaler` applied for certain models (notably SVM).

### 2. Feature Selection
Feature importance was assessed using an **ExtraTreesClassifier** model to determine the most significant features.

- Models were evaluated using feature subsets ranging from **2 to 9 features** to study their impact on performance metrics.

### 3. Model Implementation and Tuning

| Model | Description | Key Tuning / Evaluation |
|--------|--------------|--------------------------|
| **K-Nearest Neighbors (KNN)** | Evaluated with feature subsets from 2F–9F. | Optimal `k` value determined via cross-validation (e.g. `k=17`). |
| **Naive Bayes (GaussianNB)** | Simple baseline model for comparison. | Standard training and evaluation metrics. |
| **Decision Tree** | Trained using `gini` criterion. | Tested across multiple feature subsets (2F–9F). |
| **Support Vector Machines (SVM)** | Extensively tested with different kernels and hyperparameters. | Linear (C=0.01–1.0), Polynomial (degrees 1–5), and RBF (grid search for Gamma and C). |

🔹 The **RBF Kernel SVM** achieved the **highest accuracy** and was selected as the final model.

---

## 📊 Evaluation and Results

All models were evaluated using key classification metrics:

- **Accuracy Score**  
- **Precision**  
- **Recall**  
- **F1 Score**  
- **Confusion Matrix**

Performance was analyzed across increasing feature subsets to understand how feature count influences model performance.

---

## 📈 Key Findings

- Removing duplicates improved data consistency.  
- Feature scaling notably boosted SVM performance.  
- RBF SVM consistently outperformed other models in both accuracy and F1-score.  
- Feature importance analysis helped optimize model complexity without sacrificing accuracy.

---

## 🧠 Technologies Used

- Python  
- NumPy, Pandas, Matplotlib, Seaborn  
- Scikit-learn  
- Google Colab  

---

## 🧾 Citation / Reference
Dataset: [Wine Quality Data Set — UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Wine+Quality)

---

## 🚀 Quick Access
You can open and explore the project notebook directly in Google Colab:

👉 [**Open in Google Colab**](https://colab.research.google.com/drive/1599SYZq-zMO2-u14mMU3Ey7r2J-M-1Dp?usp=sharing)

---

## 🧩 Author
**Ng Xue Qing**  
CPC152 — Machine Learning Project  
Universiti Sains Malaysia (USM)

---

