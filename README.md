MLOps Project - Vehicle Insurance Data Pipeline
Welcome to the Vehicle Data Ingestion & Model Pipeline Project! This repository demonstrates the setup, configuration, and deployment of a comprehensive data pipeline using cutting-edge technologies. The goal of this project is to showcase my skills in data ingestion, model training, AWS integration, and CI/CD pipeline setup. Below are the details of each component of the project, outlining the steps taken to develop, deploy, and evaluate the data pipeline.

Table of Contents
Initial Project Setup
MongoDB Setup
Logging, Exception Handling & Notebooks
Data Ingestion Component
Data Validation, Transformation & Model Training
Model Evaluation & AWS S3 Integration
CI/CD Setup
Initial Project Setup
To begin, execute the following steps to set up the project environment:

Create Project Template:

Run the template.py file to generate the basic project structure.
Configure Setup Files:

Update setup.py and pyproject.toml to import local packages.
Refer to crashcourse.txt for more details on configuring these files.
Create Virtual Environment:

Set up a new virtual environment:
bash
Copy code
conda create -n vehicle python=3.10 -y
conda activate vehicle
Install required modules:
bash
Copy code
pip install -r requirements.txt
Verify package installation with:
bash
Copy code
pip list
MongoDB Setup
Follow these steps to set up MongoDB Atlas and configure the connection:

Sign up to MongoDB Atlas and create a new project.
Create a new cluster by selecting the default service (M0).
Set up database user credentials (username & password).
Configure network access to allow IP range: 0.0.0.0/0.
Retrieve the connection string and save it securely (replace the password).
Create a folder named notebook and add mongoDB_demo.ipynb.
Upload your dataset to MongoDB from the notebook.
Verify data in the MongoDB Atlas console under Database -> Browse Collection.
Logging, Exception Handling & Notebooks
These steps focus on setting up robust logging and exception handling:

Implement a logger file and test it in demo.py.
Write an exception handling file and verify in demo.py.
Add EDA (Exploratory Data Analysis) and Feature Engineering notebooks to the project.
Data Ingestion Component
For the Data Ingestion component, follow the steps below:

Set Up Configuration:

Declare required variables in constants.__init__.py.
Configure mongo_db_connections.py for MongoDB connection.
Develop functionality for data access in proj1_data inside the data_access folder.
Define Data Entities:

Add necessary code to config_entity.py and artifact_entity.py in the entity folder.
Data Ingestion Logic:

Implement data ingestion logic inside data_ingestion.py.
Test the pipeline by running demo.py after setting the MongoDB connection URL.
Environment Configuration:

On Mac/Windows, set the environment variable for the MongoDB URL using the terminal:
bash
Copy code
export MONGODB_URL="mongodb+srv://<username>:<password>"
echo $MONGODB_URL  # Verify
Data Validation, Transformation & Model Training
Follow these steps for Data Validation, Data Transformation, and Model Training components:

Data Validation:

Complete the validation logic in utils.main_utils.py and config.schema.yaml.
Data Transformation:

Implement the transformation logic in the corresponding files and include an estimator.py in the entity folder.
Model Training:

Develop the model training logic in the newly created estimator.py.
Model Evaluation & AWS S3 Integration
AWS Configuration
Before starting with the Model Evaluation and Push to AWS S3, configure AWS services:

Create AWS User:

Log in to AWS console and create an IAM user with AdministratorAccess.
Download the access key CSV file.
Set Up AWS Credentials:

Set environment variables for AWS access:
bash
Copy code
export AWS_ACCESS_KEY_ID="AWS_ACCESS_KEY_ID"
export AWS_SECRET_ACCESS_KEY="AWS_SECRET_ACCESS_KEY"
Configure AWS S3:

Create an S3 bucket for model storage (name: my-model-mlopsproj-1).
Configure aws_connection.py for S3 access and define bucket details in constants.__init__.py.
Model Evaluation:

Implement the logic for Model Evaluation and Pushing Models to S3 using AWS S3 integration.
Set up s3_estimator.py to handle S3-related operations.
CI/CD Setup
Automate the deployment process using CI/CD:

Docker Setup:

Create a Dockerfile and .dockerignore to containerize the application.
Set up the GitHub Actions workflow (aws.yaml) to trigger the pipeline.
AWS Setup for CI/CD:

Create a new IAM user for CI/CD and configure access to AWS services.
Set up an ECR repository for storing Docker images.
EC2 Setup:

Create an EC2 instance (Ubuntu) and install Docker.
Set up Self-hosted runners for GitHub Actions on the EC2 instance.
Configure GitHub Secrets:

Store AWS credentials and ECR information in GitHub Secrets.
Activate CI/CD Pipeline:

After pushing changes, the CI/CD pipeline will automatically be triggered to build, test, and deploy the application.
Expose Application:

Open port 5000 in EC2 to expose the application and access it via the public IP.
Conclusion
This repository provides a complete, industry-grade data pipeline setup involving MongoDB, AWS, Docker, and CI/CD. It demonstrates my technical proficiency in handling complex data engineering tasks and deploying them using modern cloud-based tools and practices.

Feel free to explore the project and get in touch for any questions or collaboration opportunities!


