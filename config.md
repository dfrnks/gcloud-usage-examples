# Config
## Documentation

- [Config](https://cloud.google.com/sdk/gcloud/reference/config)
- [Set](https://cloud.google.com/sdk/gcloud/reference/config/set)

-----

### Get config informations

```
gcloud config list
```

### Set project

```
gcloud config set project $PROJECT_ID
```

### Set dataproc/region

```
gcloud config set dataproc/region us-central1
```

### Get PROJECT ID
```
gcloud config get-value core/project
```
