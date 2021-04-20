# TNA-810-Ansible-Config

## Installer Ansible

https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

## 1- Modifier le ficher hosts
###  Ajouter les adresses ip des machines
  
  --> address_ip ansible_user=machine_user
  
## 2- Modifier le ficher playbook.yml

###  Ajouter les adresses ip des machines
  
  "- hosts: address_ip_front_i
    become: true
    roles:
      - frontend"

  - hosts: address_ip_back
      become: true
      roles:
        - backend
 
## Si plusieurs machines front ajouter un autre hosts avec l'addresse ip correspondant
### Exemple : 
  - hosts: address_ip_front_1
    become: true
    roles:
      - frontend
      - 
  - hosts: address_ip_front_2
    become: true
    roles:
      - frontend
  ...
