# Data Collection

## 2.1 Introduction
### Machine Learning cycle
Fetch=>Clean=>Prepare=> (Generate Example Data)
Train=>Evaluate=> (Train the model)
Deploy=>Monitor&Evaluate=> (Deploy model)

### Overview
#### Goal
- Understand the problem
- Understand the parts of input data
- Map data into AWS

## 2.2 Concepts
### Good Data
- large datasets
- precise attribute types, feature rich
- complete fields, no missing values
- values are consistent
- solid distribution of outcomes
- fair sampling
- at least 10 times data of nb of features

### Building a data repository

## 2.3 General Data Terminology
- Datasets = input data = train/test data
- Column = Attribute = Feature
- Row = observation = sample = data point
- Structured data : has a defined schema
- Unstructured data
- Semi-structured data : csv, json, xml
- Databases
- Data warehouses (with data processing)
- Data lakes

## 2.4 Machine Learning Data Terminology
- Labeled data & Unlabeled data
- Categorical & Continuous
- Text data (Corpus data)
- Ground Truth data
- Image data : MNIST, Image Net
- Time series data

### Amazon SageMaker Ground Truth
Tool helps build ground truth datasets

### Dataset Examples
- Image data
- Text data
- Sound data
- Signal data
- Physical data
- Biological data
- Multi-variable data

## 2.5 AWS Data Stores
### S3
- 0 bytes to 5 TB
- Unlimited storage
- Stored into buckets
- S3 is a universal namespace
- https://machinelearning.s3.amazonaws.com/

### Get data into S3
- Upload through the console
- RDS
- DynanoDB
- Redshift
- TimeStream
- DocumentDB

## 2.6 AWS Migration Tools
### Data pipeline
Source -> data pipeline -> S3

Transformation possible

### DMS (database migration service)
Not for transformation. Supports homogenous and heterogeneous migrations.

Set up a source (point for any of these types of sources) and have the data output on any of the target end points

Basiclly for relational databases, but also S3 if needed.

### AWS Glue
Fully managed ETL service.
- Take data from any of these input data sources
- Set up a crawler and classfiers to try to define the schema if possible
- Output data into other AWS services like Athena, EMR, S3 and Redshift

Change data format possible.

### Choosing the right approach
- RDS : AWS Data Pipeline
- Unstructured files in S3 : AWS Glue
- Clustered Redshift data : AWS Data Pipeline / AWS Glue
- MySQL : AWS DMS

## 2.7 AWS Helper Tools
### EMR (Elastic Map Reduce)
Fully managed Hadoop cluster eco-system runs on multiple EC2.

### Athena
Serverless platform to run SQL queries on S3.

### Redshift Spectrum vs Athena
- Redshift Spectrum : must have redshift cluster, made for existing redshift customers
- Athena : new customers quickly want to query S3 data

## 2.8 Exam Tips
