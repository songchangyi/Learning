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

**Note**: Deployment to a local service, a compute instance, or an ACI is a good choice for testing and development. For production, you should deploy to a target that meets the specific performance, scalability, and security needs of your application architecture.

1. Register a trained model
After successfully training a model, you must register it in your Azure Machine Learning workspace.

To register a model from a local file, you can use the register method of the Model object as shown here:

```
from azureml.core import Model

classification_model = Model.register(workspace=ws,
                       model_name='classification_model',
                       model_path='model.pkl', # local path
                       description='A classification model')
```

Alternatively, if you have a reference to the Run used to train the model, you can use its register_model method as shown here:

```
run.register_model( model_name='classification_model',
                    model_path='outputs/model.pkl', # run outputs path
                    description='A classification model')
```

2. Define an Inference Configuration

The model will be deployed as a service that consist of:
- A script to load the model and return predictions for submitted data.
- An environment in which the script will be run.

#### Creating an Entry Script
Typically, you use the init function to load the model from the model registry, and use the run function to generate predictions from the input data. The following example script shows this pattern:

```
import json
import joblib
import numpy as np
from azureml.core.model import Model

# Called when the service is loaded
def init():
    global model
    # Get the path to the registered model file and load it
    model_path = Model.get_model_path('classification_model')
    model = joblib.load(model_path)

# Called when a request is received
def run(raw_data):
    # Get the input data as a numpy array
    data = np.array(json.loads(raw_data)['data'])
    # Get a prediction from the model
    predictions = model.predict(data)
    # Return the predictions as any JSON serializable format
    return predictions.tolist()
```

#### Creating an Environment
Your service requires a Python environment in which to run the entry script, which you can configure using Conda configuration file. An easy way to create this file is to use a CondaDependencies class to create a default environment (which includes the azureml-defaults package and commonly-used packages like numpy and pandas), add any other required packages, and then serialize the environment to a string and save it:

```
from azureml.core.conda_dependencies import CondaDependencies

# Add the dependencies for your model
myenv = CondaDependencies()
myenv.add_conda_package("scikit-learn")

# Save the environment config as a .yml file
env_file = 'service_files/env.yml'
with open(env_file,"w") as f:
    f.write(myenv.serialize_to_string())
print("Saved dependency info in", env_file)
```

#### Combining the Script and Environment in an InferenceConfig
After creating the entry script and environment configuration file, you can combine them in an InferenceConfig for the service like this:

```
from azureml.core.model import InferenceConfig

classifier_inference_config = InferenceConfig(runtime= "python",
                                              source_directory = 'service_files',
                                              entry_script="score.py",
                                              conda_file="env.yml")
```

3. Define a Deployment Configuration
Now that you have the entry script and environment, you need to configure the compute to which the service will be deployed. If you are deploying to an AKS cluster, you must create the cluster and a compute target for it before deploying:

```
from azureml.core.compute import ComputeTarget, AksCompute

cluster_name = 'aks-cluster'
compute_config = AksCompute.provisioning_configuration(location='eastus')
production_cluster = ComputeTarget.create(ws, cluster_name, compute_config)
production_cluster.wait_for_completion(show_output=True)
```

With the compute target created, you can now define the deployment configuration, which sets the target-specific compute specification for the containerized deployment:

```
from azureml.core.webservice import AksWebservice

classifier_deploy_config = AksWebservice.deploy_configuration(cpu_cores = 1,
                                                              memory_gb = 1)
```

The code to configure an ACI deployment is similar, except that you do not need to explicitly create an ACI compute target, and you must use the deploy_configuration class from the azureml.core.webservice.AciWebservice namespace. Similarly, you can use the azureml.core.webservice.LocalWebservice namespace to configure a local Docker-based service.

**Note**: To deploy a model to an Azure Function, you do not need to create a deployment configuration. Instead, you need to package the model based on the type of function trigger you want to use.

4. Deploy the Model
```
from azureml.core.model import Model

service = Model.deploy(workspace=ws,
                       name = 'classifier-service',
                       models = [classification_model],
                       inference_config = classifier_inference_config,
                       deployment_config = classifier_deploy_config,
                       deployment_target = production_cluster)
service.wait_for_deployment(show_output = True)
```

For ACI or local services, you can omit the deployment_target parameter (or set it to None).

### 7.1.3 Consuming a Real-Time Inferencing Service
After deploying a real-time service, you can consume it from client applications to predict labels for new data cases.

#### Using the Azure Machine Learning SDK
```
import json

# An array of new data cases
x_new = [[0.1,2.3,4.1,2.0],
         [0.2,1.8,3.9,2.1]]

# Convert the array to a serializable list in a JSON document
json_data = json.dumps({"data": x_new})

# Call the web service, passing the input data
response = service.run(input_data = json_data)

# Get the predictions
predictions = json.loads(response)

# Print the predicted class for each case.
for i in range(len(x_new)):
    print (x_new[i]), predictions[i] )
```

#### Using a REST Endpoint
With the endpoint known, you can use an HTTP POST request with JSON data to call the service. The following example shows how to do this using Python:

```
import requests
import json

# An array of new data cases
x_new = [[0.1,2.3,4.1,2.0],
         [0.2,1.8,3.9,2.1]]

# Convert the array to a serializable list in a JSON document
json_data = json.dumps({"data": x_new})

# Set the content type in the request headers
request_headers = { 'Content-Type':'application/json' }

# Call the service
response = requests.post(url = endpoint,
                         data = json_data,
                         headers = request_headers)

# Get the predictions from the JSON response
predictions = json.loads(response.json())

# Print the predicted class for each case.
for i in range(len(x_new)):
    print (x_new[i]), predictions[i] )
```

#### Authentication
In production, you will likely want to restrict access to your services by applying authentication. There are two kinds of authentication you can use:
- Key: Requests are authenticated by specifying the key associated with the service.
- Token: Requests are authenticated by providing a JSON Web Token (JWT).

Assuming you have an authenticated session established with the workspace, you can retrieve the keys for a service by using the get_keys method of the WebService object associated with the service:

```
primary_key, secondary_key = service.get_keys()
```

For token-based authentication, your client application needs to use service-principal authentication to verify its identity through Azure Active Directory (Azure AD) and call the get_token method of the service to retrieve a time-limited token.

```
import requests
import json

# An array of new data cases
x_new = [[0.1,2.3,4.1,2.0],
         [0.2,1.8,3.9,2.1]]

# Convert the array to a serializable list in a JSON document
json_data = json.dumps({"data": x_new})

# Set the content type in the request headers
request_headers = { "Content-Type":"application/json",
                    "Authorization":"Bearer " + key_or_token }

# Call the service
response = requests.post(url = endpoint,
                         data = json_data,
                         headers = request_headers)

# Get the predictions from the JSON response
predictions = json.loads(response.json())

# Print the predicted class for each case.
for i in range(len(x_new)):
    print (x_new[i]), predictions[i] )
```

### 7.1.4 Troubleshooting a Real-Time Inferencing Service
Troubleshooting a failed deployment, or an error when consuming a deployed service can be complex.

#### Check the Service State
```
from azureml.core.webservice import AksWebservice

# Get the deployed service
service = AksWebservice(name='classifier-service', workspace=ws)

# Check its state
print(service.state)
```

#### Review Service Logs
```
print(service.get_logs())
```

#### Deploy to a Local Container
Deployment and runtime errors can be easier to diagnose by deploying the service as a container in a local Docker instance, like this:

```
from azureml.core.webservice import LocalWebservice

deployment_config = LocalWebservice.deploy_configuration(port=8890)
service = Model.deploy(ws, 'test-svc', [model], inference_config, deployment_config)
```

You can then test the locally deployed service using the SDK:

```
print(service.run(input_data = json_data))
```

You can then troubleshoot runtime issues by making changes to the scoring file that is referenced in the inference configuration, and reloading the service without redeploying it (something you can only do with a local service):

```
service.reload()
print(service.run(input_data = json_data))
```

## 7.2 Batch Inferencing

### 7.2.1 What is Batch Inferencing?
In machine learning, batch inferencing is used to apply a predictive model to multiple cases asynchronously - usually writing the results to a file or database.

In Azure Machine Learning, you can implement batch inferencing solutions by creating a pipeline that includes a steps to read the input data, load a registered model, predict labels, and write the results as its output.

### 7.2.2 Creating a Batch Inferencing pipeling
To create a batch inferencing pipeline, perform the following tasks:

1. Register the Model
Just as with a real-time inferencing service, to use a trained model in a batch inferencing pipeline, you must register it in your Azure Machine Learning workspace.

2. Create an Scoring Script
Just like a real-time inferencing service, a batch inferencing service requires a scoring script to load the model and use it to predict new values.

3. Create a Pipeline with a ParallelRunStep
Azure Machine Learning provides a type of pipeline step specifically for performing parallel batch inferencing. Using the ParallelRunStep class, you can read batches of files from a File dataset and write the processing output to a PipelinePata reference. Additionally, you can set the output_action setting for the step to “append_row”, which will ensure that all instances of the step being run in parallel will collate their results to a single output file named parallel_run_step.txt:

```
from azureml.contrib.pipeline.steps import ParallelRunConfig, ParallelRunStep
from azureml.pipeline.core import PipelineData
from azureml.pipeline.core import Pipeline

# Get the batch dataset for input
batch_data_set = ws.datasets('batch-data')

# Set the output location
default_ds = ws.get_default_datastore()
output_dir = PipelineData(name='inferences',
                          datastore=default_ds,
                          output_path_on_compute='results')

# Get the model
model = ws.models['classification_model']

# Define the parallel run step step configuration
parallel_run_config = ParallelRunConfig(
    source_directory='batch_scripts',
    entry_script="batch_scoring_script.py",
    mini_batch_size="5",
    error_threshold=10,
    output_action="append_row",
    environment=batch_env,
    compute_target=aml_cluster,
    node_count=4)

# Create the parallel run step
parallelrun_step = ParallelRunStep(
    name='batch-score',
    models=[model],
    parallel_run_config=parallel_run_config,
    inputs=[batch_data_set.as_named_input('batch_data')],
    output=output_dir,
    arguments=[],
    allow_reuse=True
)
# Create the pipeline
pipeline = Pipeline(workspace=ws, steps=[parallelrun_step])
```

4. Run the pipeline and Retrieve the Step Output
After your pipeline has been defined, you can run it and wait for it to complete. Then you can retrieve the parallel_run_step.txt file from the output of the step to view the results.

```
from azureml.core import Experiment

# Run the pipeline as an experiment
pipeline_run = Experiment(ws, 'batch_prediction_pipeline').submit(pipeline)
pipeline_run.wait_for_completion(show_output=True)

# Get the outputs from the first (and only) step
prediction_run = next(pipeline_run.get_children())
prediction_output = prediction_run.get_output_data('inferences')
prediction_output.download(local_path='results')

# Find the parallel_run_step.txt file
for root, dirs, files in os.walk('results'):
    for file in files:
        if file.endswith('parallel_run_step.txt'):
            result_file = os.path.join(root,file)

# Load and display the results
df = pd.read_csv(result_file, delimiter=":", header=None)
df.columns = ["File", "Prediction"]
print(df)
```

### 7.2.3 Publishing a Batch Inferencing Service
Just like any pipeline, you can publish a batch inferencing pipeline as a REST service:

```
published_pipeline = pipeline_run.publish_pipeline(name='Batch_Prediction_Pipeline',
                                                   description='Batch pipeline',
                                                   version='1.0')
rest_endpoint = published_pipeline.endpoint
```

Once published, you can use the service endpoint to initiate a batch inferencing job:

```
import requests

response = requests.post(rest_endpoint,
                         headers=auth_header,
                         json={"ExperimentName": "Batch_Prediction"})
run_id = response.json()["Id"]
```

You can also schedule the published pipeline to have it run automatically:

```
from azureml.pipeline.core import ScheduleRecurrence, Schedule

weekly = ScheduleRecurrence(frequency='Week', interval=1)
pipeline_schedule = Schedule.create(ws, name='Weekly Predictions',
                                        description='batch inferencing',
                                        pipeline_id=published_pipeline.id,
                                        experiment_name='Batch_Prediction',
                                        recurrence=weekly)
```
