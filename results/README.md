# Experiment Results

This folder contains the results and visualizations from Milestone 1 of ShopInsight AI, developed for CMPT 310 (Group 13).

We evaluated three baseline models—Logistic Regression, Decision Tree, and K-Nearest Neighbors (KNN)—to predict whether an online shopping session would result in a purchase. All reported model results are based on the validation set.

## 1. Results Files

| File | Description |
|---|---|
| `baseline_results.csv` | Performance metrics for the three baseline models |
| `pagevalues_comparison.csv` | Model performance with and without the PageValues feature |
| `class_imbalance_results.csv` | Comparison of original and balanced class weights |
| `threshold_results.csv` | Precision, recall, and F1-score at different decision thresholds |

## 2. Visualizations

| File | Description |
|---|---|
| `class_distribution.png` | Number of purchase and non-purchase sessions |
| `dataset_exploration.png` | Product page visits, browsing duration, PageValues, and visitor-type analysis |
| `baseline_model_comparison.png` | Comparison of accuracy, precision, recall, F1-score, and ROC-AUC |
| `correctly_detected_purchases.png` | Number of actual purchases correctly identified by each model |
| `confusion_matrices.png` | Confusion matrices for all three baseline models |
| `roc_curves.png` | ROC curve comparison |
| `precision_recall_curves.png` | Precision-recall curve comparison |
| `pagevalues_comparison.png` | F1-score comparison with and without PageValues |
| `class_imbalance_comparison.png` | Effect of balanced class weights on model performance |
| `threshold_tuning.png` | Precision, recall, and F1-score across decision thresholds |
| `purchase_probabilities.png` | Example purchase probabilities from the Decision Tree model |

## 3. Baseline Model Performance

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 0.8886 | 0.7971 | 0.3846 | 0.5189 | 0.8921 |
| Decision Tree | 0.8979 | 0.7004 | 0.6049 | 0.6492 | 0.9231 |
| KNN | 0.8837 | 0.7325 | 0.4021 | 0.5192 | 0.8067 |

The Decision Tree achieved the highest baseline F1-score and ROC-AUC. It correctly identified 173 of the 286 purchases in the validation set.

## 4. Experiment Findings

### PageValues Experiment

Removing PageValues significantly reduced performance for all three models. This suggests that PageValues is an important predictive feature. However, its availability at prediction time needs further investigation.

### Class Imbalance Experiment

The dataset contains considerably fewer purchase sessions than non-purchase sessions. Balanced class weights improved recall for both Logistic Regression and Decision Tree, although precision decreased.

### Decision Threshold Tuning

Changing the classification threshold affected the balance between precision and recall.

The highest validation F1-scores among the tested thresholds were:

- Decision Tree: 0.6799 at threshold 0.65
- Logistic Regression: 0.6425 at threshold 0.60

These thresholds were selected using validation data, not the held-out test set.

### Purchase Prediction Demonstration

The Decision Tree model was used to display purchase probabilities for example shopping sessions. This demonstrates how the model can provide both a predicted outcome and a probability estimate.

## 5. Next Steps

For Milestone 2, we plan to:

- Implement a neural network from scratch using NumPy, including forward propagation, backpropagation, and stochastic gradient descent.
- Compare the custom neural network with a library implementation.
- Experiment with gradient boosting.
- Investigate PageValues availability and potential information leakage.
- Evaluate model performance on later-month data.
- Further improve purchase detection and evaluate the final model on held-out data.

## 6. Reproducibility

The code, preprocessing steps, model training, evaluation, and visualizations are available in:

`notebooks/ShopInsight_Milestone1.ipynb`

The notebook contains the experiments used to generate these results.
