# AWS Step Functions

* **Use to design workflows**
* Advanced Error Handling and Retry mechanism outside the code
* Audit of the history of workflows
* Ability to "Wait" for an arbitrary amount of time
* max execution time of a State Machine is 1 year.

## Step Functions - Examples
### Train a Machine Learning Model
* *example*
    ```JSON
    "StartAt": "Generate dataset",
    "States":{
        "Generate dataset":{
            "Resource": "<GENERATE_LAMBDA_FUNCTION_ARN>",
            "Type": "Task",
            "Next": "Train model (XGBoost)",
            },
        "Train model (XGBoost)": {
            "Resource": "arn: <PARTITION>:states:::sagemaker:createTrainingJob.sync",
            "Parameters": {
                "AlgorithmSpecification":{
                    "TrainingImage": "<SAGEMAKER_TRAINING_IMAGE>",
                    "TrainingInputMode": "File"
                },
            "OutputDataConfig":{
                "S3OutputPath": "s3://<S3_BUCKET>/models"
            },
            "StoppingCondition":{
                "MaxRuntimeInSeconds": 86400
            },
            "ResourceConfig":{
                "InstanceCount":{
                    "InstanceCount": 1,
                    "InstanceType": "ml.m4.xlarge"
                }
            }
            }
        }
    }
    ```
### Tune a Machine Learning Model
### Manage a Batch Job

