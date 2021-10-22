# Generate the pre-signed URL  for objects stored in S3 Bukcet

This sample webpage can be used to upload and download the images from local machine to S3 bucket, with the help of Lambda Function
Once images is uploaded our backend lamabda function responds back with the Pre-signed url of the image and display it on the webpage.
Its just sample to How-to-generate-pre-signed-url of the object store in the S3 bucket

##

## Requirements
- Python 3 installed
- AWS CLI already configured with right permission (access to create/update/delete lambda fucntion)
- IAM role that is attached to the lambda fucntion to access the S3 bucket

## Project setup / Installation

Copy the sample code into a file named index.js
Create a deployment package.

```
zip function.zip presignedS3Lambda.py
```
Create a Lambda function with the create-function command. Replace the highlighted text in the role ARN with your account ID.

```
aws lambda create-function --function-name presignedS3Lambda \
--zip-file fileb://function.zip --handler presignedS3Lambda.lambda_handler --runtime python3.x \
--role arn:aws:iam::123456789012:role/lambda-ex
```
You should see the following output:

```json
{
    "FunctionName": "presignedS3Lambda",
    "FunctionArn": "arn:aws:lambda:us-east-2:123456789012:function:my-function",
    "Runtime": "nodejs12.x",
    "Role": "arn:aws:iam::123456789012:role/lambda-ex",
    "Handler": "presignedS3Lambda.lambda_handler",
    "CodeSha256": "FpFMvUhayLkOoVBpNuNiIVML/tuGv2iJQ7t0yWVTU8c=",
    "Version": "$LATEST",
    "TracingConfig": {
        "Mode": "PassThrough"
    },
    "RevisionId": "88ebe1e1-bfdf-4dc3-84de-3017268fa1ff",
    ...
}
```

## License

MIT
