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
