# wine-quality-classification

This repository contains the machine learning project notebook focusing on wine quality classification. The objective of this project is to develop and evaluate several classification models (KNN, Naive Bayes, Decision Tree, and SVM) to predict whether a wine is considered "Good Quality" or "Bad Quality" based on its physicochemical properties.
The methodology includes detailed data preprocessing, iterative feature selection based on importance, extensive hyperparameter tuning, and comprehensive model evaluation.

💾 Dataset
The project uses the winequality.csv dataset.

Data Attributes (Features)
The input features describe the chemical properties of the wine, including:
• Fixed acidity
• Volatile acidity
• Citric acid
• Residual sugar
• Chlorides
• Free sulfur dioxide
• Total sulfur dioxide
• Density
• pH
• Sulphates
• Alcohol

Target Variable
The original 'quality' score was transformed to create a binary classification label, 'quality_binary':
• Good Quality (1): Original quality score ≥7
• Bad Quality (0): Original quality score <7

✨ Methodology and Pipeline
The analysis pipeline followed rigorous steps including data cleaning, feature engineering, and iterative model testing:
1. Data Cleaning and Preprocessing
• Null Value Check: The dataset was confirmed to have no null values.
• Duplicate Handling: Duplicate rows were identified and removed from the dataset.
• Data Splitting: The dataset was split into training (70%) and testing (30%) sets for model development and final evaluation.
• Feature Scaling: StandardScaler was employed for certain models (specifically SVM) to normalize the features before training.
2. Feature Selection
Feature importance was assessed using an ExtraTreesClassifier model trained on the data. This technique helped determine the optimal subset of features for improving model performance.
• The models were repeatedly evaluated across feature subsets ranging from 2 up to 9 features to observe the impact on performance metrics. 

. Model Implementation and Tuning
The following classification algorithms were implemented and rigorously tested:
a) K-Nearest Neighbors(KNN): Tested across various feature subsets (2F to 9F).
Optimal k value was determined (e.g., k=17 based on cross-validation accuracy plot).
b) Naive Bayes (GaussianNB): Trained and evaluated early in the process. Standard training and metrics calculation.
c) Decision Tree: Trained using the 'gini' criterion. Tested across various feature subsets (2F to 9F).
d) Support Vector Machines (SVM): Extensive evaluation was performed comparing different kernel types and hyperparameters. Linear SVM: Tested various C values (0.01, 0.1, 1.0). Polynomial SVM: Tested degrees (1 through 5). RBF Kernel SVM: Grid search conducted for Gamma and C values.

The Radial Basis Function (RBF) Kernel SVM showed the highest accuracy among the tested SVM configurations and was selected as the final model for further iterative feature testing.

📊 Evaluation and Results
All models were evaluated using the following classification metrics:
• Accuracy Score
• Precision
• Recall
• F1 Score
• Confusion Matrix
The evaluation consistently tracked how performance metrics changed as the number of input features increased.
