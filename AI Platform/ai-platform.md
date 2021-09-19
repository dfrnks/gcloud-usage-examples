
# Tensor Flow

## Documentation

[Doc](https://cloud.google.com/sdk/gcloud/reference/ai-platform)

### Example

[Training Data Analyst](https://github.com/GoogleCloudPlatform/training-data-analyst)

```
git clone https://github.com/GoogleCloudPlatform/training-data-analyst
```


[Example](https://github.com/GoogleCloudPlatform/training-data-analyst/blob/master/self-paced-labs/ai-platform-qwikstart/ai_platform_qwik_start.ipynb)

## Local

### Train model local
```
gcloud ai-platform local train \
    --module-name trainer.task \
    --package-path trainer/ \
    --job-dir $MODEL_DIR \
    -- \
    --train-files $TRAIN_DATA \
    --eval-files $EVAL_DATA \
    --train-steps 1000 \
    --eval-steps 100
```

### Predict local

```
gcloud ai-platform local predict \
    --model-dir output/keras_export/ \
    --json-instances ./test.json
```

## Jobs

### Train model with GCP jobs

```
JOB_ID=census_$(date -u +%y%m%d_%H%M%S)
OUTPUT_PATH=gs://$BUCKET_NAME/$JOB_ID

gcloud ai-platform jobs submit training $JOB_ID \
    --job-dir $OUTPUT_PATH \
    --runtime-version $TFVERSION \
    --python-version $PYTHONVERSION \
    --module-name trainer.task \
    --package-path trainer/ \
    --region $REGION \
    -- \
    --train-files $TRAIN_DATA \
    --eval-files $EVAL_DATA \
    --train-steps 1000 \
    --eval-steps 100 \
    --verbosity DEBUG
```

### Describe jobs

```
gcloud ai-platform jobs describe census_210919_135835
```

### Get jobs logs 

```
gcloud ai-platform jobs stream-logs census_210919_135835
```

### Create model into AI Platform

```
OUTPUT_PATH=gs://$BUCKET_NAME/$JOB_ID
MODEL_BINARIES=$OUTPUT_PATH/keras_export/

gcloud ai-platform versions create v1 \
    --model $MODEL_NAME \
    --origin $MODEL_BINARIES \
    --runtime-version $TFVERSION \
    --python-version $PYTHONVERSION \
    --region=global
```

### List your models

```
gcloud ai-platform models list
```

### Predict

```
gcloud ai-platform predict \
    --model $MODEL_NAME \
    --version v1 \
    --json-instances ./test.json \
    --region global
```