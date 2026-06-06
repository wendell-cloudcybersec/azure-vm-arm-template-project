# Azure VM Deployment Documentation

## Objective

Deploy an Ubuntu Linux Virtual Machine using Azure Resource Manager (ARM) templates.

## Azure CLI Installation

Azure CLI was installed and verified using:

```bash
az version
```

## Login to Azure

```bash
az login
```

## Resource Group Creation

```bash
az group create \
--name ARMProjectRG \
--location centralus
```

## ARM Template Validation

```bash
az deployment group validate \
--resource-group ARMProjectRG \
--template-file azuredeploy.json \
--parameters azuredeploy.parameters.json
```

Validation completed successfully.

## ARM Template Deployment

```bash
az deployment group create \
--resource-group ARMProjectRG \
--template-file azuredeploy.json \
--parameters azuredeploy.parameters.json
```

## Resources Created

* Virtual Network
* Subnet
* Public IP
* Network Security Group
* Network Interface
* Ubuntu 22.04 Virtual Machine

## VM Verification

The VM status was verified:

```bash
az vm get-instance-view
```

Results:

* Provisioning succeeded
* VM running

## SSH Verification

Connection established using:

```bash
ssh azureuser@<public-ip>
```

Verification commands:

```bash
hostname
whoami
uname -a
```

Results confirmed successful access to the deployed Ubuntu VM.

## Conclusion

The deployment successfully provisioned and validated all required Azure resources using Infrastructure as Code principles.
