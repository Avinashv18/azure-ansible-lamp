# azure-devops-ci-ansible-lamp-deployment
Automatic deployment of cloud infrastructure and LAMP application stack using Ansible and Azure DevOps CI

* logon to https://dev.azure.com/

* Create DevOps project

* Create Service Connection of the type Azure Resource Manager using "Service Principal (manual)" with the same name as in azure-pipelines.yml line 17. Use the following Azure CLI commands to get the information for the Service Connection:
   * __az account subscription list__ (for subscription id and name)
   * __az account show__ (for tenantid)
   * __az ad sp create-for-rbac --name your-sp-name__ (for Service Principal Id [appid] and Service Principal Key [password])

* Create a Pipeline pointing to your clone of this repository and save it.

* At a git prompt run __git commit --allow-empty -m "trigger ci"__ and __git push origin master__ to trigger the Azure DevOps Pipeline CI and deploy the cloud infrastructure and LAMP application stack.

During the execution of the playbooks you can follow the changes on Azure with CLI command for example, 
* az vm list
* az network nsg list
* az network nsg rule list
* az network public-ip list


After initial deployment you can further customize the infrastructure or the LAMP stack by commiting your changes to the code.

:smiley:
