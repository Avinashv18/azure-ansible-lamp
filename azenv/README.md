This directory contains the playbooks to deploy the Azure infrastructure, and delete temporary Ansible VM after it deploys the LAMP application stack. 

To change the base name of the Azure Resource Group and admin user name, change their variables in vars.yml

It initially deploys three Virtual Machines: Ansible, Web, and DB servers.  

It allocates public IPs and grants SSH access to the Ansible VM and HTTP access to the Web server VM.  

All Virtual Machines have passwords disabled, so access between the agent and the ansible vm or between the ansible vm and the web/db servers is done via ssh keys.

All authorized_keys are removed at the end of the process, and the Ansible VM, which is the only one that allows SSH access, is deleted as well.  Thus, the only way to access the infrastructure without re-triggering the Azure DevOps CI is to manually open the SSH port on the Web or DB servers and changing the key for admin user on the server.
