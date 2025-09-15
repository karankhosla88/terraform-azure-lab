# 🚀 Terraform Azure Lab (GitHub Codespaces)

This repository provides a ready-to-use lab environment for deploying Azure resources with **Terraform** inside **GitHub Codespaces**.  
Each student uses their own GitHub account and Azure subscription.

---

## 📂 Repository Structure

```text
terraform-azure-lab/
├── .devcontainer/
│   └── devcontainer.json       # Codespace setup (Terraform + Azure CLI)
├── terraform/
│   ├── provider.tf             # Provider configuration
│   ├── resource_group.tf       # Resource group definition
│   ├── variables.tf            # Input variables
│   └── terraform.tfvars.example# Example variables file for students
├── .gitignore                  # Ignore local Terraform state/binaries
└── README.md                   # Lab instructions


------------------

## ✅ Prerequisites

- A **GitHub account**
- Access to **GitHub Codespaces**
- An **Azure subscription** (student/trial subscription works)

---

## 🖥️ Usage

Follow these steps to complete the lab:

1. **Launch Codespace**  
   - Open this repo in **GitHub Codespaces**.  
   - Wait for the devcontainer to install **Terraform** and **Azure CLI** automatically.  
   - Verify installation:  

     ```bash
     terraform --version
     az --version
     ```

2. **Configure Variables**  
   - Navigate to the `terraform` directory.  
   - Copy the example variables file:  

     ```bash
     cp terraform.tfvars.example terraform.tfvars
     ```

   - Edit `terraform.tfvars` and update values:  

     ```hcl
     subscription_id      = "YOUR_AZURE_SUBSCRIPTION_ID"
     resource_group_name  = "Student1-RG"
     location             = "East US"
     ```

   > 🔑 Each student must use **their own subscription ID** and a **unique resource group name**.

3. **Run Terraform**  
   - Inside the `terraform` folder, run:  

     ```bash
     terraform init     # Download providers and initialize project
     terraform plan     # Preview resources to be created
     terraform apply    # Deploy resources
     ```

4. **Clean Up**  
   - After completing the lab, always destroy resources to avoid extra costs:  

     ```bash
     terraform destroy -auto-approve
     ```

---

## 📌 Notes for Students

- Only **`terraform.tfvars`** should be edited.  
- The repo ignores `.terraform/`, `.tfstate`, and provider binaries (Terraform downloads them automatically).  
- Each student’s resources remain isolated since everyone uses their own subscription.

---

## 💡 Best Practices

- Never commit `.terraform/` or `.tfstate` files.  
- Always destroy resources after the lab.  
- Keep your resource group names **unique** if using the same Azure region.

---

## 🎯 Lab Learning Outcomes

By completing this lab, you will:

- Learn how to configure the AzureRM provider for Terraform.  
- Deploy and manage Azure resources from Codespaces.  
- Understand how to parameterize Terraform using variables and `.tfvars`.  
- Practice responsible cloud usage by cleaning up resources.  
