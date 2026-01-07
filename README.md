# Déploiement de Zabbix conteneurisé sur AWS
## Supervision d’un parc hybride (Linux & Windows)

## 📌 Présentation du projet
Ce dépôt contient les éléments liés au projet académique réalisé dans le cadre du module **Cloud Computing et Virtualisation** à l’Université de Mundiapolis.

L’objectif du projet est de mettre en œuvre une **infrastructure cloud de supervision centralisée** sur **AWS**, en utilisant **Zabbix déployé via Docker**, afin de monitorer un parc informatique **hybride** composé de machines **Linux** et **Windows**.

## 🧑‍🎓 Informations générales
- **Étudiante** : Zeineb BOUZERDA  
- **Encadrant** : Prof. Azeddine KHIAT  
- **Année universitaire** : 2025 / 2026  
- **Sujet** : Déploiement de Zabbix conteneurisé pour le monitoring d’un parc hybride  

## 🏗️ Architecture globale
L’infrastructure repose sur les composants AWS suivants :
- VPC personnalisé
- Sous-réseau public (serveur Zabbix)
- Internet Gateway et table de routage
- Security Groups (ports restreints)
- Instances EC2 :
  - Serveur Zabbix (Ubuntu 22.04)
  - Client Linux (Ubuntu 22.04)
  - Client Windows (Windows Server 2019)

Zabbix est déployé sous forme de conteneurs Docker (Server, Web, Database).

## ⚙️ Technologies utilisées
- AWS : EC2, VPC, Subnets, Security Groups, Internet Gateway  
- Zabbix  
- Docker & Docker Compose  
- Ubuntu 22.04 LTS  
- Windows Server 2019  

## 📂 Contenu du dépôt
.
├── docker-compose.yml
├── README.md
└── rapport/
    └── rapport-projet.pdf

## 🚀 Déploiement du serveur Zabbix
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y docker.io docker-compose
docker-compose up -d
```

## 🖥️ Configuration des agents
### Client Linux
- Installation de l’agent Zabbix
- Configuration du fichier `/etc/zabbix/zabbix_agentd.conf`
- Définition de l’IP du serveur Zabbix

### Client Windows
- Installation via le package MSI officiel Zabbix

## ✅ Tests et résultats
- Détection automatique des hôtes
- Statut ZBX vert
- Visualisation des métriques CPU, Mémoire et Disque

## 🏁 Conclusion
Ce projet valide la mise en place d’une supervision centralisée sur AWS à l’aide de Zabbix conteneurisé, adaptée à un environnement hybride.

