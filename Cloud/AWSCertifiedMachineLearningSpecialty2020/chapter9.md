# Implementation and Operations

## 9.1 Introduction

## 9.2 Concepts
### OpenAI Gym
gym.openai.com
### Two types of usage
|  | Offline usage | Online usage |
| --- | --- | --- |
| What | Make inferences on datasets in batch and return results as a set | Make inferences on demand as the model is called and return results immediately |
| Why | Entire dataset is needed | Need instance response |
| When | Predictive models with large historic dataset inputs | Real time detection |
### Types of deployments
- Big Bang : replace the old system with the new one
- Phased rollout : gradually replace the old one
- Parallel adoption : multi systems on the same time
### CI, CD and more CD
- Continuous Integration : merge code changes as frequently as possible with automated testing
- Continuous Delivery : automate release process to the point you can deploy at the click of a button
- Continuous Deployment : each code change is released to production with non human intervention required
### Typical development lifecycle
1. Get latest from repo
2. Make changes
3. Unit testing
4. Commit to repo
5. Integration testing
6. Acceptance testing
7. Deploy to production
8. Smoke testing

## 9.3 AI Developer Services
### AWS AI Stack
- AI services
  - No ML knowledge required
  - Scalable and robust
  - Redundant and fault tolerant
  - Pay per use
  - REST API and SDK
  - AWS Comprehend : NLP service
  - Amazon Forecast : time-series with other variables
  - Amazon Lex : chatbot
  - Amazon Personalize : recommender system
  - Amazon Polly : text-to-speech
  - Amazon Rekognition : image and video analysis
  - Amazon Textract : extract text
  - Amazon Transcribe : speech-to-text
  - Amazon Translate : machine translation

## 9.4 Amazon SageMaker Deployments
### SageMaker
- Ground Truth
- Notebook
- Training
- Inference
### 2 Deployment types
|  | Offline usage | Online usage |
| --- | --- | --- |
| Usage | Asynchronous or batch | Synchronous or Real-time |
| When | Generate predictions for a whole set of data all at once | Generate low-latency predictions |
| Method | SageMaker Batch Transform | SageMaker Hosting Services |
| Input | Varies depending on algorithm | Varies depending on algorithm |
| Output | Varies depending on algorithm | JSON string |
### SageMaker hosting services
1. Create a model
2. Create an endpoint configuration : initial weight
3. Create an endpoint
### Inference pipelines
### SageMaker Neo
A compiler and runtime component that allow us to optimize models for specific architectures.
### Elastic inference (EI)
Speeds up throughput and decreases latency.
### Automatic scaling
Minimum, Maximum, Target metric, Cool down (buffer to stabilize before adding or removing instances)
### High availability

## 9.5 Other ML Deployment Options
- Amazon elastic container service
- EC2
- Amazon elastic map reduce
- On-premises
### Deploying with ECS
deploy that ourselves
### EC2
VPC, API Gateway
### EMR
### Locally
model.tar.gz

## 9.6 Security
