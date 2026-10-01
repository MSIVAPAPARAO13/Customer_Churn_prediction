# Customer Churn Prediction

An Artificial Neural Network-based machine learning application that predicts the probability of customer churn using demographic, financial, account and engagement information.

**GitHub Repository:** https://github.com/MSIVAPAPARAO13/Customer_Churn_prediction

---

## Project Overview

Customer churn prediction helps organizations identify customers who may leave their service.

This project implements a binary classification system using a **TensorFlow/Keras Artificial Neural Network (ANN)** and provides a **Streamlit web application** for interactive predictions.

The application accepts customer information, applies the same preprocessing pipeline used during model development, and returns a churn probability.

---

## Features

* Customer churn probability prediction
* Artificial Neural Network classification
* Gender label encoding
* Geography one-hot encoding
* Feature standardization
* Saved model and preprocessing artifacts
* Interactive Streamlit interface
* Probability-based churn classification
* Reusable inference pipeline

---

## Dataset

The project uses `Churn_Modelling.csv`.

### Dataset Size

**10,000 customer records**

### Main Features

| Feature         | Description                 |
| --------------- | --------------------------- |
| CreditScore     | Customer credit score       |
| Geography       | Customer geography          |
| Gender          | Customer gender             |
| Age             | Customer age                |
| Tenure          | Years with the institution  |
| Balance         | Account balance             |
| NumOfProducts   | Number of products used     |
| HasCrCard       | Credit card ownership       |
| IsActiveMember  | Active membership indicator |
| EstimatedSalary | Estimated salary            |
| Exited          | Churn target                |

The original dataset also contains identifier-related columns such as `RowNumber`, `CustomerId`, and `Surname`.

---

## Machine Learning Pipeline

The inference pipeline follows these steps:

```text
Customer Input
      ↓
Gender Label Encoding
      ↓
Geography One-Hot Encoding
      ↓
Feature Combination
      ↓
StandardScaler Transformation
      ↓
ANN Model
      ↓
Churn Probability
      ↓
0.5 Classification Threshold
```

---

## Preprocessing

### Gender Encoding

The Gender column is converted into numerical form using a saved `LabelEncoder`.

### Geography Encoding

Geography is converted into one-hot encoded features:

```text
Geography_France
Geography_Germany
Geography_Spain
```

### Feature Scaling

The processed features are standardized using a saved `StandardScaler`.

---

## Model

The trained neural network is stored as:

```text
model.h5
```

The application loads the trained model using TensorFlow/Keras.

The model produces a probability value between 0 and 1.

The application uses:

```text
Probability > 0.5 → Customer likely to churn
Probability ≤ 0.5 → Customer not likely to churn
```

---

## Verified Prediction Example

The repository's `prediction.ipynb` contains a working inference example.

### Input

```text
Credit Score: 600
Geography: France
Gender: Male
Age: 40
Tenure: 3
Balance: 60000
Number of Products: 2
Has Credit Card: 1
Active Member: 1
Estimated Salary: 50000
```

### Output

```text
Churn Probability: 0.029739516
Approximately: 2.97%
Prediction: Customer is not likely to churn
```

This is an example inference result from the committed notebook, not a model-wide accuracy metric.

---

## Streamlit Application

The application is implemented in:

```text
app.py
```

Run the application with:

```bash
streamlit run app.py
```

The interface allows users to enter:

* Geography
* Gender
* Age
* Balance
* Credit Score
* Estimated Salary
* Tenure
* Number of Products
* Credit Card status
* Active Member status

The application then displays:

```text
Churn Probability
```

and the corresponding churn classification.

---

## Project Structure

```text
Customer_Churn_prediction/
│
├── Churn_Modelling.csv
├── LICENSE
├── README.md
├── app.py
├── experiments.ipynb
├── prediction.ipynb
│
├── model.h5
├── label_encoder_gender.pkl
├── onehot_encoder_geo.pkl
├── scaler.pkl
│
└── requirements.txt
```

---

## Technologies Used

### Programming

* Python

### Machine Learning / Deep Learning

* TensorFlow
* Keras
* Scikit-learn
* NumPy
* Pandas

### Data Visualization

* Matplotlib
* Seaborn
* TensorBoard

### Application

* Streamlit

### Model Persistence

* Pickle
* Keras `.h5` model format

---

## Installation

Clone the repository:

```bash
git clone https://github.com/MSIVAPAPARAO13/Customer_Churn_prediction.git
cd Customer_Churn_prediction
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Requirements

The repository currently specifies:

```text
tensorflow==2.15.0
pandas
numpy
scikit-learn
matplotlib
seaborn
tensorboard
streamlit
```

---

## Run the Application

```bash
streamlit run app.py
```

The Streamlit interface will open in the browser.

---

## Model Artifacts

The repository contains the trained model and preprocessing objects required for inference:

```text
model.h5
label_encoder_gender.pkl
onehot_encoder_geo.pkl
scaler.pkl
```

This allows the application to perform predictions without retraining the model.

---

## Key Learning Outcomes

* Building an ANN for binary classification
* Preparing structured customer data for deep learning
* Encoding categorical variables
* Scaling numerical features
* Saving and reusing preprocessing objects
* Loading trained Keras models for inference
* Building an interactive ML prediction interface with Streamlit

---

## Future Improvements

Possible improvements include:

* Add formal train/validation/test evaluation metrics
* Report accuracy, precision, recall, F1-score and ROC-AUC
* Add confusion matrix and ROC curve
* Add class-imbalance analysis
* Add feature importance/explainability
* Add batch CSV prediction
* Add model monitoring
* Containerize the application using Docker
* Deploy the Streamlit application to a cloud platform

---

## Author

**Siva Paparao Medisetti**

GitHub: https://github.com/MSIVAPAPARAO13/Customer_Churn_prediction
