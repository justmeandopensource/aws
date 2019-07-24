|Description|Command|
|-|-|
|SG: Id,Name|```aws ec2 describe-security-groups --query "SecurityGroups[].[GroupId,GroupName]"```|
|VPC: Id,Cidr|```aws ec2 describe-vpcs --query "Vpcs[].[VpcId,CidrBlock]"```|
