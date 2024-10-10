# Base de données chiffrée avec KeePass

## Présentation du Projet

Ce projet a pour objectif de mettre en place une solution de gestion de mots de passe centralisée, sécurisée et accessible à partir de plusieurs systèmes d'exploitation. L'idée est d'héberger une base de données chiffrée sur un **serveur Windows Server 2022**, tout en permettant aux utilisateurs, sous **Windows** ou **Ubuntu**, d'y accéder de manière sécurisée grâce à l'application **KeePass**.

### Objectifs

- **Objectif principal** : Créer une base de données chiffrée et sécurisée par une clé, accessible à partir de plusieurs clients via le logiciel KeePass.
  - Le serveur hébergeant la base de données est un **Windows Server 2022**.
  - Les clients qui accéderont à cette base de données seront sous **Windows 10**
  
- **Objectif secondaire** : Tester l’accès depuis un second client utilisant un système d’exploitation **Ubuntu22** ou **Ubuntu24** pour valider la compatibilité multi-plateforme.

## Introduction et Contexte

Dans un environnement où la sécurité des informations sensibles est une priorité, la gestion centralisée des mots de passe devient une nécessité. KeePass, un gestionnaire de mots de passe open-source, permet de créer une base de données chiffrée qui peut être partagée entre plusieurs utilisateurs, tout en assurant un haut niveau de sécurité grâce à des technologies de chiffrement robustes (comme AES-256).

Le projet consiste à implémenter cette solution dans un environnement multi-système, avec un **serveur** Windows centralisé pour l’hébergement de la base de données, et des **clients** sous différents systèmes d'exploitation pouvant accéder à cette base. Ce modèle vise à offrir une gestion centralisée et sécurisée des identifiants et des mots de passe, tout en permettant aux utilisateurs d'accéder à cette base à distance et de manière sécurisée, quelle que soit leur système d'exploitation.

---

## Rôles de chaque membre
### Sprint 1
- Product Owner : Anthony
- Scrum Master : P.A.

### Sprint 2

## Choix techniques

   1. **Cryptage et Gestion de la Base de Données**

- **Choix :** Application de mots de passe KeePass.
- **Explication :** Pour créer une base de données chiffrée, nous allons utiliser **KeePass**. KeePass utilise un algorithme de cryptage puissant comme **AES (clé de 256 bits)** et **TwoFish (clé de 256 bits + blocs de 128 bits)** pour sécuriser la base de données. Les mots de passe seront stockés dans cette base de données et conservés sous forme de fichier chiffré sur le serveur.
  
   2. **Plateforme Serveur**

- **Choix :** Windows Server 2022. (**SRVWIN01**)
- **Explication :** La base de données sera hébergée sur **Windows Server 2022**. Le serveur sera configuré avec des mesures de sécurité appropriées pour permettre l'accès des clients.
  
   3. **Plateformes Clients**

- **Choix :** Différents systèmes d'exploitation (Windows, Ubuntu).
- **Explication :** La base de données KeePass sera accessible depuis plusieurs systèmes d'exploitation. Chaque système pourra utiliser KeePass ou KeePassXC (Ubuntu).
  
   4. **Accès Client-Serveur**

- **Choix :** Partage de fichiers (172.16.10.10/24).
- **Explication :** Les clients accéderont à la base de données chiffrée via le partage de fichiers sur un réseau. Cette méthode a été choisie car nous avons un seul fichier de base de données à gérer, ce qui rend cette approche plus simple et rapide à utiliser. Elle permet également aux utilisateurs d'accéder à la base de données en toute sécurité sans nécessiter de configuration complexe.

## Difficultés / Solutions

## Suggestions d'amélioration

## Conclusion
