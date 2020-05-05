# Module 7 Deploying and Consuming Models

## 7.1 Real-time Inferencing

### 7.1.1 What is Real-Time Inferencing
In machine learning, inferencing refers to the use of a trained model to predict labels for new data on which the model has not been trained.

In Azure Machine learning, you can create real-time inferencing solutions by deploying a model as a real-time service, 
hosted in a containerized platform such as Azure Kubernetes Services (AKS).

### 7.1.2 Deploying a Real-Time Inferencing Service
You can deploy a model as a real-time web service to several kinds of compute target, including local compute, 
an Azure Machine Learning compute instance, an Azure Container Instance (ACI), an Azure Kubernetes Service (AKS) cluster, 
an Azure Function, or an Internet of Things (IoT) module.

Azure Machine Learning uses containers as a deployment mechanism, packaging the model and the code to use it as an image 
that can be deployed to a container in your chosen compute target.

### 7.1.3 Consuming a Real-Time Inferencing Service

### 7.1.4 Troubleshooting a Real-Time Inferencing Service

## 7.2 Batch Inferencing
