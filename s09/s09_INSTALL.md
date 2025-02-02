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
![](screen1)

Pour la configuration rendez vous dans `Computer Configuration > Policies > Software Settings > Software installation` puis clic droit `New > Package...`. 
![](screen1)

Sélectionner le fichier d'installation .msi , choissisez l'option `Assigned` et validez. 

Assurez vous que la source du programme est bien un chemin UNC et qu'il est accesible sur le réseau.

Il ne reste plus qu'à lier la GPO aux différentes cibles.





