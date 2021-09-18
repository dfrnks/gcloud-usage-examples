# Compute Networks

## Documentation

[Networks](https://cloud.google.com/sdk/gcloud/reference/compute/networks)

### Create new VPC

```
gcloud compute networks create securenetwork \
--subnet-mode=custom
```

### Create new Subnet
```
gcloud compute networks subnets create securenetwork-subnet \
--network=securenetwork \
--range=10.10.0.0/24 \
--purpose=PRIVATE \
--region=us-central1
```

### Create new Firewall rules to a VPC
```
gcloud compute firewall-rules create securenetwork-rdp \
--direction=INGRESS \
--network securenetwork \
--allow tcp:3389 \
--source-ranges=0.0.0.0/0 \
--target-tags=bastion-host
```

### List networks
```
gcloud compute networks subnets list \
--filter="central"
```
