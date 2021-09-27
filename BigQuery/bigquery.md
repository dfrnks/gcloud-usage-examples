# Big Query

Is a petabyte-scale fully-managed data warehouse

- Serverless
- Flexible pricing model
- Data encryption and security
- Geospatial data types e functions
- Foundation for BI and AI
- You can write ML models directly in BigQuery using SQl
- Support arrays and structs as data types



### Create a Dataset

```
bq mk taxirides
```

### Create a table
```
bq mk --time_partitioning_field timestamp \
--schema ride_id:string,point_idx:integer,latitude:float,longitude:float,timestamp:timestamp,meter_reading:float,meter_increment:float,ride_status:string,passenger_count:integer \
-t taxirides.realtime
```

## BigQuery ML

- Explore the data
- Create a ML Traininig dataset
- Select a model to train
- Train, evaluate and predict
- Improve ML Model performance
- Visualize results

How BigQuery ML Works

- Label = alias a column as ‘label’ or specify column in OPTIONS using input_label_cols
- Feature = passed through to the model as part of your SQL `SELECT statement SELECT * FROM ML.FEATURE_INFO(MODEL mydataset.mymodel)`
- Model = an object created in BigQuery that resides in your BigQuery dataset
- Model Types = Linear Regression, Logistic Regression `CREATE OR REPLACE MODEL <dataset>.<name> OPTIONS(model_type='<type>') AS <training dataset>`
- Training Progress = `SELECT * FROM ML.TRAINING_INFO(MODEL mydataset.mymodel)`
- Inspect Weights = `SELECT * FROM ML.WEIGHTS(MODEL mydataset.mymodel, (<query>))`
- Evaluation = `SELECT * FROM ML.EVALUATE(MODEL mydataset.mymodel)`
- Prediction = `SELECT * FROM ML.PREDICT(MODEL mydataset.mymodel, (<query>))`
  
  
