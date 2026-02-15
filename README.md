🚀 Ansible Infrastructure Automation


Infrastructure as Code (IaC) project built with Ansible for automated configuration management and deployment.

📖 Overview

This repository provides a structured and scalable Ansible setup including:

🔹 Reusable roles

🔹 Environment-based inventories (staging / production)

🔹 Modular playbooks

🔹 Centralized configuration via ansible.cfg

Designed for clean automation, reproducibility, and maintainability.

🧰 Requirements

Python 3.8+

Ansible 2.12+

SSH access to target machines

Sudo privileges on managed nodes

🔧 Install Ansible
Ubuntu / Debian
sudo apt update
sudo apt install ansible -y

Using pip
pip install ansible


Verify installation:

ansible --version

📂 Project Structure
.
├── inventories/
│   ├── production/
│   │   └── hosts
│   └── staging/
│       └── hosts
├── playbooks/
│   └── site.yml
├── roles/
├── group_vars/
├── host_vars/
└── ansible.cfg

🚀 Getting Started
1️⃣ Clone the repository
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>

2️⃣ Configure Inventory

Edit the desired inventory file:

inventories/production/hosts


Example:

[web]
192.168.1.10

[db]
192.168.1.20

3️⃣ Test Connectivity
ansible all -i inventories/production/hosts -m ping


Expected output:

SUCCESS

▶️ Run Playbooks
Production
ansible-playbook -i inventories/production/hosts playbooks/site.yml

Staging
ansible-playbook -i inventories/staging/hosts playbooks/site.yml

🔐 Secrets Management (Ansible Vault)

Encrypt sensitive files:

ansible-vault encrypt group_vars/all.yml


Run playbook with vault:

ansible-playbook playbooks/site.yml --ask-vault-pass

🧪 Useful Commands

List hosts:

ansible all --list-hosts -i inventories/production/hosts


Run an ad-hoc command:

ansible all -i inventories/production/hosts -a "uptime"


Check syntax:

ansible-playbook playbooks/site.yml --syntax-check


Dry run:

ansible-playbook playbooks/site.yml --check

🏗️ Best Practices

✔ Use roles for modular architecture
✔ Keep environments separated
✔ Encrypt secrets with Vault
✔ Ensure idempotency
✔ Version control everything
