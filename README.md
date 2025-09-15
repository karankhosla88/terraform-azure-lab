# Terraform Azure Lab

This lab is designed for students to practice deploying Azure resources using Terraform in GitHub Codespaces. Each student will use their own Azure subscription and follow step-by-step instructions.

---

## Repo Structure

terraform-azure-lab/
├── .devcontainer/
│ └── devcontainer.json
├── terraform/
│ ├── provider.tf
│ ├── resource_group.tf
│ ├── variables.tf
│ └── terraform.tfvars.example
├── .gitignore
└── README.md


---

## Prerequisites

- GitHub account
- Azure subscription (temporary lab subscription is fine)
- Access to GitHub Codespaces

---

## 1️⃣ Setup Codespace

1. Open this repository in **GitHub Codespaces**.  
2. Wait for the devcontainer to initialize Terraform and Azure CLI.

---

## 2️⃣ Configure Terraform Variables

1. Navigate to the `terraform` directory.  
2. Copy the example variables file:

```bash
cp terraform.tfvars.example terraform.tfvars

3. Edit terraform.tfvars with your subscription and desired resource group:
subscription_id      = "YOUR_AZURE_SUBSCRIPTION_ID"
resource_group_name  = "YourUniqueRGName"
location             = "East US"   # or any Azure region you prefer

## 3️⃣ Terraform Workflow
Run the following commands inside the terraform directory:

# Initialize Terraform and download providers
terraform init

# Preview the resources to be created
terraform plan

# Apply the configuration
terraform apply

## 4️⃣ Clean Up Resources
After the lab, destroy all resources to avoid unnecessary costs:
terraform destroy -auto-approve

## 5️⃣ Notes for Students

Only terraform.tfvars should be modified.

.terraform/ and provider binaries are ignored in the repo; Terraform downloads them automatically.

Each student should use a unique resource group name to avoid conflicts.

## 6️⃣ Best Practices

Do not commit .terraform/ or .tfstate files.

Use the provided .gitignore for Terraform files.

Always destroy lab resources after completion.
