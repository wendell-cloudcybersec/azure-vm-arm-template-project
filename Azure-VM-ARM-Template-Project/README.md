# Azure VM ARM Template Project

## Project Overview

This project demonstrates the deployment of an Ubuntu Linux Virtual Machine in Microsoft Azure using an Azure Resource Manager (ARM) template.

The deployment provisions:

* Virtual Network (VNet)
* Subnet
* Public IP Address
* Network Security Group (NSG)
* Network Interface Card (NIC)
* Ubuntu 22.04 Virtual Machine

The infrastructure was deployed using Azure CLI and Infrastructure as Code (IaC) principles.

## Technologies Used

* Microsoft Azure
* Azure CLI
* ARM Templates
* Ubuntu 22.04 LTS
* SSH

## Deployment Commands

```bash
az login

az group create --name ARMProjectRG --location centralus

az deployment group create \
--resource-group ARMProjectRG \
--template-file azuredeploy.json \
--parameters azuredeploy.parameters.json
```

## Validation

The deployment was validated using:

```bash
az deployment group validate
az vm get-instance-view
```

SSH connectivity was verified using:

```bash
ssh azureuser@<public-ip>
```

## Outcome

The VM was successfully deployed, verified, and accessed through SSH.
