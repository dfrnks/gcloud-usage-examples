# Dataflow Jobs

## Documentation

[Dataflow jobs](https://cloud.google.com/sdk/gcloud/reference/dataflow/jobs)

### Run job from template

```
gcloud dataflow jobs run "Job's name" \
    --gcs-location gs://dataflow-templates-us-central1/latest/PubSub_to_BigQuery \
    --region us-central1 \
    --staging-location gs://qwiklabs-gcp-00-a1b761aa1d73/temp \
    --parameters inputTopic=projects/pubsub-public-data/topics/taxirides-realtime,outputTableSpec=qwiklabs-gcp-00-a1b761aa1d73:taxirides.realtime
```

```
gcloud dataflow jobs run Dataflowjob \
    --gcs-location gs://dataflow-templates-us-central1/latest/GCS_Text_to_BigQuery \
    --region us-central1 \
    --staging-location gs://qwiklabs-gcp-02-2027557d101a/temp \
    --parameters javascriptTextTransformGcsPath=gs://cloud-training/gsp323/lab.js,JSONPath=gs://cloud-training/gsp323/lab.schema,javascriptTextTransformFunctionName=transform,outputTable=qwiklabs-gcp-02-2027557d101a:lab.customers,inputFilePattern=gs://cloud-training/gsp323/lab.csv,bigQueryLoadingTemporaryDirectory=gs://qwiklabs-gcp-02-2027557d101a/bigquery_temp
```
