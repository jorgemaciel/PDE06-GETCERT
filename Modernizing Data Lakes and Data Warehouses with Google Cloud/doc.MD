## Content

* Data pipelines typically fall under one of the extract load, extract load transform, or extract transform load paradigms.
* Pub Sub is the primary product for handling incoming streaming data.
* A data engineer is someone who builds data pipelines.
* BigQuery, Google Cloud's petabyte scale serverless data warehouse.
* A data engineer builds data pipelines.
* A data lake brings together data from across the enterprise into a single location.
* One option for this single location to store the raw data is to store it in a Cloud Storage bucket.
* Cloud SQL is a Google Cloud Platform service that lets you run relational databases in the cloud
    * Cloud SQL delivers high performance and scalability with up to 64 terabytes of storage capacity, 60,000 IOPS and 624 gigabytes of RAM per instance.
    * RDBMS -> Spanner e Cloud SQL
* Extract, Transform e Load -> Dataproc e Dataflow(batch pipelines)
* Cloud SQL and Cloud Spanner for relational data, and Firestore and Cloud Bigtable for NoSQL data.

## Insights:

* What if you need real-time analytics on data that arrives continuously and endlessly?
    * In that case, you might receive the data in Pub/Sub, transform it using Dataflow and stream it into BigQuery(data warehouse).
* The cleaned and transformed data are typically stored not in a data lake but in a data warehouse.
    * In other words, ETL the data and store it in a data warehouse.
 * When considering Cloud SQL, be aware that Cloud SQL is optimized to be a database
    * for transactions or writes, and BigQuery is a data warehouse optimized for reporting workloads (mostly reads).
* BigQuery is COLUMN based storage, which as you might guess, allows for really wide reporting schemas, since you can simply read individual columns out from disk.
* One of the Google Cloud products that helps manage the performance of dashboards is BigQuery BI Engine.
* One solution for data governance is the Cloud data catalog and the data loss prevention API.
    * The data catalog makes all the metadata about your datasets available to search for your users.
    * The data catalog makes all the metadata about your datasets available to search for your users.
* One solution for data governance is the Cloud data catalog and the data loss prevention API.
* One common workflow orchestration tool used by enterprises is Apache Airflow.
    * Google Cloud has a fully-managed version of Airflow called "Cloud Composer."
    * Cloud Composer helps your data engineering team orchestrate all the pieces to the data engineering
* BigQuery may be your Data Lake AND your Data Warehouse and you don’t use Cloud Storage buckets at all.
* For a multi-region bucket, the objects are replicated across regions, and for a single region bucket, the objects are replicated across zones.
    * In any case, when the object is retrieved, it is served up from the closest replica to the requester. And that is how low latency occurs.
* All data in Google Cloud is encrypted at rest and in transit.
    * The encryption is done by Google using encryption keys that we manage, Google-managed encryption keys, or GMEK.
* O-LAP systems are read-focused.
* For transactional workloads, use Cloud SQL or Firestore depending on whether you want to use SQL or No-SQL.
* Data engineers build the pipelines to populate the O-LAP system from the OLTP system.
* The default choice here is Cloud SQL, but if you require a globally distributed database, then use Cloud Spanner.
* For analytics workloads, the default choice is BigQuery.
* However, if you require high-throughput inserts, more than millions of rows per second, or if you require low latency, on the order of milliseconds, use Cloud Bigtable.
* RMDBS OLTP row-oriented tables are necessary because OLTP systems have frequent updates.
* BigQuery, however, is an O-LAP system. Column-oriented
* So you can query data in external tables or from external sources without loading it into BigQuery. These are called federated queries.
Liv290304@
* E-L, or Extract and Load, is used when data is imported as-is where the source and target have the same schema.
* E-L-T, or Extract, Load, Transform, is used when raw data will be loaded directly into the target and transformed there.
* E-T-L, or Extract, Transform, Load, is used when transformation occurs in an intermediate service before it is loaded into the target.






## Commands

gcloud storage buckets create gs://your-project-name
