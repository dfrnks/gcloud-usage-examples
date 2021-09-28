# Pubsub

## Topics

### Create a new Topic
````
gcloud pubsub topics create myTopic
````

### List topics
````
gcloud pubsub topics list
````

### Delete topics
````
gcloud pubsub topics delete myTopic
````

### Publish into a Topic
````
gcloud pubsub topics publish myTopic --message "Publisher thinks Pub/Sub is awesome"
````

## Subscriptions

### Create subscriptions
````
gcloud pubsub subscriptions create --topic myTopic mySubscription
````

### List subscriptions
````
gcloud pubsub topics list-subscriptions myTopic
````

### Delete subscriptions
````
gcloud pubsub subscriptions delete mySubscription
````

### Read a subscriptions
````
gcloud pubsub subscriptions pull mySubscription --auto-ack --limit=3
````





