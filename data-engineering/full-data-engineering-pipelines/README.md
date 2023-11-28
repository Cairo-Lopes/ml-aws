# Full Data Engineering Pipeline Real-Time Layer


::: mermaid
graph LR;

    producers--->Kinesis_Data_Streams
    
    producers2-->Kinesis_Data_Firehose
    Kinesis_Data_Firehose-->Kinesis_Data_Streams
    Kinesis_Data_Firehose--Parquet-->Amazon_S3
    Kinesis_Data_Streams--> Lambda
    Kinesis_Data_Streams-->KinesisDataStreams 
    Kinesis_Data_Streams--> KinesisDataFirehose
    KinesisDataStreams-->EC2
    EC2-- REAL-TIME ML -->SageMaker
    KinesisDataFirehose--ORC-->S3--LOAD-->Redshift
    KinesisDataFirehose--JSON-->ElasticsearchService
:::
