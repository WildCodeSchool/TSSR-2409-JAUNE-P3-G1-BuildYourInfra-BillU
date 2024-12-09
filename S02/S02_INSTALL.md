
# Documentation Administrateur 

## 1. Prérequis Techniques 

### 1.1 Prérequis Active Directory 

- Avoir un serveur Windows 2022 en graphique

### Prérequis pour Windows serveur 2022

Environment de test sur Proxmox en VM

* Memory      4 GB
    
* Processors  2 
    
* Reseau      vmbr525

* IP de réseau     : 172.18.0.0/16 
  
* IP de passerelle : 172.18.255.254 
  
* IP DNS           : 172.15.255.254 

## 2. Installation Active Directory

Choisir le serveur cible dans l'interface de Server Manager. 

![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/3ce96eab545432bb39b253f41d960e9c5f3856f6/Resources/choix%20du%20serveur.png)

Puis, allez dans `Manage` > `Add Roles and Festures`

![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/3ce96eab545432bb39b253f41d960e9c5f3856f6/Resources/Manage%20add%20roles.png)

   
   Choisir le serveur

   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/3ce96eab545432bb39b253f41d960e9c5f3856f6/Resources/choix%20des%20roles.png)

   Choisir les roles à installer
   sceen role 

   Vérifier l'isntallation de la feature `Group Policy Management`
   Screen
   Redémarrarez puis commencez la configuration post instalaltion. 
   Screen
   Donnez un nom à votre nouveau domaine Active Directory.
   Screen
   Choissiez le niveau fonctionnel le plus élévé pour votre domaine et votre forêt
   Screen
   Laissez les chemins par défauts pour les dossiers `NTDS` & `SYSVOL`
   Screen

   Continuez l'instalaltion jusqu'à l'écran de vérifications finales puis finalisez l'isntalaltion
   screen
   
   
## 3. Ajout d'un serveur Windows Core à un serveur Windows graphique
## 4. Créer une Unité organisationnelle et des groupes de sécurités sur Active Directory

   

   
  

    



