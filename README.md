# MLOps Project

# 🚀 MLOps Project with Gaussian Naive Bayes

This repository presents a complete MLOps (Machine Learning Operations) pipeline, covering everything from data preparation to deployment and monitoring of a machine learning model in production.

---

## 📌 Objective

Automate and scale the lifecycle of a Gaussian Naive Bayes model with hyperparameters using modern MLOps practices, such as model versioning, experiment tracking, deployment via API, and reproducibility of results. We apply this MLOps pipeline to the **Credit.csv** dataset from a German bank to predict customers who are good or bad payers.

## 🤔 Why Gaussian Naive Bayes?

GNB was chosen because it is simple, fast, and effective for classification tasks with approximately continuous variables. It serves as a good baseline for problems with data that follow (or approximate) a normal distribution. Additionally, its low computational cost and easy interpretability make it ideal for an initial version of the MLOps pipeline.

---

## ⚙️ Technologies and Tools Used

- **Python**  
- **MLflow**: Experiment tracking, model registry, and deployment of machine learning models.
- **MLflow.sklearn**: Integration between Scikit-learn and MLflow for model logging and saving.
- **Scikit-learn**: Model training (Naive Bayes), evaluation (accuracy, F1-score, AUC, etc.), and data splitting with `train_test_split`.
- **Pandas**: Reading, manipulating, and analyzing tabular data (DataFrames).
- **NumPy**: Mathematical operations and manipulation of numerical arrays.
- **Matplotlib**: Data visualization and charts such as ROC curve and confusion matrix.
- **Seaborn**: Creation of more elaborate statistical visualizations (such as heatmaps).
- **Requests**: Making HTTP requests

These technologies cover the entire machine learning pipeline: from data preparation to modeling, evaluation, visualization, and deployment with MLflow.

---

## 🧠 MLOps Pipeline Steps

1. **📊 Data Analysis and Preparation**
   - Data collection, cleaning, and transformation.
   - Split into training and test sets.

2. **🏗️ Model Training**
   - Selection of the Gaussian Naive Bayes algorithm
   - Setting the `var_smoothing` hyperparameter to avoid zero probability issues and improve model generalization.
   - Logging experiments in MLflow (parameters, metrics, and artifacts).

3. **📦 Versioning and Registration**
   - Registering the model in MLflow.

4. **🚀 Model Deployment**
   - Machine learning model made available locally as a service via MLflow, with an HTTP endpoint for predictions. The application allows external consumption through REST requests.

5. **📈 Monitoring and Re-evaluation**
   - Structure for periodic model revalidation with new data.
   - Logging of production metrics

---

## ✅ Results

The model achieved the following results on the test data:

| Metric     | Value                |
|------------|----------------------|
| Accuracy   | 0.6967               |
| AUC        | 0.6600               |
| F1 Score   | 0.7719               |
| Log Loss   | 10.9332              |
| Precision  | 0.7739               |
| Recall     | 0.7700               |

 - Accuracy (~69.7%): the model gets almost 7 out of 10 predictions right.
 - AUC (0.66): moderate ability to distinguish between classes.
 - F1 Score (0.77): good balance between precision and recall.
 - Precision (0.77): among positive predictions, 77% are correct (low false positive rate).
 - Recall (0.77): the model identifies 77% of actual positive cases (low false negative rate).
 - Log Loss (10.93): relatively high, indicating that the predicted probabilities may not be very reliable. This suggests that it may be worthwhile to retrain the model using techniques such as K-Folds cross-validation and combining with other algorithms.
