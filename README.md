# Fluent-bit

This installs the Fluent-bit daemonset to forward logs to Elastic Search.

### Installation
```shell script
cd ansible
ansible-playbook --vault-password-file ~/vaultpwd ./playbook.yaml
```

#### Upgrade
```shell script
cd ansible
ansible-playbook --vault-password-file ~/vaultpwd ./upgrade.yaml
```
#### Removal
```shell script
cd ansible
ansible-playbook ./reset.yaml
```

#### A Note about Ansible Vault
We use Ansible Vault to encrypt our credentials.
If you don't have the password file, you won't be able to decrypt the vault.
However, you are more than welcome to create your own credentials.
Simply look in the vars.yaml file and create your own credentials as follows:
```shell script
echo 'YourVeryStrongPassword' > ~/vaultpass
ansible-vault encrypt_string --vault-password-file=~/vaultpass "StringToEncrypt" --name="NameOfCredential"
```