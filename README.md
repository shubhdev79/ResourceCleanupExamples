# ResourceCleanupExamples

# AWS Lambda
To list AWS Lambda functions, enter the following command.

- **aws lambda list-functions**

The following syntax deletes a Lambda function.
- **aws lambda delete-function --function-name function_name**

The deletion syntax requires only the function name, so to create a script, filter the JSON output of the list-functions command on FunctionName. In Windows, you can use the following syntax to pipe the output of list-functions into the findstr command and redirect the result into a text file.

- **aws lambda list-functions | findstr /C:FunctionName >lambdafns.txt**

The resulting file looks like this:

            "FunctionName": "CloudGemSamples-CGSamplesDep-Clo-ServiceLambda-hash",
            "FunctionName": "CloudGemSamples-AH-CoreResourceTypes-AWS_SQS_Queue",
            "FunctionName": "CloudGemSamples-AH-CoreResourceTypes-Custom_ServiceApi",
            "FunctionName": "CloudGemSamples-CRH-CoreResourceTypes-Custom_Helper",
            "FunctionName": "CloudGemSamples-CRH-CoreResourceTypes-Custom_Interfac-hash",
            "FunctionName": "CloudGemSamples-CGSamplesDep-PackageVoiceLines-hash",
            
**As before, use search and replace operations to turn the file into a deletion script, as in the following example**

- aws lambda delete-function --function-name CloudGemSamples-CGSamplesDep13-Clo-ServiceLambda-hash
- aws lambda delete-function --function-name CloudGemSamples-AH-CoreResourceTypes-AWS_SQS_Queue
- aws lambda delete-function --function-name CloudGemSamples-AH-CoreResourceTypes-Custom_ServiceApi
- aws lambda delete-function --function-name CloudGemSamples-CRH-CoreResourceTypes-Custom_Helper
- aws lambda delete-function --function-name CloudGemSamples-CRH-CoreResourceTypes-Custom_Interfac-hash
- aws lambda delete-function --function-name CloudGemSamples-CGSamplesDep13-PackageVoiceLines-hash

# Instances

- **aws ec2 describe-instances | findstr /C:InstanceId >instances.txt**

                    "InstanceId": "i-XXXXXXXXXXXXXXXXX",
                    "InstanceId": "i-XXXXXXXXXXXXXXXXX",
                    "InstanceId": "i-XXXXXXXXXXXXXXXXX",
                    "InstanceId": "i-XXXXXXXXXXXXXXXXX",
                    "InstanceId": "i-XXXXXXXXXXXXXXXXX",
                    "InstanceId": "i-XXXXXXXXXXXXXXXXX",
                    "InstanceId": "i-XXXXXXXXXXXXXXXXX",
                    "InstanceId": "i-XXXXXXXXXXXXXXXXX",
                    "InstanceId": "i-XXXXXXXXXXXXXXXXX",


# Buckets

- **aws s3api list-buckets | findstr /C:Name >s3buckets.txt**


