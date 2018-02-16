

Usage:

Create aws key credential files:

```
mkdir ~/.aws
cat > ~/.aws/credentials.CUSTOMER_NAME
export AWS_REGION=eu-west-1
export AWS_ACCESS_KEY_ID=XXXXX
export AWS_SECRET_ACCESS_KEY=XXXX
export AWS_DEFAULT_REGION=eu-west-1
ctrl + c
```

You can create as many customers as you want:

```
ls ~/.aws
credentials.customer_a  credentials.customer_b  credentials.customer_c
```

Switch to a customer

```
aws-switch-profile customer_a
```

Grab instance / elb / alb information

```
aws-ec2-describe-albs
aws-ec2-describe-elbs
aws-ec2-describe-instances  
```

Connect to an instance:

```
aws-ssh test-prod-ec2-web
```

If multiple instances have the same tag, you can connect to different instances using the position flag:

```
aws-ssh -p 1 test-prod-ec2-web
aws-ssh -p 2 test-prod-ec2-web
aws-ssh -p 3 test-prod-ec2-web
aws-ssh -p 4 test-prod-ec2-web
```

You can also run a command on ALL the instances of the same tag:

```
aws-ssh -d test-prod-ec2-web uptime
```

Or run a command on just one instance

```
aws-ssh test-prod-ec2-web uptime
```

