# Algorithms

## 7.1 Introduction

## 7.2 OPTIONAL - Why do we call them "Algorithms"?

## 7.3 Concepts
### Algorithm sv Heuristic
### Algorithms
- SageMaker built-in algorithm
- AWS marketplace
- build your own via Docker Image

## 7.4 Regression
### Linear Learner Algorithm
#### Minimize error
SGD (stochastic gradient descent)

1. Very flexible
2. Built-in tuning
3. Good first choice

### Factorization machines algorithm
Captures interaction between features with high dimensional sparse datasets.
#### Things to know in SageMaker
1. Considers only pair-wise features
2. CSV is not supported
3. Doesn't work for multiclass problems
4. Really needs LOTS of data
5. CPUs rock sparse data better
6. Don't perform well on dense data
#### Use cases
- High dimensional sparse data sets
- Recommendations

## 7.5 Clustering
### K-Means
#### Things to know about SageMaker K-Means
1. Expects Tabular Data
2. Define the identifying attributes
3. SageMaker uses a modified K-Means
4. CPU instances recommended
5. Training is still a thing
6. Define features and clusters

## 7.6 Classification
### KNN
1. Choose the number of neighbors
2. A lazy algorithm
3. Training data stays in memory
### Use cases
- Credit ratings
- Product recommendations

## 7.7 Image Analysis
1. Image classification : ImageNet
2. Object detection
3. Semantic segmentation
  1. Accepts PNG file
  2. Only supports GPU
  3. Can deploy on either CPU or GPU
### Use cases
- Image metadata extraction
- CV systems

## 7.8 Anomaly Detection
### Random cut forest
1. Gives an anomaly score to data points
2. Scales Well
3. Does not benefit from GPU
### Use cases
- quality control
- fraud detection
### IP insights
1. Ingests entity/IP address pairs
2. Returns inferences via a score
3. Uses NN
4. GPUs for training
5. CPUs for inference
### Use cases
- Tiered authentication models
- Fraud detection

## 7.9 Text Analytics
### LDA (latent dirichlet allocation)
- article recommendation
- musical influence modeling
### NTM (neural topic model)
### Seq2seq
1. Steps consist of embedding, encoding and decoding
2. Initialized with pre-trained word libraries
3. Only GPU
### Use cases
- Language translations
- Speech to text
### Blazing text
Modes :
  - Word2Vec
  - Text classification

1. Expects single pre-processed text file
2. Highly scalable
3. 20X faster than fasttext
### Use cases
- Sentiment analysis (Amazon Comprehend)
- Document classification (Amazon Macie)
### Object2Vec
1. Expects pairs of things
2. Feature engineering
3. Training data required
### Use cases
- Movie rating prediction
- Document classification

## 7.10 Reinforcement Learning
Positive vs Negative

Find the path to the greatest reward.
### MDP (Markov decision process)
### Use cases
- Autonomous vehicles
- Intelligent HVAC Control

## 7.11 Forecasting
### DeepAR
point forecast vs probabilistic forecast
1. Support for various time series
2. More time series is better
3. At least 300 observations
4. Must supply some hyperparameters
5. Automatic Evaluation of the model
### Use cases
- forecasting new product performance
- predict labor needs for special events

## 7.12 Ensemble Learning
### XGBoost
1. Accepts CSV and libsvm for training and inference
2. Only CPU
3. Recommend lots of memory
4. Spark integration : Spark SDK
### Use cases
- Ranking
- Fraud detection

## 7.13 Exam Tips

## 7.14 Algorithms Lab
- make sure the data is available, create and upload a bucket if necessary
- go to SageMaker, start our notebook instance, open jupyter
