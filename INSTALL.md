Doc_Admin


## Etapes d'installation et Configuration Serveur
___
### Choix linguistiques
![[Pasted image 20241009164712.png]]
- Langage d'installation : English (U.S.)
- Heure et devise : French (France)
	- Attention : il y a plusieurs French, bien choisir celui de la France ;
- Configuration clavier : French

### Lancer l'installation
- Sélection du système d'exploitation :
	![[Pasted image 20241009170739.png]]
	- Sélectionner la version Standard avec Expérience utilisateur (*Standard Evaluation (Desktop Experience)* - en anglais) puis cliquer sur Next ;
		 Nous ne sommes pas sur une configuration Datacenter et une interface graphique est préférable ;
	- Cocher la case pour accepter les termes du contrat de licence puis cliquer sur Next ;
- Choisir le type d'installation : Custom
	![[Pasted image 20241009171918.png]]
	- Laisser la configuration par défaut et appuyer sur Next :
		![[Pasted image 20241009172105.png]]
- Le système s'installe :
	![[Pasted image 20241009172140.png]]
- Définition du mot de passe :
	- Le nom d'utilisateur est obligatoirement : Administrator
	- Définir le mot de passe par défaut : Azerty1*

### Configuration Serveur
- Découverte de réseaux : confirmer la découverte de la machine par les autres machines du réseau ;
	![[Pasted image 20241009174703.png]]
- Installation des Guest Additions :
	- Dans l'onglet Périphériques de VirtualBox, insérer l'image CD des Additions invité ;
![[Pasted image 20241009175000.png]]
- Lancer VBoxWindowsAdditions.exe
	![[Pasted image 20241009175136.png]]
	- Laisser toutes les configurations par défaut en appuyant sur Next jusqu'à l'installation des additions puis laisser le serveur redémarrer (Reboot now) avant de cliquer sur Finish ;

- Désactivation du Pare-feu
	- Après le redémarrage, se rendre dans l'onglet Local Server du Server Manager puis cliquer sur "Public : On, Private : On" :
	![[Pasted image 20241009175714.png]]
	- Successivement sur les pages "Domain network", "Private network" et "Public network", entrer et désactiver les pare-feu en passant le bouton sur Off
		![[Pasted image 20241009180236.png]]
	- Jusqu'à atteindre cet état sur les trois pare-feu : 
		![[Pasted image 20241009180327.png]]

- Activer la découverte de réseaux et le partage de fichiers :
	- Dans la barre de recherche windows, rechercher "Manage advanced sharing settings" ;
	- Pour chaque onglet "Private", "Guest or Public" et "All Networks", activer les boutons "Turn on network discovery" et "Turn on file and printer sharing" :
		![[Pasted image 20241009180655.png]]
	- Puis cliquer sur "Save changes" ;

- Configuration de la carte réseau :
	- Avec la commande Windows+R, entrer "ncpa.cpl" pour ouvrir la modification des connecteurs réseaux :
		![[Pasted image 20241009181031.png]]
	- Entrer dans les propriétés de la carte réseau connectée au réseau interne, ici la carte Ethernet 2 ;
	- Entrer dans les propriétés de la ligne "IPv4" :
		![[Pasted image 20241009181217.png]]
	- Et définir l'adresse IP en 172.16.10.10 et le masque de sous-réseau en 255.255.255.0 :
		![[Pasted image 20241009181307.png]]

- Redémarrer une dernière fois la machine pour prendre en compte tous les changements effectués.
- Votre machine est prête à être mise en réseau. Dans les étapes suivantes, nous installerons le logiciel KeePass et détaillerons le partage de fichier nécessaire pour un accès client.
