1. How did changing values onthe SparkSession property parameters affect the throughput and latency of the data?
=================================================================================================================
increasing or decreasing parameters mentioned in answer for question 2, "processedRowsPerSecond" increases or decreases

2. What were the 2-3 most efficient SparkSession property key/value pairs? Through testing multiple variations on values, how can you tell these were the most optimal? 
========================================================================================================================
Following three parameters are key.
spark.sql.shuffle.partitions                10
spark.streaming.kafka.maxRatePerPartition   10
spark.default.parallelism                   10000

Achieved upto 3.73 processedRowsPerSecond as shown bellow
2020-06-09 05:13:56 INFO  MicroBatchExecution:54 - Streaming query made progress: {
  "id" : "b8ffa682-bd87-4ea5-a012-9523eb0b8c82",
  "runId" : "7c61c67b-f31d-457d-bdf4-e0a09b581ec5",
  "name" : null,
  "timestamp" : "2020-06-09T05:13:43.154Z",
  "batchId" : 0,
  "numInputRows" : 48,
  "processedRowsPerSecond" : 3.7322136692325634,
