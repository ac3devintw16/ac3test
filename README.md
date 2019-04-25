# ac3test

This cloudformation template installs a highly-available, scalable WordPress deployment using EC2, RDS managed services. 

##Prerequisites


- install aws cli on your local machine
- create prod and dev VPCs and necessary private subnets in AWS
- create an internet gateway and attach it to each VPC respectively
- create DBSubnetGroups
- create prod and dev ssh key pairs in AWS

## Getting Started

Clone this repository on your local machine:


## Cloudformation parameter modification

Modify the following Development and Production parameter files
- ~/cfn/params/develop.json
- ~/cfn/params/production.json

##Launch CFN stack

Launch Develop Stack
```bash
aws cloudformation create-stack --stack-name ac3DevWordPress --template-body file://template/ec2-asg-rds-generic.template --parameters file://params/develop.json
```

Launch Production Stack
```bash
aws cloudformation create-stack --stack-name ac3ProdWordPress --template-body file://template/ec2-asg-rds-generic.template --parameters file://params/production.json
```

