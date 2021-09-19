# SQL Instances

## Documentation

[DOCS](https://cloud.google.com/sdk/gcloud/reference/sql/instances)

### Create a MySQL Instance

```
gcloud sql instances create prod-wordpress-instance \
            --database-version=MYSQL_5_7 --cpu=2 --memory=4GB \
            --region=us-central1 --root-password=Password1*
```

### Create a Database
```
gcloud sql databases create wordpress --instance prod-wordpress-instance
```

### Connecta a instance
```
gcloud sql connect prod-wordpress-instance -u root
```

### Set Authorized network from connect
```
gcloud sql instances patch prod-wordpress-instance \
--authorized-networks=34.121.216.71/32,34.121.187.172/32
```