# Usage gcloud and gutils commands

## Certifications
- [Associate Cloud Engineer](Associate%20Cloud%20Engineer.md)
- [Professional Data Engineer](Professional%20Data%20Engineer.md)
- [Professional Cloud Engineer](Professional%20Cloud%20Engineer.md)

## DOCS

- [gcloud](https://cloud.google.com/sdk/gcloud/reference)
- [gsutil](https://cloud.google.com/storage/docs/gsutil)

## Samples resources
- [AI Platform](AI%20Platform/ai-platform.md)
- [Auth](auth.md)
- [App Engine](App/appEngine.md)
- [BigQuery](BigQuery/readme.md)
- [Cloud Storage](gsutil/cloud_storage.md)
- Compute
    - [Instances](compute/instances.md)
        - [How to create a instance that have a startup-script](https://github.com/dfrnks/gcloud-usage-examples/blob/main/compute/instances.md#how-to-create-a-instance-that-have-a-startup-script)
        - [Create a instance from a specific image](https://github.com/dfrnks/gcloud-usage-examples/blob/main/compute/instances.md#create-a-instance-from-a-specific-image)
        - [Create a instance with more interfaces](https://github.com/dfrnks/gcloud-usage-examples/blob/main/compute/instances.md#create-a-instance-with-more-interfaces)
        - [Reset password windows](https://github.com/dfrnks/gcloud-usage-examples/blob/main/compute/instances.md#reset-password-windows)
    - [Networks](compute/networks.md)
- Container
    - [Cluster](container/cluster.md)
- [Config](config.md)
- Dataflow
    - [Jobs](dataflow/jobs.md)
- Dataproc
    - [Cluster](dataproc/cluster.md)
    - [Jobs](dataproc/jobs.md)
- [Info](info.md)
- [SQL](sql)
    - [Connect](sql/connect.md)
    - [Databases](sql/databases.md)
    - [Instances](sql/instances.md)
- Source
    - [Repos](source/repos.md)




----------

Apache benchmark

```
ab -n 1000 -c 10 https://qwiklabs-gcp-03-73f33bbc54d4.appspot.com/
```
