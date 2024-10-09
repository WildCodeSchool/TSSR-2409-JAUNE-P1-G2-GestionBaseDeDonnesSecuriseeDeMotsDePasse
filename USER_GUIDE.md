

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

- Et, bien sûr, il faut installer sur le PC un logiciel de virtualisation, nous avons retenu le logiciel [VirtualBox]((https://www.virtualbox.org/wiki/Downloads)  d'Oracle. Disponible gratuitement, en français, il se montre simple à mettre en place et à utiliser.
- Les images iso de [Windows 10](https://www.microsoft.com/fr-fr/software-download/windows10), [Windows server](https://www.microsoft.com/fr-fr/evalcenter/download-windows-server-2022) et [Ubuntu](https://www.ubuntu-fr.org/download/).
- Il nous faut également le logiciel [Keepass](https://keepass.info/download.html), indispensable pour chiffrer les mots de passe.
