# 🚰 Water Quality & Pollution Prediction Engine

![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E.svg)
![Streamlit](https://img.shields.io/badge/Streamlit-Web%20App-FF4B4B.svg)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## 📌 Project Overview
An end-to-end Machine Learning web application designed to predict water potability and contamination levels based on chemical properties (such as pH, hardness, solids, chloramines, sulfate, conductivity, organic carbon, trihalomethanes, and turbidity).

## 🔑 Key Features
- **Predictive ML Pipeline:** Trained classification model (`pollution_model.pkl`) to assess water safety.
- **Data Preprocessing:** Feature scaling, imputation of missing values, and column selection stored in `model_columns.pkl`.
- **Interactive Web Interface:** Streamlit web app (`app.py`) allowing users to input water quality metrics and receive instant safety predictions.

## 🛠️ Tech Stack
- **Machine Learning:** Scikit-Learn, Pandas, NumPy
- **Deployment & Web Framework:** Streamlit / Python
- **Model Serialization:** Pickle (`.pkl`)

## 📁 Repository Structure
├── app.py # Web application entry script 

├── WaterQualityPrediction.ipynb # Model training & evaluation notebook 

├── Water_Quality_Prediction_dataset.csv # Dataset used for model training 

├── pollution_model.pkl # Serialized ML model weights 

└── model_columns.pkl # Serialized feature list


## 🚀 How to Run Locally

1. Clone the repository:
   ```bash
   git clone https://github.com/m-santhosh-15/Water_Quality_Prediction.git

2. Install the required dependencies:
   ```bash
   pip install pandas numpy scikit-learn streamlit
  
3. Run the Streamlit web application:
   ```bash
    streamlit run app.py
## 👤 Author
- **Mendu Sri Lalitha Santhosh** 
  - GitHub: [@m-santhosh-15](https://github.com/m-santhosh-15)
  - LinkedIn: [Mendu Sri Lalitha Santhosh](https://www.linkedin.com/in/mendusanthosh)
