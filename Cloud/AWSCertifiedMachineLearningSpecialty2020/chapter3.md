# Streaming Data Collection

## 3.2 Concepts
### Early data collection
- Census of Egypt

### Data source
- Kaggle
- UCI ML Repository
- AWS
- Google's BigQuery

### Load data into AWS
- Console via S3
- Using SDKs
- CLI (command line interface)

### Steaming data
Use Kinesis (a family of tools) to stream data into AWS

### The Kinesis family
- Kinesis Data Streams
- Kinesis Data Firehose
- Kinesis Video Streams
- Kinesis Data Analytics

## 3.3 Kinesis Data Streams
- Getting data from data producers
- Transfer, Load or Stream data
- Data Consumers (processing tools) : EC2, Lambda, Kinesis Data Analytics, EMR
- Storage and Analyzation : S3, DynamoDB, Redshift, BI

### Shard
- Partition Key (unique)
- Sequence
- Data

From 1 to 500 shards by default, but can request more shards if needed

- Each shard consists of a sequence of data records. These can be ingested at 1000 records/second.
- Default limit of 500 shards, but you can request increase to unlimited shards.
- A data record is the unit of data captured.
  - sequence number
  - partition key
  - data blob (payload, up to 1MB)
- Transient Data Store - retention period for the data records are 24 hours ti 7 days.

### Interaction with Kinesis Data Streams
1. Kinesis Producer Library (KPL) : easy to use, write to a Kinesis Data Stream
2. Kinesis Client Library (KCL) : consume and process data from Kinesis Data Stream
3. Kinesis API (AWS SDK) : low level API operations to send records to a Kinesis Data Stream

### KPL vs API
1. KPL
  - a layer of abstraction specifically for ingesting data
  - automatic and configurable retry mechanism
  - additional processing delay for higher packing efficiencies and better performance
  - Java wrapper
2. API
  - Low-level API calls
  - Stream creations, resharding and putting and getting records are manually handled
  - No delays in processing
  - Any AWS SDK

### When to use
- needs to be processed by consumers
- real time analytics
- feed into other services in real time
- some action needs to occur on your data
- storing data is optional
- data retention is important

### Use cases
- process and evaluate logs immediately
- real-time data analytics

## 3.4 Kinesis Firehose
No shards, used for streaming data into some storage or data repository, like S3.

### When to use
- easily collect streaming data
- processing is optional
- final destination is S3 (or other data store)
- data retention is not important

### Use cases
- Stream and store data from devices
- Create ETL jobs (Lambda) on streaming data

## 3.5 Kinesis Video Streams
Stream videos (images/audios/radar) into the AWS cloud.

Fragments and frames from a Kinesis Video Streams to view process and analyze it.

Write consumer applications

### When to use
- process real-time streaming video data
- batch-process and store streaming video
- feed streaming data into other AWS services

## 3.6 Kinesis Data Analytics
Read and process streaming data in real time.
- Streaming input
- Kinesis Data Analytics
- Storage and Visuals, S3, Redshift, BI

### When to use
- run SQL queries on streaming data
- construct applications that provide insight on your data
- create metrics, dashboards, monitoring, notifications and alarms
- output query results into S3 (or others)

### Use cases
- Responsive real-time analytics
- Stream ETL jobs

## 3.7 Exam Tips
### Loading data into AWS
### The Kinesis Family

## 3.8 Streaming Data Collection Lab
