# Cluster
## Documentation

[DOCS](https://cloud.google.com/sdk/gcloud/reference/dataproc/clusters)

---


### Create a cluster

```
gcloud dataproc clusters create example-cluster --worker-boot-disk-size 500 --region us-central1
```

### Update Cluster

```
gcloud dataproc clusters update example-cluster --num-workers 4
```

### Submit a job to a cluster

```
gcloud dataproc jobs submit spark --cluster example-cluster \
  --class org.apache.spark.examples.SparkPi \
  --jars file:///usr/lib/spark/examples/jars/spark-examples.jar -- 1000
```