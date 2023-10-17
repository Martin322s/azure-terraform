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


  backend "azurerm" {
    resource_group_name  = "StorageRG"
    storage_account_name = "taskboardstoragemero5"
    container_name       = "taskboardcontainer"
    key                  = "terraform.tfstate"
  }
}

provider "azurerm" {
  features {}
}

resource_group_name: This variable specifies the name of the Azure Resource Group where your Azure resources will be deployed. In this case, it's set to "taskboard-resource-group."

resource_group_location: This variable defines the Azure region (location) where the resource group will be created. In this case, it's set to "westeurope."

app_service_name: This variable represents the name of the Azure Web App service that will be created. It's set to "taskboard-service."

app_service_plan_name: This variable specifies the name of the Azure App Service Plan that the web app will use. It's set to "taskboard-plan."

sql_administrator_login_username: This variable sets the username for the SQL Server administrator.

sql_administrator_password: This variable sets the password for the SQL Server administrator. It's important to use a strong, secure password.

sql_database_name: This variable defines the name of the SQL Database that will be created. It's set to "sql-database."

sql_server_name: This variable specifies the name of the Azure SQL Server. It's set to "sqlserver-azdb."
