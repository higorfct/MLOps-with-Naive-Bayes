# 🚀 MLOps Project with Gaussian Naive Bayes

This repository presents a complete **MLOps (Machine Learning Operations)** pipeline, covering everything from data preparation to deployment and monitoring of a machine learning model in production.

---
## 🚀 How to use

1. **Clone the repository and install dependencies:**
    ```bash 
    git clone https://github.com/higorfct/MLOps-with-Naive-Bayes/tree/main
    cd MLOps-with-Naive-Bayes
    pip install -r requirements.txt
    ```

## 📌 Objective

Automate and scale the lifecycle of a **Gaussian Naive Bayes (GNB)** model with hyperparameters using modern MLOps practices, such as model versioning, experiment tracking, deployment via API, and reproducibility of results.  

We apply this MLOps pipeline to the **Credit.csv** dataset from a German bank to predict customers who are good or bad payers.

---

## 🤔 Why Gaussian Naive Bayes?

GNB was chosen because it is **simple, fast, and effective** for classification tasks with approximately continuous variables. It serves as a strong **baseline model** for problems with data that follow (or approximate) a normal distribution.  

Additionally:
- **Low computational cost**
- **Easy interpretability**
- **Suitable for initial pipeline deployment**

---

## ⚙️ Technologies and Tools Used

- **Python**  
- **MLflow** → Experiment tracking, model registry, deployment  
- **MLflow.sklearn** → Integration between Scikit-learn and MLflow  
- **Scikit-learn** → Training, evaluation (accuracy, F1, AUC), splitting data  
- **Pandas** → Data manipulation and analysis  
- **NumPy** → Numerical operations  
- **Matplotlib** → Data visualization (ROC, confusion matrix)  
- **Seaborn** → Advanced statistical visualizations (heatmaps)  
- **Requests** → HTTP requests for API consumption  

These technologies cover the entire ML pipeline: **data prep → training → evaluation → visualization → deployment → monitoring**.

---

## 🧠 MLOps Pipeline Steps

1. **📊 Data Analysis and Preparation**
   - Data cleaning and transformation
   - Train/test split

2. **🏗️ Model Training**
   - Gaussian Naive Bayes with `var_smoothing`
   - Logging experiments in MLflow (parameters, metrics, artifacts)

3. **📦 Versioning and Registration**
   - Model registered in MLflow Registry

4. **🚀 Model Deployment**
   - Deployed locally as an MLflow service with HTTP endpoint for REST predictions

5. **📈 Monitoring and Re-evaluation**
   - Periodic revalidation with new data
   - Production metrics logging

---

## ✅ Results

The model achieved the following results on the test dataset:

| Metric     | Value    |
|------------|----------|
| Accuracy   | 0.6967   |
| AUC        | 0.6600   |
| F1 Score   | 0.7719   |
| Log Loss   | 10.9332  |
| Precision  | 0.7739   |
| Recall     | 0.7700   |

**Interpretation:**
- **Accuracy (~69.7%)** → ~7 out of 10 predictions correct  
- **AUC (0.66)** → moderate class discrimination ability  
- **F1 Score (0.77)** → good balance between precision & recall  
- **Precision (0.77)** → 77% of positive predictions were correct  
- **Recall (0.77)** → 77% of actual positive cases detected  
- **Log Loss (10.93)** → high value, indicating probability estimates could be improved  

---

## 🔎 Conclusions

- The **Gaussian Naive Bayes** algorithm proved to be a solid **baseline** model for the credit classification problem, reaching balanced performance in **precision and recall**.  
- However, the **AUC** and **Log Loss** suggest that the model still struggles to provide highly reliable probability estimates.  
- For future iterations, improvements could include:
  - Applying **cross-validation** for more robust training.  
  - Testing **ensemble methods** (Random Forest, Gradient Boosting) or **regularized models** (Logistic Regression with penalty).  
- From an **MLOps perspective**, the project successfully demonstrates:
  - Full **lifecycle automation**  
  - **Experiment tracking and versioning** with MLflow  
  - **Reproducibility and deployment** of models into production-like environments  

👉 This pipeline provides a **scalable and reproducible foundation** for deploying and monitoring ML models in real-world financial applications.  
