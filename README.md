```markdown
# Terraform Script to Create EC2 Instance in AWS

This repository contains a simple Terraform script to create an EC2 instance in AWS.

## Prerequisites

- [Terraform](https://www.terraform.io/downloads.html) installed on your local machine.
- AWS account with necessary permissions to create an EC2 instance.
- AWS access key and secret access key.

## AWS Setup

Ensure you have your AWS access key and secret access key. You can generate these from the AWS Management Console.

## Terraform Script

The Terraform script provided here will create a `t2.micro` EC2 instance in the `ap-south-1` region with a specified Amazon Machine Image (AMI).

```

### `main.tf`
```sh

  provider "aws" {
    region = "ap-south-1"
  }

  resource "aws_instance" "ec2-one" {
    ami               = "ami-0ad21ae1d0696ad58"
    instance_type     = "t2.micro"
    associate_public_ip_address = true

    tags = {
      Name = "Test instance terraform"
    }
  }
```
```
```


## Usage

1. Clone this repository to your local machine.

    ```sh
    mkdir <dir name>
    cd <dir name>
    ```

2. Export your AWS credentials.

    ```sh
    export AWS_ACCESS_KEY_ID=your_access_key_id
    export AWS_SECRET_ACCESS_KEY=your_secret_access_key
    ```

3. Initialize Terraform.

    ```sh
    terraform init
    ```

4. Apply the Terraform configuration to create the EC2 instance.

    ```sh
    terraform apply
    ```

    You will be prompted to confirm the action. Type `yes` to proceed.

5. After a few minutes, your EC2 instance will be created, and Terraform will output its details.

## Cleanup

To destroy the resources created by Terraform, run:

```sh
terraform destroy
```

Again, you will be prompted to confirm the action. Type `yes` to proceed.

## Notes

- Ensure that the specified AMI ID (`ami-0ad21ae1d0696ad58`) is available in the `ap-south-1` region. If not, replace it with an appropriate AMI ID available in your desired region.
- This script creates a basic EC2 instance. Additional configurations, such as security groups, key pairs, etc., can be added as needed.

## References

- [Terraform AWS Provider Documentation](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/index.html)
```

