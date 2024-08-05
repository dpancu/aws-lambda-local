
# aws-lambda-local

## Description
This is a simple AWS SAM project containing a single Lambda function called `test-function`.

## Prerequisites
- AWS CLI
- AWS SAM CLI
- Docker (if you want to test the Lambda function locally)

## Installation
1. Clone the repository or download the ZIP file.
2. Navigate to the project directory:
    ```
    cd aws-lambda-local
    ```

## Running the Function Locally
1. Install the dependencies:
    ```
    sam build
    ```
2. Start the Lambda function locally:
    ```
    sam local invoke test-function
    ```
3. Start the API Gateway locally:
    ```
    sam local start-api -t template.yaml --debug
    ```

## Deploying to AWS
1. Package the application:
    ```
    sam package --output-template-file packaged.yaml --s3-bucket YOUR_S3_BUCKET_NAME
    ```
2. Deploy the application:
    ```
    sam deploy --template-file packaged.yaml --stack-name YOUR_STACK_NAME --capabilities CAPABILITY_IAM
    ```

Replace `YOUR_S3_BUCKET_NAME` and `YOUR_STACK_NAME` with your actual S3 bucket name and CloudFormation stack name.