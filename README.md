# Base de données chiffrée avec KeePass
## Présentation du Projet

Ce projet a pour objectif de mettre en place une solution de gestion de mots de passe centralisée, sécurisée et accessible à partir de plusieurs systèmes d'exploitation. L'idée est d'héberger une base de données chiffrée sur un serveur [**Windows Server 2022**](https://www.microsoft.com/fr-fr/windows-server), tout en permettant aux utilisateurs, sous [**Windows 10**](https://www.microsoft.com/fr-fr/software-download/windows10) ou [**Ubuntu 22**](https://www.ubuntu-fr.org/), d'y accéder de manière sécurisée grâce à l'application [**KeePass**](https://keepass.info/).

### Objectifs

- **Objectif principal** :
  - Créer une base de données chiffrée et sécurisée par une clé, qui sera accessible à partir de plusieurs clients via le logiciel KeePass.
  - Le serveur hébergeant la base de données est un **Windows Server 2022**.
  - Les clients qui accéderont à cette base de données seront sous **Windows 10**.
  
- **Objectif secondaire** : Tester l’accès depuis un second client utilisant un système d’exploitation **Ubuntu 22** pour valider la compatibilité multi-plateforme.

## Introduction et Contexte

Dans un environnement où la sécurité des informations sensibles est une priorité, la gestion centralisée des mots de passe devient une nécessité. KeePass, un gestionnaire de mots de passe [open-source](https://fr.wikipedia.org/wiki/Open_source), permet de créer une base de données chiffrée qui peut être partagée entre plusieurs utilisateurs, tout en assurant un haut niveau de sécurité grâce à des technologies de chiffrement robustes (comme [AES-256](https://www.malekal.com/quest-ce-que-le-chiffrement-aes-et-comment-ca-marche/)).

Le projet consiste à implémenter cette solution dans un environnement multi-systèmes, avec un **serveur** Windows centralisé pour l’hébergement de la base de données, et des **clients** sous différents systèmes d'exploitation pouvant accéder à cette base. Ce modèle vise à offrir une gestion centralisée et sécurisée des identifiants et des mots de passe, tout en permettant aux utilisateurs d'accéder à cette base à distance et de manière sécurisée, quelle que soit leur système d'exploitation.

---

## Rôles de chaque membre
### Sprint 1
- Product Owner : Anthony
- Scrum Master  : P.A.

### Sprint 2
- Product Owner : Sam
- Scrum Master  : Matthias

## Choix techniques

1. **Cryptage et Gestion de la Base de Données**

- **Choix :** Application de mots de passe KeePass.
- **Explication :** Pour créer une base de données chiffrée, nous allons utiliser **KeePass**. KeePass utilise un algorithme de cryptage puissant comme **AES (clé de 256 bits)** et **TwoFish (clé de 256 bits + blocs de 128 bits)** pour sécuriser la base de données. Les mots de passe seront stockés dans cette base de données et conservés sous forme de fichier chiffré sur le serveur.
  
2.  **Plateforme Serveur**

- **Choix :** Windows Server 2022. (**SRVWIN01**)
- **Explication :** La base de données sera hébergée sur **Windows Server 2022**. Le serveur sera configuré avec des mesures de sécurité appropriées pour permettre l'accès des clients.
  
3.  **Plateformes Clients**

- **Choix :** Différents systèmes d'exploitation (Windows, Ubuntu).
- **Explication :** La base de données KeePass sera accessible depuis plusieurs systèmes d'exploitation. Chaque système pourra utiliser KeePass.
  
4.  **Accès Client-Serveur**

- **Choix :** Partage de fichiers (172.16.10.10/24).
- **Explication :** Les clients accéderont à la base de données chiffrée par le biais d'un partage de fichiers sur le réseau. Cette méthode a été retenue car elle centralise la gestion de la base de données dans un seul fichier, renforçant ainsi la sécurité. De plus, elle offre un accès sécurisé aux utilisateurs sans qu'une configuration complexe ne soit nécessaire.

## Tableau Difficultés / Solutions

| Difficultés rencontrées                                                                                                                                                                                                                           | Solutions envisagées                                                                                                                                                                                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Partage de fichier**<br>Pour la réalisation du projet, un fichier devait être partagé entre un serveur et plusieurs clients.                                                                                                                    | - Windows : Monter le répertoire partagé via un connecteur réseau. <br><br>- Linux : Monter le répertoire partagé en graphique via *smb*.                                                                                                                                                                                 |
| **Communication entre les ordinateurs**<br>Les clients ne parvenaient pas toujours à communiquer avec le serveur.                                                                                                                                 | - Assurer la configuration des adresses IPv4.<br>- Assurer la bonne nomination des machines.<br>- Assurer que les VMs soient bien connectées en réseau interne au **même** réseau<br>- Vérifier la désactivation des pare-feux.<br>- Activer la découverte de réseaux.<br>- Activer le partage de fichiers..              |
| **Montage du répertoire partagé au démarrage du client Ubuntu**<br>Le montage du répertoire partagé est effectif et l'objectif du projet atteint mais celui-ci a besoin d'être monté de nouveau à chaque ouverture de session utilisateur Ubuntu. | - Intégration d'un script de montage au démarrage avec un fichier *crontab*<br>- Utilisation de l'extension *Autofs*<br>- Ajout d'un script de montage parmi les services lancés au démarrage via le *systemd*<br><br>Aucune de ces tentatives n'a offert de résultat satisfaisant faute de maîtrise des outils proposés. |

## Suggestions d'amélioration
- Automatiser le montage du répertoire partagé sur le client Ubuntu ;
- Sécuriser l'accès à la base de données partagée en utilisant un login de service pour le montage du répertoire partagé ;
- Affiner les droits sur la base de données partagée selon les besoins (Lecture et Exécution peuvent être suffisants) ;
