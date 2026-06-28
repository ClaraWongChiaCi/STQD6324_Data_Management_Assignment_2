## Project Overview
This study analyzes the MovieLens 100K dataset using Apache Spark and Apache Cassandra on Google Cloud Platform. The pipeline loads raw MovieLens data, performs five analytical tasks using Spark DataFrames, stores the results in Cassandra and validates the outputs by reading the data back from Cassandra.

## System Requirement
### Hardware: Google Cloud Dataproc Cluster, Single-node cluster (n1-standard-4)
### Software:
| Software              | Version                                          |
| --------------------- | ------------------------------------------------ |
| Google Cloud Dataproc | 2.1.114-debian11                                 |
| Apache Spark          | 3.3.2                                            |
| Apache Cassandra      | cqlsh 6.1.0                                      |
| Python                | 3.10.8                                           |
| Java                  | OpenJDK 11.0.20                                  |

## Dataset: MovieLens 100K
Files used:
1. u.data - User ratings
2. u.item - Movie information
3. u.user - User demographics

## Environment Setup
1. Create a Google Cloud Dataproc cluster.
2. Upload the MovieLens files to the Dataproc instance.
3. Create the Cassandra keyspace and required tables before executing the analytical pipeline.
4. Execute the PySpark script.

## Analytical Tasks
The notebook performs the following analyses:
1. Calculate the average rating for each movie.
2. Identify the top ten movies with the highest average ratings.
3. Identify users who rated at least 50 movies and determine their favourite movie genre.
4. Identify users younger than 20 years old.
5. Identify scientists aged between 30 and 40 years old.

## Validation
After each analytical task, the processed DataFrame is written into Apache Cassandra and read back into Spark to verify successful data persistence.
The validation outputs are displayed within the notebook.

## References
MovieLens 100K Dataset. (2021, March 2). GroupLens. https://grouplens.org/datasets/movielens/100k/
