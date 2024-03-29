# Generate the pre-signed URL  for objects stored in S3 Bukcet

This sample webpage can be used to upload and download the images from the local machine to the S3 bucket, with the help of Lambda Function
Once images are uploaded our backend lambda function responds with the Pre-signed URL of the image and displays it on the webpage.
It's just a sample to  How-to-generate-signed-URL of the object stored in the S3 bucket

##

## Requirements
- Previous knowledge of AWS IAM roles.
- AWS CLI is already configured with a user that has to write permissions (access to create/update/delete lambda function).
- IAM role that is attached to the lambda function to access the S3 bucket.

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
    "Runtime": "Python3.x",
    "Role": "arn:aws:iam::123456789012:role/lambda-ex",
    "Handler": "presignedS3Lambda.lambda_handler",
    "CodeSha256": "FpFMvUhayLkOoVBpNuNiIVML/tuGv2iJQ7t0yWVTU8c=",
    "Version": "$LATEST",
    "TracingConfig": {
        "Mode": "PassThrough"
    },
    "RevisionId": "88ebe1e1-bfdf-4dc3-84de-3017268fa1ff"
}
```

## License

MIT
