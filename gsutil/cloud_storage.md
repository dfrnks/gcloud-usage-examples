# Cloud Storage

Cloud Storage has many object management features like retention policy, versioning, lifecycle management.

Storage Classes

- Standard Storage - Best for hot data and stored for only brief periods of time - None.
- Nearline Storage - A low-cost storage service for data you plan to read or modify once per month - 30 days.
- Coldline Storage - A very low-cost storage service for data you plan to read or modify once a quarter - 90 days.
- Archive Storage - The lowest-cost storage service for data archiving, only use for backup and disaster recovery - 365 days.

## Documentation

[gsutil](https://cloud.google.com/storage/docs/gsutil)

----

### Create a new bucket
```
gsutil mb gs://qwiklabs-gcp-00-e992903f04f6
```

### Create a script file 
```
cat >> install-web.sh << EOF
#!/bin/bash
apt-get update
apt-get install -y apache2
EOF
```

### Upload a file to a bucket
```
gsutil cp install-web.sh gs://qwiklabs-gcp-00-e992903f04f6
```

### Lit the files from a bucket
```
gsutil ls gs://qwiklabs-gcp-00-e992903f04f6
```
Result:
```
gs://qwiklabs-gcp-00-e992903f04f6/install-web.sh
```
