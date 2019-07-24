## Whats Required
* Security Group name
* Security Group description
* Security Group id
* VPC ID

## CLI Commands
#### List security groups
From default vpc
```
$ aws ec2 describe-security-groups
```
From a specific vpc (change vpc id accordingly)
```
$ aws ec2 describe-security-groups --filters Name=vpc-id,Values=vpc-3ced8154
```
Just grab the id and name
```
$ aws ec2 describe-security-groups --query "SecurityGroups[].[GroupId,GroupName]"
```
#### Create security group
```
$ aws ec2 create-security-group --group-name my-sg --description "My security group" --vpc-id vpc-3ced8154
```

#### Add ingress/inbound rules to the security group
CIDR ingress
```
$ aws ec2 authorize-security-group-ingress --group-id sg-903004f8 --protocol tcp --port 22 --cidr 203.0.113.0/24
```
Source from another security group
```
$ aws ec2 authorize-secutiry-group-ingress --group-id sg-903004f8 --protocol tcp --port 22 --source-group sg-a677aec9
```
#### Delete security group
```
$ aws ec2 delete-security-group --group-id sg-903004f8
```
