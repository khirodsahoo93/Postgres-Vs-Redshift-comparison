# Postgres-Vs-Redshift-comparison

## Introduction :

In the era of Big data, analysts seek to perform quick analytics and often sampling of data is done to estimate results for decision making. We wished to establish whether the use of these chosen samples using random sampling of a large dataset can be used to obtain reasonably accurate answers to the aggregation queries (GROUP-BY), in significantly shorter periods of time. Furthermore, we would like to know how the samples compare with the entire dataset in order to provide an adequate level of accuracy, and how much faster we can expect those answers to arrive.  We used Approximate Query Processing(AQP) to estimate the results of two queries. AQP in database context is considered as an alternative to approximate answers that could have been obtained by running queries on a full dataset. It is designed primarily for aggregation like count, sum, average.


## Research questions:

- Are random sampling execution timings of both the systems similar?
- How comparable are the results from Approximate Query Processing with full vs sampled dataset in both the systems?
- How similar are the overall query performance in both the systems?

In order to answer the second question, we are comparing differences in Approximate Query Processing (AQP) between Redshift and Postgres using 50% of the full dataset and comparing those results to query results on the full IMDB dataset. There were 5 steps in our methodology, as summarized in below chart:

![1](https://github.com/khirodsahoo93/Postgres-Vs-Redshift-comparison/blob/main/516%20project.png)
