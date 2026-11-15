# AWS Infrastructure Project

A small AWS-style infrastructure built with Terraform, deployed against
[LocalStack](https://www.localstack.cloud/) (Community edition) for
local testing without requiring a real AWS account.

## What this builds
- A VPC with a public subnet
- An internet gateway and routing
- A security group allowing HTTP and SSH
- Two EC2 instances

## Known limitation
An Application Load Balancer (ELBv2) was also written (see
`loadbalancer.tf.disabled`) but could not be deployed, since ELBv2
support requires LocalStack Pro (a paid feature). The code is included
to demonstrate the design, and would deploy as-is against real AWS or
LocalStack Pro.

## Usage
\`\`\`
localstack start -d   # or: docker run -d -e LOCALSTACK_ACKNOWLEDGE_ACCOUNT_REQUIREMENT=1 -p 4566:4566 localstack/localstack
terraform init
terraform plan
terraform apply
\`\`\`

