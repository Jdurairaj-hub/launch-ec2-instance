# Launch EC2 Instance

This repository provides a set of Terraform automation scripts designed to deploy an EC2 instance on AWS. It simplifies the process of launching and managing EC2 resources, making it easier to configure and maintain AWS infrastructure.

The code build focuses on automating the deployment of an EC2 instance, configuring it with necessary security groups, and optionally provisioning it with additional services. This automation can be particularly useful for developers or DevOps engineers who need to set up consistent and repeatable infrastructure.


## Features

- Launches an EC2 instance with user-specified configurations.
- Supports various instance types and configurations.
- Configurable through Terraform variables.
- Automatically provisions an EC2 instance and assigns a security group.
- Easily customizable for different regions, instance types, and key pairs.

## Prerequisites

Before you begin, ensure you have the following installed:

- [Terraform](https://www.terraform.io/downloads.html) (v1.0+)
- [AWS CLI](https://aws.amazon.com/cli/) configured with appropriate credentials.
- A valid AWS account.

## Setup and Usage

### Step 1: Clone the Repository

```bash
git clone https://github.com/Jdurairaj-hub/launch-ec2-instance.git
cd launch-ec2-instance
```

### Step 2: Initialize Terraform

Run the following command to initialize the working directory containing the Terraform configuration files:

```bash
terraform init
```

### Step 3: Modify Variables

Modify the `variables.tf` file to configure your EC2 instance according to your needs. You can set the following parameters:

- `instance_type`: Choose the EC2 instance type (e.g., `t2.micro`).
- `region`: Set the AWS region (e.g., `us-east-1`).
- `ami`: Set the Amazon Machine Image (AMI) ID.
- `key_name`: Provide the name of the SSH key pair for access.
- `vpc_id`: Optionally specify a VPC for the instance.

### Step 4: Plan the Infrastructure

To see the changes Terraform will make, run:

```bash
terraform plan
```

### Step 5: Apply the Configuration

To apply the configuration and launch the EC2 instance, run:

```bash
terraform apply
```

Type yes when prompted to confirm the creation of resources.

### Step 6: Access the Instance

Once the EC2 instance is up and running, you can SSH into it using your key pair:

```bash
ssh -i /path_to_key.pem ec2-user@instance_ip_address
```

### Cleaning Up

To destroy the EC2 instance and other resources created by Terraform, run:

```bash
terraform destroy
```

Type yes when prompted to confirm the destruction of resources.