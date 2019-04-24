# ac3test



#Getting Started

#Prerequisites


#Launch CFN stack

aws cloudformation create-stack --stack-name ac3testRun --template-body file://template/ec2-asg-rds-generic.template --parameters file://params/develop.json
