# Modeling

## 6.1 Introduction

## 6.2 Concepts
### Model
Trying to figure out a mathematical formula.

Data, Algorithm, Computation, Feedback => model => generalization

### Developing a good model
1. What type of generalization are we seeking
2. Do we really need ML
3. How will ML generalization be consumed
4. What do wa have to work with
5. How can I tell if the generalization is working

|   | Supervised Learning | Unsupervised Learning | RL |
| --- | --- | --- | --- |
| Discrete | Classification | Clustering | Simulation-based Optimization |
| Continuous | Regression | Reduction of dimentionality | Autonomous Devices |

### Choosing the right approach
| Problem | Approach | Why |
| --- | --- | --- |
| Detect whether a financial transaction is fraud | Binary classification | Fraud or not |
| Predict the rate of deceleration of a car | Heuristic Approach (No ML) | Well-known formulas |
| Determine the most efficient path of surface traval for a robotic lunar rover | Simulation based RL | Figure out the optimal path |
| Determine the breed of dog in a photo | Multi-class classification | Which dog breed is most associated |

### Cascading Algorithms

### Confusion matrix
|  | True | False |
| --- | --- | --- |
| Predicted True | TP | FP |
| Predicted False | FN | TN |

## 6.3 Data Preparation
Memorization => Generalization => Intelligence

1. Randomize
2. Split
3. Kfold
4. Train
5. Test
6. Repeat

## 6.4 SageMaker Modeling
### Machanical Turk

### Options for model creation
- SageMaker console
- SageMaker SDK
- Jupyter
- Spark

### Modeling
- Most SageMaker algorithms accept csv
- For unsupervised algorithms wa can specify the absence of labels
- The optimized protobuf recordIO format is recommended : pipe mode can stream the data from S3

### Create training job API
- High-level Python library provided by Amazon SageMaker
- SDK for Python

### Hyperparameters vs parameters
- Hyperparameters : values set before the learning process
- Parameters : derived via the learning process

## 6.5 SageMaker Training
### Why GPUs
GPU are optimized for math.

ASIC GPU FPGA CPU (<- most performant - least performant ->)

ASIC FPGA GPU/CPU (<- least flexible - most flexible ->)

FPGA ASIC GPU CPU (<- most costly - least costly ->)

- GPU, CPU : training and development
- ASIC : specialized hardware with model "burned in" (months or years)
- FPGA : specialized hardware with model programmed into chip (hours or days)

### Training
Elastic Container Repository : 
- training images : CreateTrainingJob API Call
- inference images (production) : CreateModel API Call

Channel name : train or test

Tag :
- :1 stable version
- :latest

### Training process
CloudWatch
- arguments provided
- errors during training
- accuracy statistics
- timing
- Common errors

## 6.6 Exam tips

## 6.7 Modeling Lab
