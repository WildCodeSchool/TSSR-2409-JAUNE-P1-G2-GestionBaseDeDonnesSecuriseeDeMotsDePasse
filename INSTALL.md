# Installation


- Ce document explique comment installer Windows server, Windows10 Ubuntu et Keepass. Certaines étapes sont décrites en détails, afin de couvrir la grande variété des petites particularités des différentes installations et configurations. C'est pourquoi ce document vous semblera peut-être long et compliqué, mais il vous guidera étape par étape.

- Si vous avez des problèmes, prenez le temps d'étudier attentivement ces instructions : la plupart des difficultés y sont traitées. Si cela ne suffit pas, vous pouvez demander de l'aide à la communauté [Windows]( https://support.microsoft.com/fr-fr) ou [Linux](https://doc.ubuntu-fr.org/).

## Prérequis nécessaires

Keepass et Virtualbox sont principalement développés sur Linux, Windows.

### Matériel

Comme pour n'importe quel logiciel et système d'exploitation, ils nécessitent des systèmes performants, répondant aux exigences minimales ci-dessous, afin de proposer une expérience d'utilisation agréable.

|         | Mémoire | Stockage | processeur        |
| ------- | ------- | -------- | ----------------- |
| Minimum | 8Go     | 50Go     | double coeur 2GHz |
| Idéal   | 16Go    | 1To      | i5 3.2GHz         |

- Espace disque : Votre disque dur ou votre SSD doit disposer de suffisamment de place pour accueillir ce nouveau système, chaque machine virtuelle occupant un certain espace – plusieurs giga-octets.
- Mémoire :16 Go (préférable), 8 Go (minimum) pour un fonctionnement sans heurt.

En plus des prérequis matériels et logiciels, vous devrez aussi réfléchir à la capacité de votre installation, pour lancer deux machines virtuelles ensemble.
### Logiciel

- Et, bien sûr, il faut installer sur le PC un logiciel de virtualisation, nous avons retenu le logiciel [VirtualBox](https://www.virtualbox.org/wiki/Downloads)  d'Oracle. Disponible gratuitement, en français, il se montre simple à mettre en place et à utiliser.
- Les images iso de [Windows 10](https://www.microsoft.com/fr-fr/software-download/windows10), [Windows server](https://www.microsoft.com/fr-fr/evalcenter/download-windows-server-2022) et [Ubuntu](https://www.ubuntu-fr.org/download/).
- Il nous faut également le logiciel [Keepass](https://keepass.info/download.html), indispensable pour chiffrer les mots de passe.


## Etapes d'installation et Configuration Serveur
___
### Choix linguistiques

![TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/Install Server
/choixlangue.png](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/eae98cc50b090aae0a14f00268cf52440ff07e70/Install%20Server/choixlangue.png)
- Langage d'installation : English (U.S.)
- Heure et devise : French (France)
	- Attention : il y a plusieurs French, bien choisir celui de la France ;
- Configuration clavier : French

### Lancer l'installation
- Sélection du système d'exploitation :

	![[[Pasted image 20241009170739.png]]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/eae98cc50b090aae0a14f00268cf52440ff07e70/Install%20Server/choixos.png)
	- Sélectionner la version Standard avec Expérience utilisateur (*Standard Evaluation (Desktop Experience)* - en anglais) puis cliquer sur Next ;
		 Nous ne sommes pas sur une configuration Datacenter et une interface graphique est préférable ;
	- Cocher la case pour accepter les termes du contrat de licence puis cliquer sur Next ;
- Choisir le type d'installation : Custom

 ![[[Pasted image 20241009171918.png]]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/eae98cc50b090aae0a14f00268cf52440ff07e70/Install%20Server/typeinstall.png)

- Laisser la configuration par défaut et appuyer sur Next :

  ![[[Pasted image 20241009172105.png]]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/eae98cc50b090aae0a14f00268cf52440ff07e70/Install%20Server/configstock.png)
- Le système s'installe :

 ![[[Pasted image 20241009172140.png]]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/eae98cc50b090aae0a14f00268cf52440ff07e70/Install%20Server/install.png)
- Définition du mot de passe :
	- Le nom d'utilisateur est obligatoirement : Administrator
	- Définir le mot de passe par défaut : Azerty1*

### Configuration Serveur
- Découverte de réseaux : confirmer la découverte de la machine par les autres machines du réseau ;

 ![[[Pasted image 20241009174703.png]]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/eae98cc50b090aae0a14f00268cf52440ff07e70/Install%20Server/net.png)
- Installation des Guest Additions :
	- Dans l'onglet Périphériques de VirtualBox, insérer l'image CD des Additions invité ;

 ![[[Pasted image 20241009175000.png]]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/eae98cc50b090aae0a14f00268cf52440ff07e70/Install%20Server/addcd.png)

- Lancer VBoxWindowsAdditions.exe

	![[Pasted image 20241009175136.png](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/eae98cc50b090aae0a14f00268cf52440ff07e70/Install%20Server/vboxadd.png)](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/57c4446bdaa3aa201edbf339984b736ad6cf6eef/Install%20Server/vboxadd.png)

 	- Laisser toutes les configurations par défaut en appuyant sur Next jusqu'à l'installation des additions puis laisser le serveur redémarrer (Reboot now) avant de cliquer sur Finish ;

- Désactivation du Pare-feu
	- Après le redémarrage, se rendre dans l'onglet Local Server du Server Manager puis cliquer sur "Public : On, Private : On" :

 ![[[Pasted image 20241009175714.png]]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/eae98cc50b090aae0a14f00268cf52440ff07e70/Install%20Server/firewall.png)

 - Successivement sur les pages "Domain network", "Private network" et "Public network", entrer et désactiver les pare-feu en passant le bouton sur Off

  ![[[Pasted image 20241009180236.png]]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/eae98cc50b090aae0a14f00268cf52440ff07e70/Install%20Server/firedom.png)

 - Jusqu'à atteindre cet état sur les trois pare-feu :

 	![[[Pasted image 20241009180327.png]]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/eae98cc50b090aae0a14f00268cf52440ff07e70/Install%20Server/allfire.png)

- Activer la découverte de réseaux et le partage de fichiers :
	- Dans la barre de recherche windows, rechercher "Manage advanced sharing settings" ;
	- Pour chaque onglet "Private", "Guest or Public" et "All Networks", activer les boutons "Turn on network discovery" et "Turn on file and printer sharing" :

![[[Pasted image 20241009180655.png]]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/eae98cc50b090aae0a14f00268cf52440ff07e70/Install%20Server/share.png)

 - Puis cliquer sur "Save changes" ;

- Configuration de la carte réseau :
	- Avec la commande Windows+R, entrer "ncpa.cpl" pour ouvrir la modification des connecteurs réseaux :

  ![[[Pasted image 20241009181031.png]]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/eae98cc50b090aae0a14f00268cf52440ff07e70/Install%20Server/ncpa.png)

- Entrer dans les propriétés de la carte réseau connectée au réseau interne, ici la carte Ethernet 2 ;
- Entrer dans les propriétés de la ligne "IPv4" :
 
	![[[Pasted image 20241009181217.png]]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/eae98cc50b090aae0a14f00268cf52440ff07e70/Install%20Server/ipv4.png)

 - Et définir l'adresse IP en 172.16.10.10 et le masque de sous-réseau en 255.255.255.0 :

  ![[[Pasted image 20241009181307.png]]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/eae98cc50b090aae0a14f00268cf52440ff07e70/Install%20Server/address.png)

- Redémarrer une dernière fois la machine pour prendre en compte tous les changements effectués.
- Votre machine est prête à être mise en réseau. Dans les étapes suivantes, nous installerons le logiciel KeePass et détaillerons le partage de fichier nécessaire pour un accès client.
