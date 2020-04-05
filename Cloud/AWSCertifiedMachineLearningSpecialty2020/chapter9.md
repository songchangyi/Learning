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
- Visibility : VPC Endpoints, Network Access Control Lists, Security Groups
- Authentication : Identity and Access Management
- Access Control : Identity and Access Management
- Encryption : Key Management Service

-> AWS, VPC, NETWORK ACL, SECURITY GROUP, EC2, VPC Endpoint, S3
### VPC Endpoint
A way to access other AWS services using the AWS network without having to send traffic over the public Internet.

2 types of VPC Endpoints :
- Interface Endpoints : DNS redirection
- Gateway Endpoints : only for S3, DynamoDB, differ
### Notebook Instances
1. Internet-enabled by default
2. Can disable Internet access
3. Designed for single user
### IAM policies
Identity-based policy vs. Resource-based policy
### Encryption
- Encryption at rest : encryption key
- Encryption in transit

## 9.7 Monitor and Evaluate
### Amazon CloudWatch
1. Wide variety of metrics
2. Near real-time
3. Metrics available for 15 months
4. 2 week limit on console
### CloudTrail
1. Log API access
2. Last 90 Day's events
3. Can be kept indefinitely
4. Query with Amazon Athena

## 9.8 Exam tips

## 9.9 Implementation and Operations Lab
### Hints
Simply call the .deploy() method after training. Create an API Gateway endpoint.
### Beginner
- Navigate to SageMaker, notebook instances, open jupyter, run code
- Open Lambda, create function, name, python, IAM role
- Go to IAM, find the role, attach policies, full access
- Go back to Lambda, paste Python code, create environment variables, endpoint name
- API Gateway, Get started, Create new API, name, Create API, Actions, POST, Lambda function, Save, Test with JSON data, Actions, Deploy API
