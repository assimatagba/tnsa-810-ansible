# TNA-810-Ansible-Config

## Installer Ansible

https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

## 1- Modifier le ficher hosts
###  Ajouter les adresses ip des machines
  
  --> address_ip ansible_user=machine_user
  
## 2- Modifier le ficher playbook.yml

###  Ajouter les adresses ip des machines
  hosts: address_ip_machine
  
  Voir les configs dans le fichier playbook.yml
 
## Si plusieurs machines front ajouter un autre hosts avec l'addresse ip correspondant
### Voir l'exemple dans le fichier playbook.yml

## 3- Generer une ssh-key

  $ ssh-keygen
  
  $ ssh-copy-id machine_user@address_ip_1
  
  $ ssh-copy-id machine_user@address_ip_2
  
  ... Si plusieurs machines
  
  ### Pour eviter de saisir le passphrase ssh a chaque fois
  
  $ exec ssh-agent bash
  
  $ ssh-add
  
  Enter passphrase for ~/.ssh/id_rsa: ton_passphrase
  
## 4- Lancer ansible

  - Tester le ping 

Reponse ping: 

10.101.53.202 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python"
    },
    "changed": false,
    "ping": "pong"
}
10.101.53.201 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python"
    },
    "changed": false,
    "ping": "pong"
}
  
 $ ansible -m ping all
 
 - Lancer ansible-playbook

 $ ansible-playbook -K playbook.yml
