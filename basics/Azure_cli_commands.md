## Azure CLI Commands:

### Open the Azure Cloud Shell
shell.azure.com

### List Resrouce Groups

```
az group list
```

### Create variable with output of "az group list" command

```
rgcli=$(az group list)
```

### Create variable to only include the name of the Resource Group 

```
rgcli=$(az group list --query "[].name" --output tsv)
```

### Show contents of variable

```
echo $rgcli
```

### Create Virtual Network using variable

```
az network vnet create \
    --name vnet-cli \
    --resource-group $rgcli \
    --address-prefix 10.0.0.0/16 \
```