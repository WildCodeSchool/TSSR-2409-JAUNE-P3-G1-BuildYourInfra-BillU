## Prérequis

Contenaire Debian 12

Environnent de test sur Proxmox en VM

  Memory 2 GB

  Processors 2

  Réseau vmbr525

  Adresse IP de réseau : 172.18.0.25/16

  Adresse IP de passerelle : 172.18.255.254

  Adresse IP du DNS : 172.18.0.1

 ## VOIP - Mettre en place un serveur de téléphonie sur IP


 ### Mise en place d'une GPO pour 3CX 

 Préreuqis : avoir télécharger le fichier d'installation 3CXPhone .msi svur le lien suivant ![lien](https://www.3cx.fr/voip-telephone/softphone/)
 
La GPO pour déployer 3CX 

![](../Ressources/S09/3cx_3.png)

Pour la configuration rendez vous dans `Computer Configuration > Policies > Software Settings > Software installation` puis clic droit `New > Package...`

![](../Ressources/S09/3cx_1.png)

Sélectionner le fichier d'installation .msi , choissisez l'option `Assigned` et validez. 

Assurez vous que la source du programme est bien un chemin UNC et qu'il est accesible sur le réseau.

![](../Ressources/S09/3cx_2.png)

Il ne reste plus qu'à lier la GPO aux différentes cibles.


## Installation de Windows Server Backup

Installation de la fonctionnalité WSB depuis le server manager, Manage, add roles and features.
Pour assurer la sauvegarde de notre AD on a choisi d'installer un nouveau serveur core équipé de disk en RAID1 par soucis de fiabilité.

![](../Ressources/S09/S09WSB-1.png)

Une fois installé, nous devons configurer WSB pour réaliser la sauvegarde de l'AD. Depuis le server manager, dans all server, faire un clique droit sur le serveur core destiné à héberger la sauvegarde et choisir Computer Management.
  
![](../Ressources/S09/S09WSB-2.png)
  
Double cliquer sur Local Backup et choisir Backup Schedule puis configurer les paramètres de sauvegarde dans la fenêtre d'aide
  
![](../Ressources/S09/S09WSB-3.png)
  
Next
  
![](../Ressources/S09/S09WSB-4.png)
  
Nous choisissons une sauvegarde complète de notre AD
  
![](../Ressources/S09/S09WSB-5.png)

Paramètrer le moment de la réalisation de la sauvegarde.
  
![](../Ressources/S09/S09WSB-6.png)

On choisi d'effectuer la sauvegarde sur un disque dédié 


## FAQ:



