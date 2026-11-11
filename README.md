# EC2 on AWS with Terraform

This Terraform configuration launches one `t3.micro` EC2 instance in `us-east-1`
using the latest Amazon Linux 2023 x86_64 AMI. It uses the AWS provider's default
credential chain and the account's default VPC/subnet.

## Requirements

- Terraform 1.3 or later
- AWS credentials configured locally (for example, through `aws configure` or an
  AWS profile)
- An AWS account with a default VPC and permission to launch EC2 instances

## Create the instance

```powershell
terraform init
terraform plan
terraform apply
```

To select a different EC2 instance type:

```powershell
terraform apply -var="instance_type=t3.small"
```

Terraform prints the instance ID and public IP when available. The instance may
incur AWS charges while running.

## Remove the instance

```powershell
terraform destroy
```
