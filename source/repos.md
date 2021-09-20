
### Create a Git Repository
```
gcloud source repos create devops-repo
```

### Clone a Git Repository
```
gcloud source repos clone devops-repo
```

### Build and submit a Docker container to Google Container Registry
```
gcloud builds submit --tag gcr.io/$DEVSHELL_PROJECT_ID/devops-image:v0.1 .
```


### List all images from Google Container Registry
```
gcloud builds list --filter=SUCCESS
```
### List existing images.
gcloud container images list

### List tags and digests for the specified image.
gcloud container images list-tags gcr.io/qwiklabs-gcp-04-fd6f393f1fcf/devops-repo

### Lists information about the specified image.

gcloud container images describe gcr.io/qwiklabs-gcp-04-fd6f393f1fcf/devops-repo:0a1404e39b238458093f32f9f567108798c23745