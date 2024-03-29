# GCP Products
## Queueing Service
### Pub/Sub
- to capture the data stream
- It's convenient in many ways, such as being loosely coupled and easy to scale.

This document may give us more useful information
https://developers.cyberagent.co.jp/blog/archives/1672/

---

## Data Cleaning Service
### Dataprep
Dataprep allows users to explore data visually by transforming the file into CSV, JSON, or in a graphical table format.
- Provisioning: Fully automated provisioning of clusters
- System Integration: BigTable and BigQuery
- Ease of Use: Easy to use
- Approach: Fully managed, No ops approach
- Unique For: UI driven processing of data(cleaning/exploration/preparation)

### Dataproc
With the in-built monitoring system, you can transfer your cluster data to your applications. 
You can get quick-reports from the system and also have the feature of storing data in Google’s BigQuery.(TensorFlow is out of box)
- Provisioning: provisioning clusters is done manually
- System Integration: Apache Spark and Hadoop(managed Hadoop service)
- Ease of Use: simple, easy to use
- Approach: Hands-On, DevOps Approach
- Unique For: Data Science / ML Ecosystem

### Dataflow
ETL(Extract, transform, and load) data into multiple data warehouses at the same time.
Dataflow is considered as MapReduce replacement to handle large number of parallelization tasks.
to aggregate and extract insights in real-time in BigQuery
- Provisioning: Serverless, automatic provisioning of clusters
- System Integration: Apache Beam
- Ease of Use: Relatively difficult
- Approach: Fully managed, No Ops Approach
- Unique For: Batch and Streaming of data

### Could Data Fusion
Could Data Fusion is a managed service for quickly building data pipelines and ETL processes.
It is based on the open-source CDAP(Clinical Data Analytics Platform) project and therefore is portable to any environment.
It has a visual interface that allows you to create codeless data pipelines as required.

- Data Warehouse
- Data Migration
- Data Consolidation
- Master Data Management
- Data Consistency

<img src="https://s3.amazonaws.com/media.whizlabs.com/learn/ml35.png">

### Cloud Compose
Cloud Compose is for workflow management, not for Data preparation

---

## Data Storage Service

### BigQuery
- Allow us to do Exploratory Data Analysis and Feature Selection
- Allow us to do Model building, Training and Hyperparameter tuning but not Automatic deployment and serving

#### BigQueryML
Supported ML models by BigQueryML
- Linear Regression
- Binary Logistic Regression
- Multiclass Logistic Regression
- K-Means Clustering 
- Matrix Factorization
- Time Series
- Boosted Tree
- Deep Neural Network(DNN)
- AutoML Tables
- TensorFlow model importing
- Autoencoder

Note: ML models for non-tabular data are not supported like images, voices, videos. such as CNN

#### BigQueryML Open
BigQueryML Open is related to Open Data.



### BigTable

---

## AI Products
### Kubeflow Pipeline
an open-source platform to create and deploy ML workflow based on docker container
- Using packaged templates in Dokcer images in a k8s environment
- Manage your various tests/experiments
- Simplifying the orchestration of ML pipelines
- Reuse components and pipelines

### Vertex AI
- Train an ML without code(AutoML) and with custom
- Evaluate and Tune models
- Deploy models
- Manage prediction batch, online and monitoring
- Manage models version, workflows and retraining
- Manage the complete model maintenance cycle
- Vertex Ai integrates the following elements. 
  - Datasets: data, metadata and annotations, structured or unstructured. For all kinds of libraries.
  - Training pipelines to build an ML model
  - ML models, imported or created in the environment
  - Endpoints for inference

Datasets are suitable for all kinds of libraries. A data set is a collection of related, discrete items of related data that may be accessed individually or in combination or managed as a whole entity. A data set is organized into some type of data structure.

<img src="https://s3.amazonaws.com/media.whizlabs.com/learn/ml2-4.png">

#### Vertex Feature Store
Vertex Feature Store is a service to orginize and store ML feature s through a central store. This allows you to share and optimize ML features important for the specific environment and to reuse at any time.

All these translate into the greater speed of the creation of ML services. But these also allow minimizing problems such as processing skew, which occurs when the distribution of data in production is different from that of training, often due to errors in the organization of the features.

#### Vertex Model Monitoring
Vertext Model Monitoring is to monitor the quality of the forecasts continuously. since if input data to ML models may change over time.(this can be a serious problem, as performance will obviously degrade.)

- Skew Detection
  - for skew detection, it looks at and compares the feature's values distribution in the training data.
- Drift Detection
  - For drift detection, it looks at and compares the feature's values distribution in the production data.

### Document AI
A complete service for the automatic understanding of documents and their management,
Document AI, which integrates computer natural language processing, OCR and vision and enable us to create pre-trained templates aimed at intelligent document administration.

### Recommendation AI
It's a ready-to-use service for all the requirements. Users don't need to create models, tune, train, all that is done by the service with users' data. Also delivery is automatically done, with high-quality recommendations via web, mobile, email.

#### Features
- Select your recommendation type
- Select your objective
- Set business rules

#### Recommendation Types
- Others you may like
- Frequently Bought Together
- Recommended for you
- Recently Viewed
  - This recommendation is useless for new products
  - And this is actually not recommendation 

<img src="https://s3.amazonaws.com/media.whizlabs.com/learn/ml24.png">

### AutoML
#### AutoML Tables
AutoML tables is aimed to automatically build and deploy models on your data in the fastest way possible. It is integrated within BigQuery ML and is available i the unified Vertex AI.

#### AutoML Vision
AutoML Vision lets you train models to classify your images with your own characteristics and labels. 
So you can tailor your work as you want.

#### AutoML Vision Edge
AutoML Vision Edge lets you model deployed on edge devices such as mobile phone.

#### AutoML Video Intelligence
AutoML Video Intelligence is a service that allows you to customize the pre-trained Video intelligence GCP system according to your specific needs.

In particular, AutoML Video Intelligence Object Tracking allows you to identify and locate particular entities of interest to you with your specific tags.

### Cloud Vision AI
Vision AI uses pre-trained models trained by Google. This is powerfull, but less customizable for customized classifications.

### Video AI
Video AI manages videos, not images.
It can extract metadata from any streaming video, get insights in a far shorter time, and let trigger events
#### Cloud Video AI Intelligence AI
Cloud Video Intelligence AI is a pre-configured and ready-to-use service, therefore not configurale for specific needs.

### TensorFlow Extended
TensorFlow Extended is for deploying production ML pipelines, and it doesn't have any AutoML Services.

## Security Services
### Cloud Armor
Cloud Armor is a security service at the edge against attacks like DDoS.
### Cloud HSM(Hardware Security Module)
Cloud HSM is a service for cryptography based on special and certified hardware and software
### Network Firewall
Network Firewall rules are a set of rules that deny or block network traffic in a VPC, just network rules. VPC service-controls lets you define control at a more granular level, with context-aware access, suitable for multi-tenant environments


