# Hello World API Stack

Sample Hello World API Stack consisting AWS API Gateway and Lambda backend deployed through CloudFormation.

## Prerequisites

In order to deploy this stack, you need following setup:

- [An AWS Account] https://aws.amazon.com/free/free-tier/
- [Your AWS Credentials] https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html
- Install and configure [AWS CLI](https://aws.amazon.com/cli/) (AWS Command Line Interface)


## Usage

```bash
# Create Stack
aws cloudformation create-stack --stack-name hello-world-api-stack --template-body file://hello-world-api-stack.yaml --parameters file://parameters-hello-world-api-stack.json --tags file://tags-hello-world-api-stack.json --capabilities CAPABILITY_NAMED_IAM

# Update Stack
aws cloudformation update-stack --stack-name hello-world-api-stack --template-body file://hello-world-api-stack.yaml --parameters file://parameters-hello-world-api-stack.json --tags file://tags-hello-world-api-stack.json --capabilities CAPABILITY_NAMED_IAM

# Delete Stack
aws cloudformation delete-stack --stack-name hello-world-api-stack
```


## Accessing API

```bash
# Once stack is deployed, describe the stack
aws cloudformation describe-stacks --stack-name hello-world-api-stack

#Note down the ApiUrl from Outputs section
{
    "Stacks": [
        {
            "StackId": "arn:aws:cloudformation:eu-west-1:1234455889:stack/hello-world-api-stack/8978798cbjn-f88a-11eb-90af-0a33ae0acab1",
            "DriftInformation": {
                "StackDriftStatus": "NOT_CHECKED"
            },
            "Description": "AWS CloudFormation Template to Deploy API Gateway with Lambda Proxy Backend",
            "Parameters": [
                { ..
				}
				
            ],
            "Tags": [
                { ..
				}
            ],
            "Outputs": [
                {
                    "Description": "Hello World API URL",
                    "ExportName": "hello-world-api-stack-ApiUrl",
                    "OutputKey": "ApiUrl",
                    "OutputValue": "https://abcd2f5gh7.execute-api.eu-west-1.amazonaws.com/dev/hello"
                },
                { ..
				}
			]
		}	
    ]
}

# Hit the ApiUrl from your browser and it should give respone from Hello World API.
```