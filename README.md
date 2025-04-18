# Hospital Data Analysis with PySpark


## Description
This project explores and analyzes hospital admission data using both machine learning (ML) and deep learning (DL) techniques. It involves data loading, cleaning, exploring, and visualizing key metrics from a large hospital dataset. Various data processing techniques are applied, including dealing with missing values, analyzing categorical columns, and summarizing statistics. The models were trained and evaluated using different algorithms to predict hospital charges.

## Key Features
- **Data Loading**: Supports loading data from both CSV files and MongoDB collections using PySpark and the MongoDB Spark connector.
- **Data Exploration**: Comprehensive data exploration with summary statistics, missing value detection, and categorical analysis.
- **Model Evaluation**: Supports training and evaluating multiple models, including Logistic Regression, Random Forest, Decision Tree, and Deep Learning models.
- **Visualization**: Includes visualizations such as confusion matrices and model performance metrics to interpret the results.
- **Alternative Data Sources**: Flexibility to work with different data sources such as CSV files and MongoDB.

## Technologies
- **PySpark**: Used for data loading, exploration, and processing large-scale datasets.
- **MongoDB**: Alternative data source for storing and accessing hospital admission data.
- **Machine Learning**: Models such as Logistic Regression, Random Forest, and Decision Tree were used for classification tasks.
- **Deep Learning**: Neural networks for deep learning-based predictions and model evaluation.
- **Python Libraries**:
  - **scikit-learn**: Used for traditional machine learning models and evaluation metrics.
  - **TensorFlow**: Used for building and evaluating the deep learning model.
  - **pandas**: For data manipulation and conversion between PySpark DataFrame and Pandas DataFrame.
  - **matplotlib, seaborn**: For data visualization, including confusion matrix and performance metrics.
  - **pymongo**: MongoDB connector for accessing data stored in MongoDB.
  

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Model Results](#model-results)
  - [Machine Learning Model Results](#machine-learning-model-results)
  - [Deep Learning Model Results](#deep-learning-model-results).

## Installation
1. Clone the repository:
      ```bash
      https://github.com/mo72001/Bigdata-hospital/blob/main/projectfile/Big_data_Hospital_by_pyspark.ipynb

2.Install required libraries:
         
         pip install pyspark seaborn matplotlib pandas tensorflow scikit-learn pymongo

3. Data source:
     ```bash
     https://rowzero.io/datasets/ny-hospital-dataset?


## Usage
1.Loading the Hospital Admission Dataset:

- Load the Dataset using PySpark (CSV file):
  ```bash
   from pyspark.sql import SparkSession
  spark = SparkSession.builder.appName("HospitalDataAnalysis").getOrCreate()

  # Load dataset (replace with your actual file path)
  file_path = "/path/to/your/dataset.csv"
  df = spark.read.csv(file_path, header=True, inferSchema=True)

  
### OR
- Load the Dataset from MongoDB:
  ```bash
  from pyspark.sql import SparkSession

  # MongoDB connection details
  mongo_uri = ""
  mongo_database = ""
  mongo_collection = ""

  # Initialize the Spark session with MongoDB support
  spark = SparkSession.builder \
    .appName("HospitalDataAnalysis") \
    .config("spark.mongodb.input.uri", f"{mongo_uri}/{mongo_database}.{mongo_collection}") \
    .config("spark.mongodb.output.uri", f"{mongo_uri}/{mongo_database}.{mongo_collection}") \
    .getOrCreate()

  # Load dataset from MongoDB collection
  df = spark.read.format("mongo").option("uri", f"{mongo_uri}/{mongo_database}.{mongo_collection}").load()


## Model Results

### Machine Learning Model Results
- **Logistic Regression**:

  Precision (Class 0): 0.77

  Precision (Class 1): 0.69

  Recall (Class 0): 0.64

  Recall (Class 1): 0.80

  F1-Score (Class 0): 0.70

  F1-Score (Class 1): 0.74

  Accuracy: 0.72

  AUC (Area Under Curve): 0.8077


- **Random Forest**:

  Precision (Class 0): 0.77

  Precision (Class 1): 0.73

  Recall (Class 0): 0.71

  Recall (Class 1): 0.79

  F1-Score (Class 0): 0.74

  F1-Score (Class 1): 0.76

  Accuracy: 0.75

  AUC (Area Under Curve): 0.8320


- **Decision Tree**:


  Precision (Class 0): 0.75

  Precision (Class 1): 0.74

  Recall (Class 0): 0.73

  Recall (Class 1): 0.76

  F1-Score (Class 0): 0.74

  F1-Score (Class 1): 0.75

  Accuracy: 0.74

  AUC (Area Under Curve): 0.7500



### Deep Learning Model Results:

- **Deep Learning**:

   Precision (Class 0): 0.76

   Precision (Class 1): 0.74

   Recall (Class 0): 0.73

   Recall (Class 1): 0.77

   F1-Score (Class 0): 0.74

   F1-Score (Class 1): 0.75

   Accuracy: 0.75

   AUC (Area Under Curve): 0.8379



