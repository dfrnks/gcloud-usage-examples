# Auth

### Get Access token
```
gcloud auth print-access-token 
```

### Exemplo login docker use prin-access-token
```
gcloud auth print-access-token | docker login -u oauth2accesstoken --password-stdin https://gcr.io
```

### Configure docker
```
gcloud auth configure-docker
```