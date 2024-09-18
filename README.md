# DS_capstone_2_2
# Diabetes Prediction App

This project is a **diabetes prediction application** that uses a deep learning model for classifying whether an individual has diabetes based on their gender, age, BMI, blood pressure, and glucose level. The app is built using **Streamlit** for the frontend, **MongoDB** for the database, and **TensorFlow** for the machine learning model.

## Features

- **Frontend**: Streamlit is used to create an interactive user interface where users input personal data such as gender, age, weight, height, blood pressure, and glucose levels.
- **Backend**: A deep learning model built with TensorFlow processes the input data to predict whether the user has diabetes.
- **Database**: The predictions along with the input data are saved to a MongoDB database for future analysis.
- **Model**: The deep learning model is trained using the Keras API and saved in the `.h5` format for deployment.

## Frontend - Streamlit

The frontend of the application allows users to input the following details:
- **Gender**: Selected through radio buttons (`Male` or `Female`).
- **Age**: Input as a number (integer).
- **Weight**: Input in pounds (allows decimals).
- **Height**: Input in inches (allows decimals).
- **BMI**: Automatically calculated based on weight and height.
- **Blood Pressure**: Input as an integer.
- **Glucose Level**: Input as an integer.

Once the inputs are validated, the user can submit the data by clicking the "Predict" button, which will invoke the deep learning model to make a prediction.

## Backend - Deep Learning Model

The deep learning model is a sequential neural network built using TensorFlow and Keras. It has been trained to classify whether the user has diabetes or not, based on the input features:
- **Gender** (encoded as 0 for Male, 1 for Female),
- **Age**,
- **BMI** (calculated from weight and height),
- **Blood Pressure**,
- **Glucose Level**.

The model is saved as `DL_optimized_model.h5` and loaded into the Streamlit app for making predictions.

## Database - MongoDB

The MongoDB database is used to store the user's input data along with the prediction. The MongoDB collection stores:
- Gender (as 0 or 1),
- Age,
- Weight,
- Height,
- Calculated BMI,
- Blood Pressure,
- Glucose Level,
- Prediction result (either 0 or 1 for diabetes classification).

### MongoDB Connection
The app connects to a MongoDB Atlas cluster using the connection string (`mongo_uri`), and stores each prediction in the `DiabetesRepo` database under the `Diabetes Prediction Data` collection.

## How to Run the Project

### Prerequisites
- Python 3.7+
- Streamlit
- TensorFlow
- Keras
- MongoDB (Atlas or Local)
- pymongo (for MongoDB connection)

### Setup Instructions

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/diabetes-prediction-app.git
   cd diabetes-prediction-app
