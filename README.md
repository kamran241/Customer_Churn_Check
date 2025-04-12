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
