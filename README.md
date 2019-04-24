# ac3test



#Getting Started

#Prerequisites
- install aws cli on your local machine
- create prod and dev VPCs and necessary private subnets in AWS
- create an internet gateway and attach it to each VPC respectively
- create DBSubnetGroups
- create prod and dev ssh key pairs in AWS


#Launch CFN stack

aws cloudformation create-stack --stack-name ac3testRun --template-body file://template/ec2-asg-rds-generic.template --parameters file://params/develop.json
