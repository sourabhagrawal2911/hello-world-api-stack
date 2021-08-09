# Hello World API Stack

Sample Hello World API Stack consisting AWS API Gateway and Lambda backend deployed through CloudFormation.

## Tools
In order to execute the scripts, you need to install the following tools:

- [AWS CLI](https://aws.amazon.com/cli/) (AWS Command Line Interface)

## Usage

```bash
# Create Stack
aws cloudformation create-stack --stack-name hello-world-api-stack --template-body file://hello-world-api-stack.yaml --parameters file://parameters-hello-world-api-stack.json --tags file://tags-hello-world-api-stack.json --capabilities CAPABILITY_NAMED_IAM

# Update Stack
aws cloudformation update-stack --stack-name hello-world-api-stack --template-body file://hello-world-api-stack.yaml --parameters file://parameters-hello-world-api-stack.json --tags file://tags-hello-world-api-stack.json --capabilities CAPABILITY_NAMED_IAM

# Delete Stack
aws cloudformation delete-stack --stack-name hello-world-api-stack
```