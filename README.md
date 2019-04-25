# ac3test

This cloudformation template installs a highly-available, scalable WordPress deployment using EC2, RDS managed services. 

## Prerequisites


- install aws cli on your local machine and run aws configure, follow the prompts and enter the necessary  AWS credentials:
``` bash
  aws configure
```
- create prod and dev VPCs and necessary private subnets in AWS
- create an internet gateway and attach it to each VPC respectively
- create DBSubnetGroups
- create prod and dev ssh key pairs in AWS

## Getting Started

Clone this repository on your local machine:
```bash
  git clone https://github.com/ac3devintw16/ac3test.git
```
Navigate to "~/cfn/" directory


## Cloudformation parameter modification

Modify the following Development and Production parameter files:
- ~/cfn/params/develop.json
- ~/cfn/params/production.json

For Develop environment you may specify less number of EC2 instances and a RDS deploymet without MultiAZ as that level of redundancy would only be required in production:

```json
   {
    "ParameterKey": "WebServerCapacity",
    "ParameterValue": "1"
   }

   {
    "ParameterKey": "MultiAZDatabase",
    "ParameterValue": "false"
   }

```



## Launch CFN stack

Launch Develop Stack
```bash
aws cloudformation create-stack --stack-name ac3DevWordPress --template-body file://template/ec2-asg-rds-generic.template --parameters file://params/develop.json
```

Launch Production Stack
```bash
aws cloudformation create-stack --stack-name ac3ProdWordPress --template-body file://template/ec2-asg-rds-generic.template --parameters file://params/production.json
```

