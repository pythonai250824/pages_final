# 📊 Final Project: FastAPI Server for Model Training and Prediction

## 🎯 Project Goal

The project starts with the simplest machine learning model: **Linear Regression**. Once the pipeline is implemented, you can expand to additional model types such as Random Forest, Logistic Regression, or SVM.


Build a FastAPI server that allows:
- Uploading a CSV file with data
- Training machine learning models based on user input
- Performing predictions using the trained model
- Specifying which columns are features and which column is the label


## 🧱️ Architecture Overview
- Data is uploaded as a CSV file
- The user specifies which columns are features and which is the label
- The model is trained based on the uploaded file and the provided configuration
- The model is saved as a `.pkl` file along with its feature and label metadata


## 🔌 API Endpoints


### ⚙️ `POST /train`
Receives a CSV file and trains a model using the selected features and label.
You can also pass additional parameters specific to the model (e.g., estimator settings, feature scaling options, etc.).
These parameters are currently unused for Linear Regression but will be supported in future extensions.

- `file`: the CSV file
- `model_name`: e.g. "linear"
- `features`: JSON array of column names
- `label`: name of the target column
- `model_params` (optional): JSON object containing hyperparameters for the selected model
#### Output:
```json
{
  "status": "model trained",
  "features": ["age", "salary", "rooms"],
  "label": "price"
}
```

### 🎯 `POST /predict/{model_name}`
Receives feature values and returns a prediction from the trained model
#### Input:
```json
{
  "age": 35,
  "salary": 70000,
  "rooms": 3
}
```
#### Output:
```json
{
  "prediction": 322000
}
```

### 📊 `GET /models`
Returns a list of all trained models, including type, training date, features, and label


## 🧰 Technologies Used
- Python 3.10+
- FastAPI
- Pydantic
- Pandas
- Scikit-learn
- Joblib (for saving models)
- Optional: SQLite or SQLAlchemy for managing metadata and models


## ✅ Development Steps

## 📦 Model Usage Tracking
A simple SQLite database can be used to keep track of user activity:
- Number of models trained per user
- Number of prediction requests made per user

Each action will be logged with a timestamp and user identifier (email or token-based). This allows for usage monitoring, rate limiting, and reporting.

### 🧪 Full Example

#### Step 1: Train a Model
**Endpoint:** `POST /train`
**Type:** multipart/form-data

**Form Fields:**
- `file`: CSV file containing your data
- `model_name`: `linear`
- `features`: `["age", "salary", "rooms"]`
- `label`: `price`

**Example CSV content:**
```csv
age,salary,rooms,price
30,50000,2,200000
40,80000,3,350000
50,100000,4,450000
```

**Expected Response:**
```json
{
  "status": "model trained",
  "features": ["age", "salary", "rooms"],
  "label": "price"
}
```

#### Step 2: Make a Prediction
**Endpoint:** `POST /predict/linear`

**Request Body:**
```json
{
  "age": 35,
  "salary": 70000,
  "rooms": 3
}
```

**Expected Response:**
```json
{
  "prediction": 322000
}
```

## 💡 Optional Extensions
- Email + JWT authentication
- Support for multiple model types: random_forest, logistic, svr, xgboost
- Model evaluation (MAE, R2, etc.)
- Rate limiting per user/email
- Web UI for uploading data and running predictions
## 📤 הגשה

יש לשלוח את הפתרון למייל:
📧 [pythonai170624+FINALSERVER@gmail.com](mailto:pythonai170624+FINALSERVER@gmail.com)


