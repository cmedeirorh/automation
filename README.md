readme_content = """# AWS Multi-Region Infrastructure Provisioning

This Ansible project provisions a foundational AWS network and security infrastructure across multiple regions simultaneously. It is designed as a reusable Ansible role that ensures consistent networking, access, and tagging standards.

## Features

- **Multi-Region Deployment:** Iterates through a defined list of AWS regions to deploy identical environments.
- **VPC & Subnets:** Creates VPCs and maps public subnets within them.
- **Internet Routing:** Provisions Internet Gateways (IGWs) and Route Tables to enable public internet access for resources within the subnets.
- **Security Groups:** Configures stateful Security Groups allowing inbound SSH (Port 22) and unrestricted outbound internet traffic.
- **Dynamic SSH Key Injection:** Automatically fetches a public SSH key from a defined GitHub `.keys` URL and imports it as an EC2 Key Pair in all target regions.
- **Standardized Tagging:** Applies `Environment`, `Purpose`, `Owner`, and `Name` tags to all provisioned resources for governance and cost tracking.

## Prerequisites

Before running this playbook, ensure the control node meets the following requirements:

1. **Ansible Installed:** `pip install ansible`
2. **AWS Collection Installed:** `ansible-galaxy collection install amazon.aws`
3. **Boto3 & Botocore:** `pip install boto3 botocore`
4. **AWS Credentials:** Authenticated via standard methods (e.g., `~/.aws/credentials`, exported environment variables like `AWS_ACCESS_KEY_ID`, or an attached IAM instance profile).

## Directory Structure
