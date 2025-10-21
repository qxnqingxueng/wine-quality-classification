# wine-quality-classification

📝 Project Overview
This repository contains the machine learning implementation for a binary classification task focused on predicting the quality of wine based on its physicochemical properties.<br> The main goal is to categorize wine samples as either "Good Quality" or "Bad Quality". The methodology includes extensive preprocessing, feature importance assessment, and comparison across multiple algorithms, including iterative testing of various feature subsets.<br>

--------------------------------------------------------------------------------
📊 Dataset and Target Variable
The project uses the winequality.csv dataset.<br>
Features (Physicochemical Properties)
The model inputs rely on eleven features:
• Fixed acidity<br>
• Volatile acidity<br>
• Citric acid<br>
• Residual sugar<br>
• Chlorides<br>
• Free sulfur dioxide<br>
• Total sulfur dioxide<br>
• Density<br>
• pH<br>
• Sulphates<br>
• Alcohol<br>
Target Transformation
The original quantitative 'quality' score was converted into a binary target variable, 'quality_binary':<br>
• Good Quality (1): Original quality score ≥7<br>
• Bad Quality (0): Original quality score <7<br>

--------------------------------------------------------------------------------
🛠️ Data Pipeline and Methodology
1. Data Preprocessing
• Null Check: The dataset was verified to contain zero null values.<br>
• Duplicate Handling: Duplicate rows present in the initial dataset were removed.<br>
• Data Split: The data was partitioned into a training set (70%) and a testing set (30%).<br>
• Feature Scaling: Standard scaling using StandardScaler was applied to the features prior to training distance-based models like KNN and SVM.<br>
2. Feature Selection
Feature importance was analyzed using an ExtraTreesClassifier model, which ranked the influence of the 11 attributes on predicting quality. The importance visualization guided iterative model testing using various subsets of features (e.g., 2, 3, 4, up to 9 features) to find the combination yielding the highest performance metrics.<br>
3. Model Implementation and Tuning
Three primary model types were deployed and evaluated:<br>
K-Nearest Neighbors (KNN)
• The optimal number of neighbors (k) was searched for (e.g., k=17 was determined as optimal based on cross-validation accuracy plot).
• Trained and evaluated iteratively across various feature subsets.<br>
Decision Tree
• The classifier was instantiated using the 'gini' criterion.
• Tested across varying feature subsets.<br>
Support Vector Machines (SVM)
The SVM section involved the most comprehensive evaluation, testing three kernel types and performing hyperparameter tuning:
1. Linear Kernel: Tested different C values (0.01, 0.1, 1.0).
2. Polynomial Kernel: Evaluated different polynomial degrees (1 through 5).
3. Radial Basis Function (RBF) Kernel: Optimized using a search over multiple gamma and C values.<br>
The RBF kernel generally achieved the highest accuracy compared to the Linear and Polynomial kernels and was therefore selected as the best performing SVM approach.<br>

--------------------------------------------------------------------------------
📈 Evaluation Metrics
All models were measured using a standard suite of classification metrics:<br>
• Accuracy Score<br>
• Precision<br>
• Recall<br>
• F1 Score<br>
• Confusion Matrix<br>
