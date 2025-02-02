# terraform-azure-storage-account
[Terraform](https://www.terraform.io) module to create an [Azure storage account](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-overview).

![Azure Storage Account](terraform-azure-storage-account.jpg)

## Install
This module requires that the following are installed locally:
* [Docker](https://www.docker.com/get-started)
* [Terraform](https://learn.hashicorp.com/tutorials/terraform/install-cli)

It also requires that there is an existing [Azure Resource Group](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/manage-resource-groups-portal) into which to place the storage account.

## Usage

### Log Into Azure
```bash
docker run -it -v $HOME/.azure:/root/.azure mcr.microsoft.com/azure-cli az login
```

### Create the Storage Account
```bash
# initialise 
terraform init

# create a terraform plan file from the provided variables
# NOTE: the existing Azure resource group will need to be provided at the command-line 
terraform plan -out tfplan

# apply the plan, creating the Azure storage account resource
terraform apply "tfplan"
```

### Destroy the Storage Account
```bash
terraform destroy
```

## Licence
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

This project is licenced under the terms of the [Apache 2.0 License](LICENCE.md) licence.