# MLOps Project - Vehicle Insurance Data Pipeline
Welcome to the Vehicle Data Ingestion & Model Pipeline Project! This repository demonstrates the setup, configuration, and deployment of a comprehensive data pipeline using cutting-edge technologies. The goal of this project is to showcase my skills in data ingestion, model training, AWS integration, and CI/CD pipeline setup. Below are the details of each component of the project, outlining the steps taken to develop, deploy, and evaluate the data pipeline.

---

## 📁 Project Setup and Structure

### Step 1: Project Template
- Start by executing the `template.py` file to set up the initial folder structure and placeholder files for the project.

### Step 2: Package Management
- Set up your local packages with `setup.py` and `pyproject.toml`.
- **Tip**: Learn more about these files from the `crashcourse.txt`.

### Step 3: Virtual Environment and Dependencies
- Create a virtual environment and install dependencies from `requirements.txt`:
  ```bash
  conda create -n vehicle_insurance python=3.10 -y
  conda activate vehicle_insurance
  pip install -r requirements.txt
  ```
- Verify installed packages with:
  ```bash
  pip list
  ```

---

## 📊 Data Management & MongoDB Setup

### Step 4: MongoDB Atlas Configuration
1. Sign up for [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) and create a new project.
2. Set up a free M0 cluster, configure the username/password, and allow access from any IP address (`0.0.0.0/0`).
3. Retrieve the MongoDB connection string and save it (replace `<password>` with your password).

### Step 5: Pushing Data to MongoDB
1. Create a folder `notebook`, add the dataset, and create a notebook `mongoDB_demo.ipynb`.
2. Use the notebook to push data to MongoDB and verify the data in MongoDB Atlas under **Database > Browse Collections**.

---

## 📝 Logging, Exception Handling & Data Exploration

### Step 6: Logging & Exception Handling
- Implement logging and exception handling in a module and test it on a demo file `demo.py`.

### Step 7: Exploratory Data Analysis (EDA) & Feature Engineering
- Perform EDA and feature engineering in the `EDA` and `Feature Engg` notebook for preparing data for the pipeline.

---

## 📥 Data Ingestion

### Step 8: Data Ingestion Pipeline
- Define MongoDB connection functions in `configuration.mongo_db_connections.py`.
- Develop data ingestion components in `data_access` and `components.data_ingestion.py` to fetch and transform data.
- Update `entity/config_entity.py` and `entity/artifact_entity.py` with ingestion configurations.
- Run `demo.py` after setting up the MongoDB connection URL.

### Setting Environment Variables
- Set the MongoDB URL:
  ```bash
  # For Bash
  export MONGODB_URL="mongodb+srv://<username>:<password>...."
  # For PowerShell
  $env:MONGODB_URL = "mongodb+srv://<username>:<password>...."
  ```

---

## 🔍 Data Validation, Transformation & Model Training

### Step 9: Data Validation
- Define the schema in `config.schema.yaml` and implement validation functions in `utils.main_utils.py`.

### Step 10: Data Transformation
- Implement transformation logic in `components.data_transformation.py` and create `estimator.py` in the `entity` folder.

### Step 11: Model Training
- Implement model training in `components.model_trainer.py` using code from `estimator.py`.

---

## 🌐 Cloud Setup for Model Deployment

### Step 12: AWS Setup
1. Log in to AWS and create an IAM user with `AdministratorAccess`.
2. Set AWS credentials as environment variables:
   ```bash
   # For Bash
   export AWS_ACCESS_KEY_ID="YOUR_AWS_ACCESS_KEY_ID"
   export AWS_SECRET_ACCESS_KEY="YOUR_AWS_SECRET_ACCESS_KEY"
   ```

3. Create an S3 bucket for storing models and configure access in `constants.__init__.py`.

### Step 13: Model Evaluation & Deployment to S3
- Create an S3 bucket (`my-model-mlopsproj`) in the `us-east-1` region.
- Develop code to push and pull models from the S3 bucket in `src.aws_storage` and `entity/s3_estimator.py`.

---

## 🚀 Model Evaluation, Deployment & Prediction Pipeline

### Step 14: Model Evaluation & Deployment
- Implement model evaluation and deployment components.
- Set up the prediction pipeline with `app.py` for API integration.

### Step 15: Static and Template Directories
- Add `static` and `template` directories for the user interface.

---

## 🔄 CI/CD Automation with Docker & GitHub Actions

### Step 16: Docker & GitHub Actions
1. Create `Dockerfile` and `.dockerignore`.
2. Set up GitHub Actions with AWS authentication using secrets:
   - `AWS_ACCESS_KEY_ID`
   - `AWS_SECRET_ACCESS_KEY`
   - `AWS_DEFAULT_REGION`
   - `ECR_REPO`

### Step 17: EC2 & ECR Setup
1. Set up an EC2 instance for deployment.
2. Install Docker on EC2.
3. Connect EC2 as a self-hosted runner in GitHub.

### Step 18: Final Deployment Steps
1. Open the 5080 port on EC2.
2. Access the deployed app via `http://<public_ip>:5080`.

---


## 🎯 Project Workflow Summary

1. **Data Ingestion** ➔ **Data Validation** ➔ **Data Transformation**
2. **Model Training** ➔ **Model Evaluation** ➔ **Model Deployment**
3. **CI/CD Automation** with GitHub Actions, Docker, AWS EC2, and ECR




