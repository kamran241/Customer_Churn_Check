# Machine Learning Model Project

This repository contains a machine learning model integrated with a web application. The project uses scikit-learn for model training, pandas and numpy for data processing, joblib for model persistence, Flask for a prediction API, and Streamlit for an interactive user interface.
## Purpose

The goal is to provide a complete setup for training, deploying, and interacting with a machine learning model via a web app. This `README` outlines the dependencies and instructions to run the project.

## Requirements

### Python Version
- **Python 3.13.3**

### Dependencies
The following packages are required:

| Package        | Version | Purpose                                      |
|----------------|---------|----------------------------------------------|
| Flask         | 3.0.3   | Backend API to serve model predictions       |
| pandas        | 2.2.2   | Data loading and preprocessing               |
| numpy         | 1.26.4  | Numerical operations for data and models     |
| scikit-learn  | 1.5.1   | Model training and evaluation                |
| joblib        | 1.4.2   | Saving and loading trained models            |
| streamlit     | 1.37.1  | Interactive web interface for users          |
| Werkzeug      | 3.0.3   | Flask dependency for request handling        |       |


All dependencies are listed in `requirements.txt`.

## Installation

Follow these steps to set up the project:

1. **Clone the Repository**:
   
   git clone https://github.com/kamran241/Customer_Churn_Check.git
   cd customer_churn_chek

2. **Install Python 3.13.3**:

   Verify:
   python --version

3. **Install Dependencies**:

   Install required packages

   pip install -r requirements.txt

4. **Verify Package Versions**

   Confirm that installed packages match the required versions
      pip list | grep -E "Flask|pandas|numpy|scikit-learn|joblib|streamlit|Werkzeug|python-dotenv|gunicorn"

   
 **after installing dependencies and clone it to your local you have just chance the base dir location from app.py ""C:\Users\kamra\OneDrive\Desktop\churn model"" this to your local base directory location**


 ## How TO Run

 1. **Run the Flask API**

      Run:
       python app.py

2. **Run the Streamlit App**

   Run:
     streamlit run frontend.py
      

 
   
