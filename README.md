# rhev-install
The Goal of this project is to build a pxe boot server to install RHEV and then install RHEV-Manager
A host is needed to run this ansible commands

Ansible tasks
-	Register host with Red Hat
-	Setup Kickstart file
-	Setup http server
-	Setup DHCP
-	Setup DNS

Create ssh key
```diff
ssh-keygen -t rsa -b 4096
echo "eval `ssh-agent`; ssh-add" >> ~/.bash_profile
```
1.	Create a password file for the ansible vault:
```diff
$ vi ../vault_pw_file
```
2.	Create Ansible vault and add subscription information:
a.	Add rhnUserID and rhnUserPass
```diff
$ ansible-vault create group_vars/all/vault.yaml
	vault_rhnUserID: #######
    vault_rhnUserPass: #######
```
e.	ansible
