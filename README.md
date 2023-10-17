# Terraform Configuration for Azure Web App Deployment

This Terraform configuration deploys an Azure web app with an associated Azure SQL Database and integrates it with source control. It also creates a random integer to ensure unique resource names.

## Prerequisites

Before using this Terraform configuration, make sure you have:

- An Azure subscription and valid credentials.
- Terraform installed on your local machine.
- The Azure CLI installed and authenticated.

## Configuration

The following Terraform configuration uses the HashiCorp Azure provider to create Azure resources:

```hcl
terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "3.75.0"
    }
  }
