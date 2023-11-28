# DMS - Database Migration Services

* Quickly and securely migrate databases to AWS, resilient, self healing
* The source database remains available during the migration
* Supports:
    - Homogeneous migrations: ex Oracle to Oracle
    - Heterogeneous migrations: ex Microsoft SQL Server to Aurora
* Continuous Data Replication using CDC
* You must create an EC2 instance to perform the replication tasks

## AWS DMS vs Glue

* **Glue**:
    - Glue ETL: Run Apache Spark code, Scala or Python based, focus on the ETL
    - Glue ETL: Do not worry about configuring or managing the resource
    - Data Catalog to make the data available to Athena or Redshift Spectrum
* **AWS DMS**:
    * Continuous Data Replication
    * No data transformation
    * Once the data is in AWS, you can use Glue to transform it
    