# Cluster

### Create a new cluster
```
gcloud container clusters create echo-cluster \
--zone us-central1-a
--machine-type=n1-standard-2 \
--num-nodes=2
```

### Login into cluster
```
gcloud container clusters get-credentials echo-cluster --zone us-central1-a
```