|Description|Command|
|-|-|
|Security Groups|```aws ec2 describe-security-groups --query "SecurityGroups[].[GroupId,GroupName]"```|
|VPC|```aws ec2 describe-vpcs --query "Vpcs[].[VpcId,CidrBlock]"```|
|Subnets|```aws ec2 describe-subnets --query "Subnets[].[SubnetId,AvailabilityZone,CidrBlock,VpcId]"```|
