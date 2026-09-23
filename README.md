# Azure Resource Manager (ARM) Infrastructure Automation

## Project Overview
This repository contains production-ready JSON Azure Resource Manager (ARM) templates designed to automate the deployment of cloud infrastructure resources. This project demonstrates Infrastructure as Code (IaC) principles by replacing manual portal configurations with declarative, version-controlled scripts.

## Architecture & Features
- **Dynamic Parameterization:** Implemented customizable inputs for storage account naming (`storageName`) and redundancy tier selection (`storageSKU`).
- **Policy Compliance:** Built to adapt dynamically to regional data sovereignty compliance by leveraging `[resourceGroup().location]`.
- **Structured Outputs:** Configured runtime telemetry outputs to automatically capture and return the primary blob endpoints (`primaryEndpoints`) upon deployment success.

## Deployment Instructions
Deploy this infrastructure cleanly using the Azure CLI via Windows Command Prompt or Bash:

```cmd
az deployment group create \
  --resource-group YourResourceGroup \
  --name TemplateDeployment \
  --template-file storage-account-deployment.json \
  --parameters storageName=uniquestoragename storageSKU=Standard_LRS
```
