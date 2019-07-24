|Description|Command|
|-|-|
|Security Groups|```aws ec2 describe-security-groups --query "SecurityGroups[].[GroupId,GroupName,Description,VpcId]" --output table```|
|VPC|```aws ec2 describe-vpcs --query "Vpcs[].[VpcId,CidrBlock]" --output table```|
|Subnets|```aws ec2 describe-subnets --query "Subnets[].[SubnetId,AvailabilityZone,CidrBlock,VpcId]" --output table```|
|Instances|```aws ec2 describe-instances --query "Reservations[].Instances[].[InstanceId,InstanceType,PrivateIpAddress,PublicIpAddress,State.Name,Placement.AvailabilityZone]" --output table```|
