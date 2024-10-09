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

## Difficultés / Solutions

## Suggestions d'amélioration

## Conclusion
