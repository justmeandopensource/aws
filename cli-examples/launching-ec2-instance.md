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
