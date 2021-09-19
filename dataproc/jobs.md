# Jobs
## Documentation

[DOCS](https://cloud.google.com/sdk/gcloud/reference/dataproc/jobs)

----

### Submit a job to a cluster

```
gcloud dataproc jobs submit spark --cluster example-cluster \
  --class org.apache.spark.examples.SparkPi \
  --jars file:///usr/lib/spark/examples/jars/spark-examples.jar -- 1000
```