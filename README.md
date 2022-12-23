# Postgres-Vs-Redshift-comparison


Research questions:
Are random sampling execution timings of both the systems similar?
How comparable are the results from Approximate Query Processing with full vs sampled dataset in both the systems?
How similar are the overall query performance in both the systems?

In order to answer the second question, we are comparing differences in Approximate Query Processing (AQP) between Redshift and Postgres using 50% of the full dataset and comparing those results to query results on the full IMDB dataset. There were 5 steps in our methodology, as summarized in below chart:



Figure 3
!(https://github.com/khirodsahoo93/Postgres-Vs-Redshift-comparison/blob/main/516%20project.png)
