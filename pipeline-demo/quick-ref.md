## Sample application (Linux)
```
wget https://s3.amazonaws.com/aws-codedeploy-us-east-1/samples/latest/SampleApp_Linux.zip
```

## Bootstrap code for installing CodeDeploy agent on Linux
```
#!/bin/bash
yum -y update
yum install -y ruby
yum install -y aws-cli
cd /home/ec2-user
aws s3 cp s3://aws-codedeploy-us-east-2/latest/install . --region us-east-2
chmod +x ./install
./install auto
```
