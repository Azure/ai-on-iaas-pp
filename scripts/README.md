# Tutorials for Operationalization
These tutorials are categorized by scenario and thus often contains multiple Azure components. 

## Experimentation & Model Development
When experimenting and developing a model, data scientists want to optimize their own time and reduce the friction of installing software, provision infrastructure, and moving data. 

## Operationalization & Model Deployment <a name="operationalization-&-model-deployment"></a>
When deploying your model and operationalizing your AI solution in Azure, it can confusing to choose from Azure's vast set of resources, services, and tools. 

### [0] Using Azure Functions to provision a DSVM for periodic batch scoring
Azure functions can be used with the DSVM to automate your batch scoring jobs.

- [0_0] Deploy your DSVM from Azure Functions
- [0_1] Automate your Azure Function to read & write data from Blob Storage

Please see this architecture [link] reference for a full end-to-end batch scoring sceanrio with Spark on AZTK.

### [1] Deploy your Spark model to AZTK for batch processing/training/scoring
AZTK allows you to deploy, manage and run Apache Spark clusters in a simple and cost-efficient way. 

AZTK has two primary _modes_: interactive mode and job-submission mode. The difference between these two modes is that interactive mode lets users manage their Spark clusters while job-submission mode will automatically provision/deprovision your cluster based on the job. 

Unless otherwise stated, this set of tutorials will use AZTK's interactive mode.

- [[1_0] Deploy a CPU or GPU enabled AZTK Spark cluster from your local machine](/tutorials_operationalization/1_0.md)
- [1_1] Setting up your AZTK Spark cluster to read/write data from Azure Blob
- [1_2] Use AZTK's run jupyter notebooks and the Spark UI
- [1_3] Use Azure Functions to automate your AZTK batch job using AZTK's job-submission mode
- [1_4] [Enterprise-Ready] Deploy your AZTK clusters in a Virtual Network

Please see this architecture [link] reference for a full end-to-end batch scoring sceanrio with Spark on AZTK.

For additional details about AZTK, please visit the [AZTK repo](https://www.github.com/azure/aztk).

### [2] Deploy your DL model to BatchAI for batch scoring
BatchAI allows you to deploy, manage and run compute intensive deep learning jobs in a cost-efficient way.

- [2_0] Deploy a CPU or GPU enabled BatchAI cluster from your local machine
- [2_1] Mount a fileshare to your BatchAI cluster
- [2_2] Set up Tensorboard on BatchAI for monitoring your run history
- [2_3] Use Azure Functions to automate your DL jobs 
- [2_4] Use Azure Data Factory to automate your DL jobs

Please see this architecture [link] reference for a full end-to-end batch scoring sceanrio with Tensorflow on BatchAI.

For an End-to-End Anomaly Detection scenario using Azure Batch AI, please refer to this: https://github.com/saidbleik/batchai_mm_ad

### [3] Deploy your DL model to AKS for real-time request/response workloads
Deploying to AKS is most suited for real-time request/response workloads. 

See this repo (https://github.com/Microsoft/AKSDeploymentTutorial) to talk through the following steps:
- Model development where we load the pretrained model and test it by using it to score images
- Developing the interface our Flask app will use to load and call the model
- Building the Docker Image with our Flask REST API and model
- Testing our Docker image before deployment
- Creating our Kubernetes cluster and deploying our application to it
- Testing the deployed model
- Testing the throughput of our model
