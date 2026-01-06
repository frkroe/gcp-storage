# EDEM - Máster Big Data y Cloud - GCP Storage

## Overview
This repository contains **hands-on exercises** for the **EDEM – Máster Big Data y Cloud** program, focused on exploring storage options in **Google Cloud Platform (GCP)**.


The folders are structured as follows:


**[gcp_sql](./gcp_sql/)**
- [exercise_postgresql](./gcp_sql/exercise_postgresql/): Exercise to deploy a PostgreSQL instance in GCP, create tables and insert data using Mockaroo
- [exercise_alloy_db](./gcp_sql/exercise_alloy_db/): Exercise to deploy an AlloyDB instance in GCP, and compare it with the performance of PostgreSQL by running some queries
- [exercise_e2e](./gcp_sql/exercise_e2e/): Exercise to deploy an end2end architecture in GCP, using Cloud SQL, PubSub and Compute Engine instances

**[gcp_datawarehouse](./gcp_datawarehouse/)**
- [exercise_bigquery](./gcp_datawarehouse/exercise_bigquery/): Exercise to try the basic functionalities of BigQuery
- [exercise_end2end](./gcp_datawarehouse/exercise_end2end/): Exercise to deploy an end2end architecture in GCP, using Cloud SQL, PubSub, Compute Engine instances and BigQuery

**[gcp_datalake](./gcp_datalake/)**
- [exercise_gcs](./gcp_datalake/exercise_gcs/): Exercise to create a bucket and check its functionality as a object storage container used as a data_lake
- [exercise_end2end](./gcp_datalake/exercise_end2end): Exercise to deploy an end2end architecture in GCP, using Cloud SQL, PubSub, Compute Engine instances, BigQuery and GCS

**[gcp_nosql](./gcp_nosql/)**
- [exercise_stocks](./gcp_nosql/exercise_stocks/): Exercise to use BigTable to store and query stock data
- [exercise_iot](./gcp_nosql/exercise_iot/): Exercise to use an IoT application with Raspberry Pi and BigTable to query temperature data in real time.

## Prerequisites

We will use the end-to-end exercise from the [GCP Setup module](https://github.com/frkroe/gcp-setup).
