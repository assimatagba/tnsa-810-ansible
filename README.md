# TNA-810-Ansible-Config

## Installer Ansible

https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

## 1- Modifier le ficher hosts
###  Ajouter les adresses ip des machines
  
  --> address_ip ansible_user=machine_user
  
## 2- Modifier le ficher playbook.yml

###  Ajouter les adresses ip des machines
  
  --> hosts: address_ip
