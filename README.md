# **Appliances Energy Prediction: Model Training and Analysis** 


The dataset for this quiz is the Appliances Energy Prediction data from https://archive.ics.uci.edu/ml/machine-learning-databases/00374.

It can also be accessed from https://drive.google.com/file/d/1Eru_UHVc3WLHVveC9Q8K9QUxlzYeHt18/view?usp=share_link.

The code attached to it is my solution to the quiz. The dataset is also provided for direct download.

 

## **Overview**  
Energy consumption prediction is essential for optimizing appliance usage, reducing costs, and improving energy efficiency. This project focuses on predicting **appliance energy consumption** using multiple regression models. The dataset was preprocessed, and different models were trained to evaluate performance based on various metrics.  

---  

## **Workflow and Methodology**  

### **1. Data Preprocessing: Scaling with Min-Max Scaler**  
- The dataset was normalized using **MinMaxScaler** to scale all feature values between **0 and 1**.  
- This ensures that no single feature dominates the learning process due to differing magnitudes.  

### **2. Model Selection and Training**  
The dataset was split into **training and testing sets** using **train_test_split**. Cross-validation (**cross_validate**) was applied to enhance model reliability.  

The following regression models were trained:  
- **Linear Regression** (Baseline model)  
- **Ridge Regression** (L2 regularization to reduce overfitting)  
- **Lasso Regression** (L1 regularization for feature selection, α = 0.001)  

### **3. Performance Evaluation Metrics**  
To assess model accuracy and reliability, the following metrics were used:  
- **Mean Absolute Error (MAE)** – Measures the average error between actual and predicted values.  
- **Mean Squared Error (MSE)** – Penalizes larger errors more significantly.  
- **R² Score** – Evaluates how well the model explains variance in the dataset.  

### **4. Feature Importance Analysis**  
From the **Linear Regression** and **Lasso Regression (α = 0.001)** models:  
- Features with **the lowest and highest weights** were identified.  
- Features with **non-zero weights** in Lasso Regression were extracted, providing insights into the most influential variables.  

### **5. Model Performance Comparison (RMSE Scores)**  
| Model                 | Train RMSE | Test RMSE |  
|----------------------|------------|-----------|  
| **Linear Regression** | **95.216**  | **93.640**  |  
| **Ridge Regression**  | **93.716**  |   |  
| **Lasso Regression (α=0.001)** | **99.813**  |  |  

- The **Linear and Ridge Regression models** had lower RMSE values, indicating better generalization.  
- The **Lasso Regression model** had a higher RMSE, likely due to feature regularization affecting predictive performance.  

### **6. Conclusion on Linear Regression Model**  
- **RMSE Interpretation**: A **smaller RMSE** indicates a better model.  
- The **test RMSE (93.640) is lower than the train RMSE (95.216)**.  
- This suggests that **the model did not overfit** on the training set, making it a **well-generalized model** for predicting appliance energy consumption.  

---  

## **Key Takeaways**  
✔ **Feature Scaling** improves model stability and convergence.  
✔ **Regularization Techniques** (L1 and L2) help prevent overfitting and improve feature selection.  
✔ **Linear Regression performed well**, with Ridge Regression offering slight improvements.  
✔ **Lasso Regression, while useful for feature selection, had a higher error rate**, impacting predictive accuracy.  

