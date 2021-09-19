# Dataflow

## Documentation

[Dataflow jobs](https://cloud.google.com/sdk/gcloud/reference/dataflow/jobs)

### Run job from template

```
gcloud dataflow jobs run Job's name \
--gcs-location gs://dataflow-templates-us-central1/latest/PubSub_to_BigQuery \
--region us-central1 \
--staging-location gs://qwiklabs-gcp-00-a1b761aa1d73/temp \
--parameters inputTopic=projects/pubsub-public-data/topics/taxirides-realtime,outputTableSpec=qwiklabs-gcp-00-a1b761aa1d73:taxirides.realtime
```