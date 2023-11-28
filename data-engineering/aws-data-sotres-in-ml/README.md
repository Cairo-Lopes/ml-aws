# Data Stores for Machine Learning

## Redshift
* Data Werehousing, SQL, analytics (OLAP - Online analytical processing)
* Load data from S3 to Redshift
* Use Redshift Spectrum to query data directly in S3 (no loading)

## RDS, Aurora
* Relation Store, SQL (OLTP - Online Transaction Processing)
* Must provision servers in advance

## DynamoDB
* NoSQL data store, serverless, provision read/write capacity
* Useful to store a machine learning model served by your application

## S3
* Object storage
* Serverless, infinite storage
* Integration with most AWS Services

## OpenSearch (previously ElasticSearch)
* Indexing of data
* Search amongst data points 
* Clickstream Analytics

## ElastiCache
* Caching mechanism
* **Not** really used for Machine Learning
