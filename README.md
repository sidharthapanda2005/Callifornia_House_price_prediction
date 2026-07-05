# 🏠 California Housing Price Prediction using Machine Learning & FastAPI

## 📖 Project Description

This project is an end-to-end Machine Learning application that predicts the median house price in California based on various housing features such as median income, house age, average number of rooms, population, and geographical location.

The project demonstrates the complete Machine Learning lifecycle, starting from data preprocessing and model training to model deployment using FastAPI.

The trained machine learning model is saved using Pickle and served through REST APIs, allowing users to send housing details and receive predicted house prices.

---

# 🎯 Objectives

The main objectives of this project are:

- Learn how to work with a real-world dataset.
- Perform data preprocessing and feature selection.
- Train multiple machine learning algorithms.
- Evaluate and compare model performance.
- Save the best-performing model.
- Deploy the trained model using FastAPI.
- Build REST APIs for real-time predictions.

---

# 📂 Project Structure

```
California-Housing-Prediction/
│
├── MLProject.ipynb
├── housing.py
├── regressor.pkl
├── requirements.txt
└── README.md
```

## Explanation

### MLProject.ipynb

This Jupyter Notebook contains the complete Machine Learning workflow.

It includes:

- Importing libraries
- Loading the California Housing Dataset
- Data preprocessing
- Exploratory Data Analysis (EDA)
- Splitting the dataset
- Training different ML models
- Evaluating the models
- Saving the best model

---

### housing.py

This is the FastAPI application.

It performs the following tasks:

- Loads the saved model.
- Creates API endpoints.
- Accepts user input.
- Predicts house prices.
- Returns prediction results as JSON.

---

### regressor.pkl

This is the serialized machine learning model.

Instead of training the model every time the application starts, the trained model is saved using Pickle and loaded directly.

This makes prediction much faster.

---

### requirements.txt

Contains all Python libraries required to run the project.

Example:

```
fastapi
uvicorn
numpy
pandas
scikit-learn
pickle-mixin
```

Installing these dependencies ensures that anyone cloning the repository can run the project without missing packages.

---

# 📊 Dataset

The project uses the California Housing Dataset available in Scikit-Learn.

The dataset contains information collected from California census data.

Each row represents one housing block.

The target variable is the median house value.

---

# 📌 Features Used

The machine learning model uses the following input features.

## 1. MedInc

Median income of households in the area.

Higher income generally indicates higher housing prices.

---

## 2. HouseAge

Average age of houses in that location.

Older or newer houses may influence the house price.

---

## 3. AveRooms

Average number of rooms per household.

Larger houses usually have more rooms and often cost more.

---

## 4. AveBedrms

Average number of bedrooms.

Used along with average rooms to estimate house size.

---

## 5. Population

Total population living in that block.

Population density can affect housing demand.

---

## 6. AveOccup

Average number of occupants per household.

Provides information about occupancy and living conditions.

---

## 7. Latitude

Geographical latitude coordinate.

Location plays an important role in housing prices.

---

## 8. Longitude

Geographical longitude coordinate.

Combined with latitude, it helps identify the exact location.

---

# 🎯 Target Variable

The target variable is:

Median House Value

This is the value the model tries to predict.

---

# ⚙️ Machine Learning Workflow

## Step 1 - Import Libraries

The notebook imports libraries such as:

- NumPy
- Pandas
- Matplotlib
- Scikit-Learn

These libraries are used for data manipulation, visualization, model training, and evaluation.

---

## Step 2 - Load Dataset

The California Housing dataset is loaded from Scikit-Learn.

The dataset contains both input features and target values.

---

## Step 3 - Data Preprocessing

Data preprocessing prepares the dataset for machine learning.

This includes:

- Checking missing values
- Understanding feature distributions
- Separating features and target

---

## Step 4 - Train-Test Split

The dataset is divided into:

- Training Data (80%)
- Testing Data (20%)

Training data is used to train the model.

Testing data is used to evaluate model performance.

---

## Step 5 - Model Training

Different machine learning algorithms are trained.

Examples include:

- Linear Regression
- Random Forest Regressor

Each model learns the relationship between housing features and house prices.

---

## Step 6 - Model Evaluation

The models are evaluated using performance metrics such as:

- R² Score
- Mean Absolute Error
- Mean Squared Error

The model with the best performance is selected.

---

## Step 7 - Save Model

The trained model is saved using Pickle.

```python
pickle.dump(model, open("regressor.pkl", "wb"))
```

Saving the model prevents retraining every time the application starts.

---

## Step 8 - Deployment

The saved model is deployed using FastAPI.

FastAPI exposes REST APIs that can be called from web applications or mobile applications.

---

# 🚀 FastAPI Application

The FastAPI application is written inside **housing.py**.

It performs three major tasks.

### 1. Load the saved model

The Pickle file is loaded into memory.

```python
pickle_in = open("regressor.pkl","rb")
model = pickle.load(pickle_in)
```

---

### 2. Create API

FastAPI creates endpoints like:

```
GET /
```

and

```
POST /predict
```

---

### 3. Return Predictions

The API receives user inputs.

The model predicts the house price.

The predicted value is returned in JSON format.

Example:

```json
{
    "prediction": 4.52
}
```

---

# 📡 API Endpoints

## GET /

Purpose:

Checks whether the API is running successfully.

Response:

```json
{
    "Deployment": "Hello and Welcome to 5 Minutes Engineering"
}
```

---

## POST /predict

Purpose:

Predict the house price using input values.

Input Parameters:

| Feature | Description |
|----------|-------------|
| MedInc | Median Income |
| HouseAge | House Age |
| AveRooms | Average Rooms |
| AveBedrms | Average Bedrooms |
| Population | Population |
| AveOccup | Average Occupancy |
| Latitude | Latitude |
| Longitude | Longitude |

Output:

```json
{
    "prediction": 4.56
}
```

---

# 💻 How to Run

Clone the repository.

```
git clone https://github.com/yourusername/California-Housing-Prediction.git
```

Install dependencies.

```
pip install -r requirements.txt
```

Run FastAPI.

```
uvicorn housing:app --reload
```

Open your browser.

```
http://127.0.0.1:8000/docs
```

FastAPI automatically generates Swagger UI where you can test the API interactively.

---

# 📈 Future Improvements

Some possible enhancements include:

- Add feature engineering.
- Improve model accuracy using XGBoost.
- Deploy on AWS or Azure.
- Dockerize the application.
- Add user authentication.
- Build a frontend using React or Streamlit.
- Integrate CI/CD using GitHub Actions.

---

# 🛠️ Technologies Used

- Python
- Machine Learning
- Scikit-Learn
- Pandas
- NumPy
- FastAPI
- Uvicorn
- Pickle
- Jupyter Notebook

---

# 📚 Learning Outcomes

By completing this project, you will understand:

- Data preprocessing
- Feature selection
- Regression models
- Model evaluation
- Model serialization
- REST API development
- FastAPI deployment
- Machine Learning project structure
- End-to-end ML deployment

---

# 👨‍💻 Author

**Sidhartha**



You are free to use, modify, and distribute this project with proper attribution.
