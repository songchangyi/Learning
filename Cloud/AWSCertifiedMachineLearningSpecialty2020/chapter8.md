# Evaluation and Optimization

## 8.1 Introduction

## 8.2 Concepts
### Evaluation steps
1. Define evaluation
2. Evaluate
3. Tune
### Validations
- Offline validation : validation set, K-fold
- Online validation : Canary deployment, A/B Testing
### Canary deployment
- Route53
  - 99% => current version
  - 1% => new version

## 8.3 Monitoring and Analyzing Training Jobs
### Algorithm  metrics
- Training metrics
- Validation metrics

SageMaker => CloudWatch

## 8.4 Evaluating Model Accuracy
### Underfitting
1. More data
2. Train longer
### Overfitting
1. More data
2. Early stopping
3. Sprinkle in some noise
4. Regulate
5. Ensembles
6. Ditch some features
### Robust model
### Regression accuracy
#### Residual distribution
#### Math stuff
#### RMSE
### Binary classification accuracy
### Multiclass classfication
### Improving model accuracy
1. Collect data
2. Feature processing
3. Model parameter tuning

## 8.5 Model Tuning
Making small adjustments to hyperparameters to improve the performance of the model.
### Automatic model tuning
1. Choose tunable hyperparameter
2. Choose a range of values
3. Choose the objective metric
### Bayesian Optimization

## 8.6 Exam tips

## 8.7 Evaluation and Optimization Lab
### Sending out team of Scientist
### Final results
Hyperparameters, time, accuracy
### Hints
Create a SageMaker Hyperparameter tuning job with different ranges of values to find the best configuration to minimize the validation loss
metric.

Use the newly optimized hyperparameters to rerun our training job. Compare the results.
### Beginners
- Jump into SageMaker, Hyperparameter tuning jobs, create, name, IAM role, Linear Learner, Pipe mode
- Hyperparameters, Next
- Train mode, S3 location, add channel for validation data, output path, Next
- Instance type, maximum training jobs, create jobs
- Best training job, CloudWatch, Logs
- rerun the jupyter notebook with optimized hyperparameters
