# Ansible
Environnement de Test Ansible Sovi

# Ansible Lab - macOS

Ce dépôt contient un **lab Ansible** pour automatiser des tâches sur macOS et, si besoin, sur des VMs distantes via SSH.  
Vous trouverez des playbooks pour installer des logiciels, configurer le système, ou gérer des machines dans un domaine.

---

## 📦 Prérequis

Avant de commencer, assurez-vous que votre Mac dispose de :

- macOS à jour
- [Homebrew](https://brew.sh/) installé
- Git installé
- [Visual Studio Code](https://code.visualstudio.com/) (optionnel, recommandé)
- Connexion SSH si vous utilisez des VMs distantes

---

## 🛠 Installation d'Ansible

1. Installer Homebrew (si nécessaire) :

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install ansible
ansible --version



