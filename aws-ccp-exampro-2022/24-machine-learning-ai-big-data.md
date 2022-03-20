# Machine Learning, AI, and Big Data

Artificial Intelligence (AI) = machines performing jobs that mimic human behavior

Machine Learning (ML) = machines that get better at a task without explicit programming

Deep Learning (DL) = machines that have an artificial neural network inspired by the human brain to solve complex problems

Amazon SageMaker = fully managed service to build, train, and deploy machine learning models at scale

- Apache MXNet on AWS = open-source deep learning framework
- TensorFlow on AWS = open-source machine intelligence library
- PyTorch on AWS = open-source machine learning framework

Amazon SageMaker GroundTruth = data-labelling service. Datasets are labelled by humans in order to train machine learning models

Amazon Augmented AI = human-intervention review service. When SageMaker uses ML to make a prediction, it is not confident it has the right answer -> queue up the prediction for human review

## AI and ML Services

Amazon CodeGuru = ML code analysis service. Performs code-reviews and suggests changes to improve the quality of code. Can show visual code profiles to pinpoint performance

Amazon Lex = conversation interface service. Build voice and text chatbots

Amazon Personalize = real-time recommendations service. Same tech used to make product recommendations on Amazon commercial platform

Amazon Polly = text-to-speech service. Upload text and audio file spoken by a synthesized voice is generated

Amazon Rekognition = image and video recognition service. Analyze images and videos to detect and label objects, people, celebrities

Amazon Transcribe = speech-to-text service. Upload audio, convert to text

Amazon Textract = OCR (extract text from scanned documents) service. Paper forms to electronic

Amazon Translate = neural ML translation service. Uses deep learning models to deliver more accurate and natural sounding translations

Amazon Comprehend = Natural Language Processor (NLP) service. Find relationships between text to produce insights. Looks at data and makes predictions

Amazon Forecast = time-series forecasting service. Forecast business outcomes such as product demand, resource needs, and financial performance

AWS Deep Learning AMIs = EC2s pre-installed with popular deep learning frameworks and interfaces such as TensorFlow, PyTorch, Apache MXNet, Chainer, Gluon, Horovod, and Keras

AWS Deep Learning Containers = Docker images preinstalled with popular deep learning frameworks and interfaces

AWS DeepComposer = ML-enabled musical keyboard

AWS DeepLens = video camera using deep learning

AWS DeepRacer = toy race car powered with ML to perform autonomous driving

Amazon Elastic Inference = attach low-cost GPU-powered acceleration to EC2 instances to reduce cost of running deep learning inference by up to 75%

Amazon Fraud Detector = fully managed fraud detection service. Identify potentially fraudulent online activities such as online payment fraud and creation of fake accounts

Amazon Kendra = enterprise ML search engine service. Uses natural language to suggest answers to a question instead of simple keyword matching

## Big Data and Analytics Services

Big Data = massive volumes of structured/unstructured data that is so large it is difficult to move and process using traditional database and software techniques

Amazon Athena = serverless interactive query service. Takes a bunch of CSV/JSON files in an S3 bucket and loads them into temporary SQL tables to run SQL queries. For when you want to query CSV or JSON files. Similar to Apache Presto

Amazon CloudSearch = fully managed full-text search service. When you want to add search to your website

Amazon Elasticsearch Service (ES) = managed Elasticsearch cluster. Elasticsearch is an open-source full-text search engine. More robust than CloudSearch but requires more server and operational maintenance

Amazon Elastic MapReduce (EMR) = data processing and analysis for creating reports just like Redshift, but more suited for when you need to transform unstructured data into structured data on the fly

Kinesis Data Streams = real-time streaming data service. Create producers which send data into a stream. Multiple consumers can consume data within a stream. Use for real-time analytics, click streams, ingesting data from fleet of IOT devices

Kinesis Firehose = serverless and simpler version of Kinesis Data Streams. Pay on-demand based on how much data is consumed through the stream and don't worry about underlying servers

Kinesis Data Analytics = run queries against data flowing through real-time stream so you can create reports and analytics on emerging data

Kinesis Video Streams = analyze or apply processing to real-time streaming video

Managed Kafka Service (MSK) = fully managed Apache Kafka service. Similar to Kinesis but more robust

Redshift = petabyte-size data warehouse. Used for Online Analytical Processing (OLAP). Can be expensive because data is kept "hot", meaning very complex queries can be run against a large amount of data to get results back very quickly. For generating analytics/reports from large amount of data quickly

Amazon QuickSight = business intelligence (BI) dashboard. Use it to create business dashboards to power business decisions. Little/no programming knowledge required, and connects to / ingests many different types of data sources/databases

AWS Data Pipeline = automate the movement of data. Reliably move data between compute and storage services

AWS Glue = Extract, Transform, Load (ETL) service. Move data from one location to another, then transform it before the final destination. Similar to Database Migration Service (DMS) but more robust

AWS Lake Formation = centralized, curated, secured repository for storing all of your data. A data lake is a storage repository holding vast amounts of raw data in native format until needed

AWS Data Exchange = catalog of third-party datasets. Download for free or subscribe/purchase datasets. Can be useful for learning how to work with the AWS data tools

## Amazon QuickSight

Amazon QuickSight = BI tool. Uses SPICE (super-fast, parallel, in-memory, calculation engine) to achieve blazing fast performance at scale

Amazon QuickSight ML Insights = detect anomalies, perform accurate forecasting, generate natural language narratives

Amazon QuickSight Q = ask question using natural language, on all your data, and receive answers in seconds
