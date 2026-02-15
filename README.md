🚀 Ansible Installation & Deployment Guide

Ce dépôt contient les playbooks et rôles Ansible nécessaires pour configurer et déployer l'infrastructure.

📦 Prérequis

Avant de commencer, assure-toi d’avoir :

Python 3.x

Pip

SSH installé et configuré

Un accès sudo sur les machines cibles

Installer Ansible
🐧 Linux / macOS
sudo apt update
sudo apt install ansible -y


ou via pip :

pip install ansible

🪟 Windows

Utiliser WSL (Windows Subsystem for Linux) recommandé.

Installer via pip :

pip install ansible


Vérifier l’installation :

ansible --version

📁 Structure du projet
.
├── inventories/
│   ├── production/
│   └── staging/
├── roles/
├── playbooks/
├── group_vars/
├── host_vars/
└── ansible.cfg

⚙️ Configuration
1️⃣ Cloner le projet
git clone https://github.com/ton-utilisateur/ton-repo.git
cd ton-repo

2️⃣ Configurer l’inventaire

Modifier le fichier :

inventories/production/hosts


Exemple :

[web]
192.168.1.10

[db]
192.168.1.20

🔐 Gestion des clés SSH

Si nécessaire :

ssh-keygen
ssh-copy-id user@server

▶️ Exécuter un playbook
ansible-playbook -i inventories/production/hosts playbooks/site.yml

🧪 Test de connexion
ansible all -i inventories/production/hosts -m ping

📚 Bonnes pratiques

Utiliser des rôles pour modulariser

Séparer staging / production

Utiliser Ansible Vault pour les secrets :

ansible-vault encrypt group_vars/all.yml

🛠️ Commandes utiles

Lister les hosts :

ansible all --list-hosts -i inventories/production/hosts


Exécuter une commande :

ansible all -i inventories/production/hosts -a "uptime"

🤝 Contribution

Fork le projet

Créer une branche

Faire une Pull Request
