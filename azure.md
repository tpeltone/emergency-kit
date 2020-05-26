# Azure

## Links

[Ansible on Azure Documentation](https://docs.microsoft.com/en-us/azure/developer/ansible/)

[GitHub - Microsoft Smart Hotel 360](https://github.com/Microsoft/SmartHotel360)

[Deploying Infrastructure Automatically To Azure CLoud Using Ansible and Azure Pipelines](https://www.youtube.com/watch?v=Q8aWeHCrGh4)

### Create Service Principal

Open the Azure Cloud Shell to create a service principal

```bash
# run the command
az ad sp create-for-rbac --name ServicePrincipalXXX
```

The output looks something likes this, but of course with your unique values.

```bash
{
  "appId": "xxxx-xxxx-xxxx-xxxxx-xxxxxx-xx",
  "displayName": "ServicePrincipalXXX",
  "name": "http://ServicePrincipalXXX",
  "password": "6c42a565-25eb-498c-9467-65d2b1e5b5f2",
  "tenant": "xxxx-xxxx-xxxx-xxxxx-xxxxxx-xx"
}
```

```bash
# type
az account show
```

```bash
{
  "environmentName": "AzureCloud",
  "homeTenantId": "xxxx-xxxx-xxxx-xxxxx-xxxxxx-xx",
  "id": "xxxx-xxxx-xxxx-xxxxx-xxxxxx-xx",
  "isDefault": true,
  "managedByTenants": [],
  "name": "Visual Studio Enterprise",
  "state": "Enabled",
  "tenantId": "xxxx-xxxx-xxxx-xxxxx-xxxxxx-xx",
  "user": {
    "cloudShellID": true,
    "name": "live.com#email@mail.com",
    "type": "user"
  }
}

```

## Ansible in Azure Cloud

Install Ansible commands

### Update and upgrade the packages

```bash
sudo apt update && sudo apt dist-upgrade -y
```

### Install pre-requisite packages

```bash
sudo apt install -y libssl-dev libffi-dev python-dev python-pip
```

### Install Ansible and Azure SDK via pip

```bash
sudo pip install ansible[azure]
```

### Service principle and subscription IDs

```bash
az ad sp create-for-rbac --name ServicePrincipalRadwan
az account show
```

### Authentication Remote Ansible machine to Azure

```bash
mkdir ~/.azure
nano ~/.azure/credentials
```

### Authenticate values

Insert the values into ~/.azure/credentials  
* _subscription_id=Your Azure Subscription_  
* _client_id=appId_  
* _secret=password_  
* _tenant=tenantId_  

```vim
 [default]

subscription_id=xxxx-xxxx-xxxx-xxxxx-xxxxxx-xx

client_id=xxxx-xxxx-xxxx-xxxxx-xxxxxx-xx

secret=xxxx-xxxx-xxxx-xxxxx-xxxxxx-xx

tenant=xxxx-xxxx-xxxx-xxxxx-xxxxxx-xx
```

### Generate RSA key

```bash
ssh-keygen -t rsa
chmod 755 ~/.ssh
touch ~/.ssh/authorized_keys
chmod 644 ~/.ssh/authorized_keys
ssh-copy-id mradwan@127.0.0.1
cat ~/.ssh/id_rsa
```

User name and password to login to the hotel web app

```bash
Username: me@smarthotel360.com
Password: 1234
```
