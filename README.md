# nopcommerce on Ubuntu 20.04 

This playbook will install a NopCommerce website on top of a Ubuntu 20.04 machine.
Please note - playbook could install multiple nopcommerce websites to your host. Just adjust http_envs variable

## Settings

- `mysql_root_password`: The desired password for the **root** MySQL account.
- `http_envs`: if you need to install multiple instances of wordpress.
- `nop_version`: specify version of nopcommerce

## Running this Playbook

Quickstart guide for those already familiar with Ansible:

### 1. Customize Options

```
vim vars/main.yml
---
#MySQL Settings
mysql_root_password: "mysql_root_password"

#HTTP Settings
http_envs: ['nopcommerce-dev', 'nopcommerce-qa']

#NopCommere Version
nop_version: "4.40.3"
```

### 2. Run the Playbook

```command
ansible-playbook -l [target] -i [inventory file] -u [remote user] playbook.yml
```

### 3. Obtain Let's Encrypt Certificates
```
certbot --nginx -d your_domain
```

### 4. Proceed with the nopccommerce setup

### 5. admin url: your_domain/admin
