
# Terraform Azure Lab

## Setup Instructions

1. Open Codespace from this repository.
2. Log in to Azure:
```bash
az login --use-device-code
az account set --subscription "<THEIR_SUBSCRIPTION_ID>"
cd terraform
terraform init
terraform plan
terraform apply

