# Compute Instances

## Documentation

- [Instances](https://cloud.google.com/sdk/gcloud/reference/compute/instances)
- [Firewall-rules](https://cloud.google.com/sdk/gcloud/reference/compute/firewall-rules)
- [startupscript](https://cloud.google.com/compute/docs/startupscript#gcloud)

----

### Create Instance
```
gcloud compute instances create apache \
--zone=us-central1-a \
--tags http-server,https-server
```
### Add firewall rule
```
gcloud compute firewall-rules create default-allow-http \
--direction=INGRESS \
--priority=1000 \
--network=default \
--action=ALLOW \
--rules=tcp:80 \
--source-ranges=0.0.0.0/0 \
--target-tags=http-server

gcloud compute firewall-rules create default-allow-https \
--direction=INGRESS \
--priority=1000 \
--network=default \
--action=ALLOW \
--rules=tcp:443 \
--source-ranges=0.0.0.0/0 \
--target-tags=https-server
```
### Connect SSH
```
gcloud beta compute ssh \
--zone "us-central1-a" "apache" \
--project "qwiklabs-gcp-00-23808ddc93ec"
```
### Get info about instance
```
gcloud compute instances describe apache --zone us-central1-a
```
### Stop instance
```
gcloud compute instances stop apache --zone us-central1-a
```
### Start instance
```
gcloud compute instances start apache --zone us-central1-a
```
You will see the new external IP:
```
Instance internal IP is 10.128.0.2
Instance external IP is 35.188.71.54
```

### Delete instance
```
gcloud compute instances delete vm-securehost
```

## How to create a instance that have a startup-script

### From a file
```
gcloud compute instances create example-instance \
  --metadata-from-file startup-script=examples/scripts/install.sh
```

### Directly
```
gcloud compute instances create example-instance \
  --metadata startup-script='#! /bin/bash
# Installs apache and a custom homepage
  apt update
  apt -y install apache2
  cat <<EOF > /var/www/html/index.html
  <html><body><h1>Hello World</h1>
  <p>This page was created from a start up script.</p>
  </body></html>
  EOF'
```

### From a Cloud Storage Bucket file
```
gcloud compute instances create example-instance \
--zone us-central1-a \
--tags http-server \
--scopes storage-ro \
--metadata startup-script-url=gs://qwiklabs-gcp-00-e992903f04f6/install-web.sh
```

The scope parameter define that instances can have access to cloud storage


### Update instance and add Startup script
```
gcloud compute instances add-metadata example-instance \
  --metadata-from-file startup-script=examples/scripts/install.sh
```
or 
```
gcloud compute instances add-metadata example-instance \
  --metadata startup-script-url=gs://qwiklabs-gcp-00-e992903f04f6/install-web.sh
```

[Execute with the instance running](https://cloud.google.com/compute/docs/startupscript#rerunthescript)

## Create a instance from a specific image

### Get image list
```
gcloud compute images list --filter="2016"
```

### Set image and image project

```
gcloud compute instances create vm-bastionhost \
--zone=us-central1-a \
--image=windows-server-2016-dc-v20210914 \
--image-project=windows-cloud \
--tags bastion-host
```

## Create a instance with more interfaces

```
gcloud compute instances create vm-bastionhost \
--zone=us-central1-a \
--image=windows-server-2016-dc-v20210914 \
--image-project=windows-cloud \
--tags bastion-host \
--network-interface network=securenetwork,subnet=securenetwork-subnet,no-address \
--network-interface network=default,subnet=default,no-address
```

## Reset password windows
```
gcloud compute reset-windows-password vm-bastionhost --user app_admin --zone us-central1-a
```

## Create a instance from a container image

```
gcloud compute instances create-with-container instance-1 \
  --zone=us-central1-a \
  --tags=http-server \
  --image=cos-stable-89-16108-470-25 \
  --image-project=cos-cloud \
  --boot-disk-size=10GB \
  --boot-disk-type=pd-balanced \
  --boot-disk-device-name=instance-1 \
  --no-shielded-secure-boot \
  --shielded-vtpm \
  --shielded-integrity-monitoring \
  --container-image=gcr.io/qwiklabs-gcp-04-fd6f393f1fcf/devops-image:v0.1 \
  --container-restart-policy=always \
  --labels=container-vm=cos-stable-89-16108-470-25
```
