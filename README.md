# Network Attack and Defense Simulation

## English Version

## Introduction
This project aims to simulate network attacks and defenses using widely used, powerful tools. It includes the setup, execution, and analysis of common cyber attacks and defenses in a virtualized environment.

## Objectives
- Simulate common network attacks (DDoS, Man-in-the-Middle, SQL Injection)
- Implement network defenses (firewall, IDS/IPS, WAF)
- Analyze and document the results

## Prerequisites
- VirtualBox
- Kali Linux ISO
- Ubuntu Server ISO
- Security Onion ISO
- Basic knowledge of networking and cybersecurity

## Resources

### Download ISO Files

Please download the following ISO files and place them in the `resources` directory:

1. **Kali Linux ISO**
   - [Kali Linux Downloads](https://www.kali.org/get-kali/)
   - Download the appropriate version for your needs and place the ISO file in the `resources` directory.

2. **Ubuntu Server ISO**
   - [Ubuntu Server Download](https://ubuntu.com/download/server)
   - Download the LTS version for stability and place the ISO file in the `resources` directory.

3. **Security Onion ISO**
   - [Security Onion Downloads](https://securityonionsolutions.com/software/)
   - Download the latest version and place the ISO file in the `resources` directory.


## Installation

### Step 1: Install VirtualBox
Download and install VirtualBox from [VirtualBox official site](https://www.virtualbox.org/).

### Step 2: Setup Virtual Machines
1. **VM 1: Attacker (Kali Linux)**
   - Download the Kali Linux ISO and create a VM in VirtualBox.
2. **VM 2: Victim Server (Ubuntu Server)**
   - Download the Ubuntu Server ISO and create a VM.
3. **VM 3: Defense (Security Onion)**
   - Download the Security Onion ISO and create a VM.

### Step 3: Configure Network
1. Configure an internal network in VirtualBox to allow communication between VMs.
2. Assign static IP addresses to the VMs.

## Usage

### Simulating Attacks

#### DDoS Attack
- **Tool:** hping3
  - Command: `hping3 -S --flood -V <IP_VICTIM>`
- **Analysis:** Use Wireshark on the victim machine to capture traffic.

#### Man-in-the-Middle (MITM)
- **Tool:** ettercap
  - Command: `ettercap -T -q -M arp:remote /<IP_VICTIM>/ /<IP_GATEWAY>/`
- **Analysis:** Use Wireshark to inspect intercepted packets.

#### SQL Injection
- **Tool:** sqlmap
  - Command: `sqlmap -u "http://<IP_VICTIM>/vulnerable_page.php?id=1" --dbs`
- **Analysis:** Check database logs for injection attempts.

### Implementing Defenses

#### Firewall (PFsense)
- **Installation:** Install PFsense on the defense VM.
- **Configuration:** Configure rules to block suspicious IP addresses and limit traffic.

#### Intrusion Detection System (Snort)
- **Installation:** Install Snort on Security Onion.
- **Configuration:** Set rules to detect DDoS, MITM, and SQL Injection attacks.

#### Brute Force Protection (fail2ban)
- **Installation:** Install fail2ban on the Ubuntu server.
- **Configuration:** Monitor logs and block IPs after several failed login attempts.

## Contributing
Contributions are welcome! Please fork this repository and submit a pull request with your changes.

## License
This project is licensed under the Apache License 2.0 - see the LICENSE file for details.

## Contact
For any questions or suggestions, please contact [Tom Souillard](mailto:tom.souillard@gmail.com).
____
## Version Française

# Simulation de Réseaux avec Attaques et Défenses

## Introduction
Ce projet vise à simuler des attaques et des défenses réseau en utilisant des outils puissants et couramment utilisés. Il inclut la configuration, l'exécution et l'analyse d'attaques et de défenses courantes dans un environnement virtualisé.

## Objectifs
- Simuler des attaques réseau courantes (DDoS, Man-in-the-Middle, SQL Injection)
- Mettre en place des défenses réseau (pare-feu, IDS/IPS, WAF)
- Analyser et documenter les résultats

## Prérequis
- VirtualBox
- ISO de Kali Linux
- ISO d'Ubuntu Server
- ISO de Security Onion
- Connaissances de base en réseau et cybersécurité

## Ressources

### Télécharger les fichiers ISO

Veuillez télécharger les fichiers ISO suivants et placez-les dans le répertoire « ressources » :

1. **ISO Kali Linux**
    - [Téléchargements Kali Linux](https://www.kali.org/get-kali/)
    - Téléchargez la version adaptée à vos besoins et placez le fichier ISO dans le répertoire `ressources`.

2. **ISO du serveur Ubuntu**
    - [Téléchargement du serveur Ubuntu](https://ubuntu.com/download/server)
    - Téléchargez la version LTS pour plus de stabilité et placez le fichier ISO dans le répertoire « ressources ».

3. **Sécurité Oignon ISO**
    - [Téléchargements Security Onion](https://securityonionsolutions.com/software/)
    - Téléchargez la dernière version et placez le fichier ISO dans le répertoire « ressources ».

## Installation

### Étape 1 : Installer VirtualBox
Téléchargez et installez VirtualBox depuis [le site officiel de VirtualBox](https://www.virtualbox.org/).

### Étape 2 : Configuration des Machines Virtuelles
1. **VM 1 : Attaquant (Kali Linux)**
   - Téléchargez l'ISO de Kali Linux et créez une VM dans VirtualBox.
2. **VM 2 : Serveur Victime (Ubuntu Server)**
   - Téléchargez l'ISO d'Ubuntu Server et créez une VM.
3. **VM 3 : Défense (Security Onion)**
   - Téléchargez l'ISO de Security Onion et créez une VM.

### Étape 3 : Configuration Réseau
1. Configurez un réseau interne dans VirtualBox pour permettre la communication entre les VM.
2. Attribuez des adresses IP statiques aux VM.

## Utilisation

### Simulation des Attaques

#### Attaque DDoS
- **Outil :** hping3
  - Commande : `hping3 -S --flood -V <IP_VICTIM>`
- **Analyse :** Utilisez Wireshark sur la machine victime pour capturer le trafic.

#### Man-in-the-Middle (MITM)
- **Outil :** ettercap
  - Commande : `ettercap -T -q -M arp:remote /<IP_VICTIM>/ /<IP_GATEWAY>/`
- **Analyse :** Utilisez Wireshark pour inspecter les paquets interceptés.

#### Injection SQL
- **Outil :** sqlmap
  - Commande : `sqlmap -u "http://<IP_VICTIM>/vulnerable_page.php?id=1" --dbs`
- **Analyse :** Vérifiez les journaux de la base de données pour les tentatives d'injection.

### Mise en Place des Défenses

#### Pare-feu (PFsense)
- **Installation :** Installez PFsense sur la VM de défense.
- **Configuration :** Configurez les règles pour bloquer les adresses IP suspectes et limiter le trafic.

#### Système de Détection d'Intrusion (Snort)
- **Installation :** Installez Snort sur Security Onion.
- **Configuration :** Définissez des règles pour détecter les attaques DDoS, MITM et SQL Injection.

#### Protection contre les Attaques par Force Brute (fail2ban)
- **Installation :** Installez fail2ban sur le serveur Ubuntu.
- **Configuration :** Surveillez les journaux et bloquez les IP après plusieurs tentatives de connexion échouées.

## Contribuer
Les contributions sont les bienvenues ! Veuillez forker ce dépôt et soumettre une pull request avec vos modifications.

## Licence
Ce projet est sous licence Apache Licence 2.0 - voir le fichier LICENSE pour plus de détails.

## Contact
Pour toute question ou suggestion, veuillez contacter [Tom Souillard](mailto:tom.souillard@gmail.com).
