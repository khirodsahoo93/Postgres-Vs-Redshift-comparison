# Postgres-Vs-Redshift-comparison

## Introduction :

In the era of Big data, analysts seek to perform quick analytics and often sampling of data is done to estimate results for decision making. We wished to establish whether the use of these chosen samples using random sampling of a large dataset can be used to obtain reasonably accurate answers to the aggregation queries (GROUP-BY), in significantly shorter periods of time. Furthermore, we would like to know how the samples compare with the entire dataset in order to provide an adequate level of accuracy, and how much faster we can expect those answers to arrive.  We used Approximate Query Processing(AQP) to estimate the results of two queries. AQP in database context is considered as an alternative to approximate answers that could have been obtained by running queries on a full dataset. It is designed primarily for aggregation like count, sum, average.


## Research questions:

- Are random sampling execution timings of both the systems similar?
- How comparable are the results from Approximate Query Processing with full vs sampled dataset in both the systems?
- How similar are the overall query performance in both the systems?

In order to answer the second question, we are comparing differences in Approximate Query Processing (AQP) between Redshift and Postgres using 50% of the full dataset and comparing those results to query results on the full IMDB dataset. There were 5 steps in our methodology, as summarized in below chart:

![1](https://github.com/khirodsahoo93/Postgres-Vs-Redshift-comparison/blob/main/516%20project.png)

### Data ingestion :

For running queries on Postgres, we used the Dbeaver Postgres client to load complete data [1] from an sql dump file. Since we couldn’t identify a way to create a database from a dump file on the Redshift server, we resorted to exporting the Postgres tables to CSV files which were then loaded into AWS S3 buckets. We created the corresponding database on Redshift spectrum from these uploaded CSV files and ran the below queries. 

### SQL Queries :

1. Sampling queries: 
Random sampling was used to create a sample dataset with 50% and 30% of the complete data in cast_info and movie_info tables, which were the largest tables in terms of size of CSV files respectively (Cast Info: 1.2 GB, ~36 million rows, 6 columns & Movie Info: 900MB, ~14 million rows, 5 columns). These were as below.
create table cast_info_s5 as select * from cast_info ci order by RANDOM() limit 36244344/2
create table movie_info_s5 as select * from movie_info order by RANDOM() limit 14835720/2

2. GROUP BY queries for Approximate Query Processing:
We modified two of the JOB queries [2] to include aggregations using the GROUP BY SQL command [3]. 

3. JOB queries: For understanding the overall performance differences between both systems, we ran 6 standard queries from the JOB benchmark, without any modifications.


For results, please view the full report:

()


