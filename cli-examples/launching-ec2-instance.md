## Whats Required
* AMI ID
* Instance count
* Instance type
* KeyPair name
* SecurityGroup ID
* Subnet ID

## CLI Commands

```
$ aws ec2 run-instances --image-id ami-0bdfa1adc3878cd23 --count 1 --instance-type t2.micro --key-name just-me-aws-demo --security-group-ids sg-0f7272cd2e155e0d8 --subnet-id subnet-f878ca82
```

##### To launch an instance with user-data for bootstrapping
Create a file (eg: /tmp/user-data)
```
#!/bin/bash
yum install -y httpd
chkconfig httpd on
echo "Hello World" > /var/www/html/index.html
service httpd start
```
Now you can launch instance using below command passing the above file
```
aws ec2 run-instances --image-id ami-0bdfa1adc3878cd23 --count 1 --instance-type t2.micro --key-name just-me-aws-demo --security-group-ids sg-0f7272cd2e155e0d8 --subnet-id subnet-f878ca82 --user-data file:///tmp/user-data
```

##### To view user-data for a running instance
```
aws ec2 describe-instance-attribute --instance-id i-0e2b5e1d6fe312acf --attribute userData --query UserData.Value --output text | base64 --decode
```
