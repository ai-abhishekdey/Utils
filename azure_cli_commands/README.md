
## Azure CLI installation and commands

**Author: Abhishek Dey**


## Installation

```
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash


sudo apt-get update && sudo apt-get install --only-upgrade -y azure-cli

```

## Check installed Azure CLI version

```
az --version

```

## Login

* Using Browser

```
az login

```

* No-Browser

```
az login --use-device-code

```
* Using Tenant-ID

```
az login --tenant <Tenant-ID>

```

## List of subscriptions

```
az account list -o table

```

## List of virtual machines (VMs)

```
az vm list -o table

```

## List of Storage Accounts / Blobs

```
az storage account list -o table

```

## List containers (buckets) inside a storage account

```
az storage container list --account-name <storage_account_name> -o table

```

## Upload a single file

```
az storage blob upload \
  --account-name <storage_account> \
  --container-name <container> \
  --file <path/to/file> \
  --name <filename> 
  
```

```
az storage blob upload \
  --account-name abhishekdey \
  --container-name ad-workspace \
  --file img/test_img.jpg \
  --name single_test_img.jpg 
  
```

* This will upload **test_img.jpg from img folder** to **ad-workspace** container. The name of the uploaded image will be **single_test_img.jpg**

## Upload a folder with files

```
az storage blob upload-batch \
  --account-name <storage_account> \
  --destination <container> \
  --source <local_folder> \

```

Eg:

```
az storage blob upload-batch \
  --account-name abhishekdey\
  --destination ad-workspace/test_folder \
  --source ./img

```

* This will upload **img** folder inside **ad-workspace/test_folder**


## List inside container

```
az storage blob list \
  --account-name abhishekdey \
  --container-name ad-workspace \
  --delimiter "/" \
  -o table

```

```

Name                 Blob Type    Blob Tier    Length    Content Type    Last Modified             
-------------------  -----------  -----------  --------  --------------  -------------------------
test_folder/
single_test_img.jpg  BlockBlob    Hot          151591    image/jpeg      2025-12-06T11:49:41+00:00

```

## To list the contents inside a specific "folder"

```
az storage blob list \
  --account-name abhishekdey \
  --container-name ad-workspace \
  --prefix "test_folder/" \
  -o table 
  
```

```

Name                      Blob Type    Blob Tier    Length    Content Type    Last Modified              
------------------------  -----------  -----------  --------  --------------  -------------------------  
test_folder/test_img.jpg  BlockBlob    Hot          151591    image/jpeg      2025-12-06T11:52:25+00:00

```

## To download a single file

```
az storage blob download \
  --account-name abhishekdey \
  --container-name ad-workspace \
  --name test_folder/test_img.jpg \
  --file output.jpg
  
```

* This will donwload **test_folder/test_img.jpg** as **output.jpg** in pwd

## To download a folder

* first create the output_dir

```
mkdir -p output_dir

```

```
az storage blob download-batch \
  --account-name abhishekdey \
  --source ad-workspace \
  --pattern "test_folder/*" \
  --destination ./output_dir

```

* This will dowload **test_folder** along with its contents inside **output_dir**. 


## References

* [Installation](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?view=azure-cli-latest&pivots=apt)
