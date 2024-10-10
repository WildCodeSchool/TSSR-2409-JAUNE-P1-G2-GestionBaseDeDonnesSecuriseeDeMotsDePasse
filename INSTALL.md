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



# Etapes d'installation et configuration Windows 10


### Choix des langues


![[langue.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/langue.png)

- Une fois que le PC démarre, la première étape consiste à choisir vos préférences linguistiques.
- Puis cliquez sur installer maintenant.

## Licence et version de Windows

Une fenêtre Activer Windows s'ouvre alors et plusieurs options sont possibles : soit vous avez une clé produit (licence) et n'avez qu'à entrer son code
Une clé de produit est un code de 25 chiffres qui se présente sous la forme suivante :

CLÉ DE PRODUIT : XXXXX-XXXXX-XXXXX-XXXXX-XXXXX

Pendant l’installation, vous êtes invité à entrer une clé de produit.



### Lancer l'installation


![[choix os.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/choix%20os.png)

Sélectionnez ensuite la version de Windows qui vous convient, Windows Famille étant le choix recommandé pour les particuliers.

Acceptez les termes du contrat


### Choix de la destination de l'installation


![[installation disque.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/installation%20disque.png)


Choisissez ensuite Personnalisé : installer uniquement Windows (avancé).


![[espace alloué.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/espace%20allou%C3%A9.png)

À la demande *Où souhaitez-vous installer Windows ?”*, plusieurs options sont possibles :

- Si votre disque est vide, sélectionnez-le et cliquez sur Suivant  
- S'il ne l'est pas, choisissez le lecteur principal et cliquez sur Formater, puis Suivant (attention, vous perdrez les données du lecteur en question, ce qui ne devrait normalement pas poser de problème).


![[instal.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/instal.png)

L'installation de Windows se lance et vous n'avez plus qu'à attendre qu'elle s'achève.


## Configurer Windows 10


### Choix des langues



![[choix langue 2.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/choix%20langue%202.png)

- Sélectionnez votre pays.


![[clavier.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/clavier.png)

- puis votre disposition de clavier.


![[clavier secondaire.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/clavier%20secondaire.png)

- et éventuellement une seconde disposition.



![[ajout compte.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/ajout%20compte.png)

- L'étape suivante exige la création d'un compte Microsoft ou, le cas échéant, de s'identifier avec celui dont vous disposez. Cliquez sur *compte hors connexion* pour s'en affranchir.



![[nom utilisateur.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/nom%20utilisateur.png)

- Créer votre nom d'utilisateur et cliquez sur suivant.



![[mot de passe.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/mot%20de%20passe.png)


- Définissez un mot de passe pour votre ordinateur.

-  Il faudra ensuite choisir si vous souhaiter activer différents services.
- Windows prend enfin quelques minutes pour se configurer.
- Passé ces minutes, le Bureau de Windows 10 s'affiche et l'ordinateur est prêt à être utilisé.


### Configuration du poste client


![[adittion invité.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/adittion%20invit%C3%A9.png)

- Dans l'onglet Périphériques de VirtualBox, insérer l'image CD des Additions invité.


![[localisation .exe guest.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/localisation%20.exe%20guest.png)

- Chercher ensuite le lecteur créer VirtualBox Guest Additions et sélectionner a l'intérieur l'exécutable VBoxWindowsAdditions. Ensuite appuyé sur next et installer et Windows redémarrera automatiquement.


### Configuration réseau



![[réseau 1.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/r%C3%A9seau%201.png)

- cliquez sur **Réseau et Internet** depuis les paramètres de Windows 10


![[réseau 2.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/r%C3%A9seau%202.png)

- Cliquez sur *Modifier les options d'adaptateur*


![[réseau 3.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/r%C3%A9seau%203.png)

- Cliquez sur les propriétés de votre carte réseau.


![[réseau 4.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/r%C3%A9seau%204.png)

- double cliquez sur *Protocole Internet version 4* 


![[réseau 5.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/r%C3%A9seau%205.png)

- Cliquez sur *Utilisez l'adresse IP suivante* et insérez l'adresse ip. ainsi que le masque de sous réseau fournit.


### Connexion au serveur


- Dans les paramètres, cliquez sur *Réseau et Internet* , *accès à distance* puis sur *centre Réseau et partage*.
- Cliquez sur *Modifier les paramètres de partage avancés* et vérifié que la Recherche réseau et le partage de fichiers, d'imprimante et le Partage protégé par mot de passe soit activés.

- Ensuite ouvrez l'explorateur de fichiers et tapez l'adresse du serveur avec le nom du dossier comme dans la démonstration ci dessous.
-
- ![[accès serveur.png]](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P1-G2-GestionBaseDeDonnesSecuriseeDeMotsDePasse/blob/A-verifier/image%20install%20win%2010/acc%C3%A8s%20serveur.png)
- 
