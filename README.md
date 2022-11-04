# INFRASTRUCTURE AS CODE
In this Assignment we are learning how to use AWS cloudformation template to deploy things like creating VPC, Internet Gateway, Subnets, etc.

# Prerequisite
## AWS Account
## AWS IAM user with access key and secret key and Administrator privileges.
## AWS CLI configured


-----
# How to Run
After you have configured AWS CLI with your appropriate profile and regions.

To run the cloudformation stack file, run below command where your YML file is present.
````
aws --profile=dev cloudformation create-stack --stack-name YourStackName --template-body file://VPC.yml
````
After running this command, if everything is fine, you can check the status of your stack execution by running the below command.
````
aws cloudformation describe-stacks
````
This will give you all the details of the stack.

To pass parameters to your command, run below command:
````
aws --profile=dev cloudformation create-stack --stack-name YourStackName --template-body file://VPC.yml --parameters ParameterKey=amiImageId,ParameterValue=ami-049798eca1d0ee2d5 --capabilities CAPABILITY_NAMED_IAM 
````

To delete the stack, run below command.
````
aws --profile=dev cloudformation delete-stack --stack-name MyNetwork 
````

You can check all the created resources on AWS console by logging into your account and going to resource link.



