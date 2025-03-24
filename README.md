# Ansible for Azure Demo #

Providing simple playbooks to showcase IaC for Azure

Galaxy Ref: https://galaxy.ansible.com/ui/repo/published/azure/azcollection/

## Azure CLI Run ##

```bash
$ ansible-playbook azure_provision_rg.yaml
$ ansible-playbook azure_provision_vnet.yaml
$ ansible-playbook azure_provision_subnet.yaml
```

## AAP Setup ##

You will need to create AAP (2.5) resources: 
- Project
- Inventory (localhost)
- Job Templates
- Machine Credential
- Sync galaxy community for azure.azcollection
- Ensure AAP Org points to Galaxy 

Create Execution Environment (EE)

See azure-ee folder for example.

Push EE to Automation Hub.

For AAP2.5, the user must be configured with the galaxy content admin role first.

## Azure CLI Setup ##

Export Azure Secret to ENV, as we are using the default ```auth_source: env```

```bash
export AZURE_CLIENT_ID=your_client_id
export AZURE_CLIENT_SECRET=your_secret
export AZURE_TENANT_ID=your_tenant_id
export AZURE_SUBSCRIPTION_ID=your_subscription_id
```

Install collection on local Ansible Host

```bash
$ ansible-galaxy collection install azure.azcollection
```

Install python modules per requirements. [https://github.com/ansible-collections/azure/blob/dev/requirements.txt](Source Repo)

```bash
$ echo requirements.txt
packaging
requests[security]
xmltodict
msgraph-sdk==1.6.0
azure-cli-core==2.64.0
azure-common==1.1.28
azure-identity==1.19.0
azure-mgmt-authorization==4.0.0
azure-mgmt-apimanagement==4.0.1
azure-mgmt-batch==17.3.0
azure-mgmt-compute==33.0.0
azure-mgmt-cdn==13.1.1
azure-mgmt-containerinstance==10.1.0
azure-mgmt-core==1.4.0
azure-mgmt-containerregistry==10.3.0
azure-containerregistry==1.2.0
azure-mgmt-containerservice==32.1.0
azure-mgmt-datafactory==9.0.0
azure-mgmt-dns==8.1.0
azure-mgmt-marketplaceordering==1.2.0b2
azure-mgmt-monitor==6.0.2
azure-mgmt-managedservices==7.0.0b2
azure-mgmt-managementgroups==1.1.0b2
azure-mgmt-network==28.0.0
azure-mgmt-nspkg==3.0.2
azure-mgmt-privatedns==1.1.0
azure-mgmt-redis==14.4.0
azure-mgmt-resource==23.2.0
azure-mgmt-rdbms==10.2.0b17
azure-mgmt-search==9.2.0b2
azure-mgmt-servicebus==8.2.1
azure-mgmt-sql==4.0.0b19
azure-mgmt-storage==21.2.1
azure-mgmt-trafficmanager==1.1.0
azure-mgmt-web==7.3.1
azure-nspkg==3.0.2
azure-storage-blob==12.23.0b1
azure-core==1.31.0
azure-keyvault==4.2.0
azure-mgmt-keyvault==10.3.1
azure-mgmt-cosmosdb==10.0.0b3
azure-mgmt-hdinsight==9.1.0b1
azure-mgmt-devtestlabs==10.0.0b2
azure-mgmt-loganalytics==13.0.0b7
azure-mgmt-automation==1.1.0b4
azure-mgmt-iothub==3.0.0
azure-iot-hub==2.6.1;platform_machine=="x86_64"
azure-mgmt-recoveryservices==3.0.0
azure-mgmt-recoveryservicesbackup==9.1.0
azure-mgmt-notificationhubs==8.1.0b1
azure-mgmt-eventhub==11.1.0
azure-mgmt-resourcehealth==1.0.0b6
oras
netaddr

# If you're using python3.11
$ pip3.11 install -r requirements.txt
```
