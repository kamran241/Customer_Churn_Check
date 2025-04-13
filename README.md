# Customer Churn Prediction Project

This repository hosts a machine learning model for predicting customer churn, integrated with a web application. The project leverages **scikit-learn** for model training, **pandas** and **numpy** for data processing, **joblib** for model persistence, **Flask** for a prediction API, and **Streamlit** for an interactive user interface, Enabling user to input cvc file and view churn prediction and download that prediction file.

![Project Overview](https://github.com/kamran241/Customer_Churn_Check/blob/main/images/Screenshot%202025-04-13%20025809.png)

## Purpose

The goal is to provide a complete, deployable system for training, serving, and interacting with a customer churn prediction model via a web app. This `README` details the dependencies, setup, and instructions to run the project locally or in production.

## Prerequisites

Before starting, ensure you have:
- **Git** installed for cloning the repository.
- A code editor (e.g., VS Code) for modifying files like `app.py`.
- Basic familiarity with Python and terminal commands.

## Requirements

### Python Version
- **Python 3.13.3**: Primary environment for this project. If compatibility issues occur, Python 3.10 is recommended.

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
| Werkzeug      | 3.0.3   | Flask dependency for request handling        |


All dependencies are listed in `requirements.txt`.

## Installation

Follow these steps to set up the project on your local machine:

1. **Clone the Repository**:

   ```bash
      git clone https://github.com/kamran241/Customer_Churn_Check.git  # this will clone the code from gihub 
      cd Customer_Churn_Check  ## this will be used to go to customer_churn_chek directory 

3. **Install Python 3.13.3**
    Download from python.org
       Verify installation:

   ```bash
      python --version  ## this will show you the version of python

5. **Install Dependencies**
    Install required packages:

   ```bash
   pip install -r requirements.txt # this will install all the requirment

7. **Update Base Directory**

     Open app.py in a text editor.
     Change the base directory path from "C:\Users\kamra\OneDrive\Desktop\churn model" to your local project directory (e.g., /home/user/Customer_Churn_Check or C:\path\to\your\project).
      - For example, modify the following lines in app.py:
           - BASE_DIR = r"/path/to/your/project"  # Update this to your project directory
           - MODEL_PATH = os.path.join(BASE_DIR, 'churn_model.pkl')
           - SCALER_PATH = os.path.join(BASE_DIR, 'scaler.pkl')
           - FEATURES_PATH = os.path.join(BASE_DIR, 'feature_columns.pkl')

9. **Verify Package Versions**
   Confirm versions match

   ```bash
   pip list | grep -E "Flask|pandas|numpy|scikit-learn|joblib|streamlit|Werkzeug|python-dotenv|gunicorn"


# IF You Want To Deploy It On Docker(Linux)

To deploy the project in a Docker container on a Linux system, follow these steps:

**1.Ensure Docker is Installed:**
  Install Docker if not already present:
    ```bash
     sudo apt update
     sudo apt install docker.io
     sudo systemctl start docker
     sudo systemctl enable docker
 
 **verify install**
      ```bash
         docker --version

**2.Create a Dockerfile:**
  in the project root, create a file named Dockerfile with the following content:
    ```bash
    FROM python:3.13.3-slim

    WORKDIR /app

    COPY . /app

    RUN pip install --no-cache-dir -r requirements.txt

     EXPOSE 8000 8501

   CMD ["sh", "-c", "python app.py & streamlit run frontend.py --server.port 8501"]

**3.Update Base Directory for Docker:**
  Open app.py and set the base directory to /app, which is the working directory in the Docker container:
     
    - BASE_DIR = r"/app"
    - MODEL_PATH = os.path.join(BASE_DIR, 'churn_model.pkl')
    - SCALER_PATH = os.path.join(BASE_DIR, 'scaler.pkl')
    - FEATURES_PATH = os.path.join(BASE_DIR, 'feature_columns.pkl')
 Save the changes. This ensures the model, scaler, and feature files are correctly referenced within the container.

**4.Build the Docker Image:**
  Run the following command in the project directory:
      ```bash
         docker build -t customer-churn-prediction .

**5.Run the Docker Container:**
   Start the container, mapping ports for Flask (5000) and Streamlit (8501):
       ```bash
          docker run -p 8000:8000 -p 8501:8501 customer-churn-prediction

**6.Access the Application:**
   - Flask API: http://localhost:5000
   - Streamlit UI: http://localhost:8501

**7.Notes"**
    -  Ensure churn_model.pkl, scaler.pkl, and feature_columns.pkl are in the project root before building the Docker image, as they are copied into the /app directory.
    -  If you need to modify paths for a different setup, update BASE_DIR in app.py accordingly before building the image.
# How to Run (locally)

Once set up, run the application as follows:

1. Start the Flask server:

   ```bash
   python app.py # TO run the flask server

3. Run the Streamlit App:
      Launch the Streamlit interface:

   ```bash
   streamlit run frontend.py  ## this will run your ui

## Testing

1. API:
    Use test_data.csv with curl or Postman (see Test Data section).
2. UI:
    Upload test_data.csv in Streamlit or input data manually.

## Test Data
  To test the model, a sample of dataset (test_data.csv) are provided in the repository.
     Download: Find test data from the repo and download it and in **ui** give that data it will give you predictions.
     
![Project Overview](https://github.com/kamran241/Customer_Churn_Check/blob/main/images/Screenshot%202025-04-13%20041231.png)

# Troubleshooting

**Installation Errors:**
   
    
    ```bash
    pip install --upgrade pip  # this will upgrade or install the pip
    pip install -r requirements.txt ## this will install your requirments

**Version Mismatches:**
  
      ```bash   
      pip install -r requirements.txt --force-reinstall ## use this command to forcely install 

**Directory Issues:**
   Update app.py’s directory path correctly.
# License
   MIT License (add LICENSE file if needed).

# Contact
   Raise issues on GitHub or contact the maintainer.





