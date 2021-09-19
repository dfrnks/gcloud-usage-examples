# Service Accounts


### Create a new service account

```
gcloud iam service-accounts create quickstart
```

```
gcloud iam service-accounts create my-natlang-sa \
  --display-name "my natural language service account"
```

### Create credentials to login as your service account

```
gcloud iam service-accounts keys create key.json \
    --iam-account quickstart@qwiklabs-gcp-02-b4b7dd3dde28.iam.gserviceaccount.com
```


### Activate service account with key auth file
```
gcloud auth activate-service-account --key-file key.json
```
