
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

### Étape 1 : Connexion au serveur Windows Core
1. Connectez-vous au serveur Windows Core avec un compte administrateur local.
2. Tapez la commande `SConfig` dans l'invite de commande et appuyez sur Entrée.

    ![Sconfig](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/56fcfe942535d9f5b9fd5b683e1da38e8e58a018/Resources/s02/S02%20WinCORE%2001%20Sconfig.png)
    
### Étape 2 : Modifier le nom de l'ordinateur
1. Sur l'écran de configuration du serveur (*Server Configuration*), sélectionnez l'option **2** en tapant `2` pour modifier le nom de l'ordinateur.
2. Saisissez le nouveau nom (*WINCORE-1*) pour le serveur Core et appuyez sur Entrée. 
3. Redémarrez le serveur lorsqu'on vous le demande.

   ![SS2](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/56fcfe942535d9f5b9fd5b683e1da38e8e58a018/Resources/s02/S02%20WinCORE%2002%20computer%20name.png)

### Étape 3 : Rejoindre le domaine Active Directory
1. Après le redémarrage, reconnectez-vous au serveur et relancez `SConfig`.
2. Sélectionnez l'option **1** (*Domain/Workgroup*) en tapant `1`.
3. Tapez `D` pour joindre un domaine.
4. Indiquez le nom du domaine et un utilisateur autorisé dans le format `billu.lan`.
5. Saisissez le mot de passe de l'utilisateur lorsque vous y êtes invité.

    ![SS3](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/56fcfe942535d9f5b9fd5b683e1da38e8e58a018/Resources/s02/S02%20WinCORE%2003%20Change%20Domain.png)

### Étape 4 : Finaliser l'intégration
1. Si on vous propose de changer le nom de l'ordinateur à nouveau, sélectionnez **Non** (puisque cela a déjà été fait).
2. Redémarrez le serveur pour terminer le processus.

### Vérification
Après le redémarrage :
- Connectez-vous au serveur avec les informations d'identification du domaine.
- Tapez `SConfig` pour confirmer que le serveur est bien joint au domaine Active Directory.

    ![SS4](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/56fcfe942535d9f5b9fd5b683e1da38e8e58a018/Resources/s02/S02%20WinCORE%2004%20final.png)

## Contrôler Windows Server Core depuis Windows Server 2022

- Une fois le serveur Core intégré au domaine, vous pouvez le gérer facilement depuis un serveur Windows Server 2022 avec interface graphique. Il suffit d'utiliser le *Server Manager* pour ajouter le serveur Windows Core à la liste des serveurs. Cliquez Manage > Add Servers

![SS5](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/a09caebfba4f7dae7c7374a4c6ef710b28d34fb9/Resources/s02/S02%20WinCORE%2005%20windows%20server%20manager.png) 

- Cherchez votre serveur sur l'Active Directory

![SS6](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/a09caebfba4f7dae7c7374a4c6ef710b28d34fb9/Resources/s02/S02%20WinCORE%2006%20windows%20server%20manager%20add.png)
    
- Votre serveur doit apparaitre sur le serveur manager

![SS7](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/a09caebfba4f7dae7c7374a4c6ef710b28d34fb9/Resources/s02/S02%20WinCORE%2007%20windows%20server%20manager%20final.png)

## 4. Créer une Unité Organisationnelle et des groupes de sécurités sur Active Directory

### Étape 1 : Accéder à la console Active Directory Users and Computers
1. Connectez-vous à un serveur Windows avec l'interface graphique et les outils d'administration Active Directory installés.
2. Ouvrez l'outil **Active Directory Users and Computers**.

    ![ADUC](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/b9b466c9493b1d0a228a7b2feff6877fccedadc6/Resources/s02/S02%20OU%20et%20des%20groupes%2001.png)

### Étape 2 : Créer une nouvelle Unité Organisationnelle
1. Dans la console ADUC, naviguez jusqu'au domaine billu.lan (ou domaine souhaité).
2. Faites un clic droit sur le domaine et sélectionnez **New > Organizational Unit**.

    ![SS2](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/b9b466c9493b1d0a228a7b2feff6877fccedadc6/Resources/s02/S02%20OU%20et%20des%20groupes%2002.png)

3. Donnez un nom à votre Unité Organisationnelle et cliquez sur **OK**.

    ![SS3](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/b9b466c9493b1d0a228a7b2feff6877fccedadc6/Resources/s02/S02%20OU%20et%20des%20groupes%2003.png)

4. La nouvelle Unité Organisationnelle apparaît dans la structure Active Directory.

### Étape 3 : Créer un groupe de sécurité
1. Naviguez jusqu'à l'Unité Organisationnelle que vous venez de créer.
2. Faites un clic droit sur l'Unité Organisationnelle et sélectionnez **New > Group**.


3. Donnez un nom à votre groupe.
4. Configurez les paramètres du groupe :
   - **Group Scope** : Choisissez **Global**.
   - **Group Type** : Sélectionnez **Security**.
5. Cliquez sur **OK** pour créer le groupe.

    ![SS4](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/b9b466c9493b1d0a228a7b2feff6877fccedadc6/Resources/s02/S02%20OU%20et%20des%20groupes%2004.png)

### Étape 4 : Ajouter des membres au groupe
1. Faites un clic droit sur le groupe nouvellement créé et sélectionnez **Properties**.
2. Allez à l’onglet **Members** et cliquez sur **Add**.

    ![SS6](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/e68f1869c36250bbd8e136f2888cdf7f3782f437/Resources/s02/Capture%20d'%C3%A9cran%202024-12-12%20101820.png)

3. Saisissez les noms des utilisateurs ou groupes que vous souhaitez ajouter, puis cliquez sur **Check Names** pour valider.
4. Une fois les membres ajoutés, cliquez sur **OK** pour sauvegarder.


### Vérification
- Retournez à l’onglet **Members** dans les propriétés du groupe pour confirmer que les membres ont été correctement ajoutés.
- Naviguez dans l’Unité Organisationnelle pour vérifier que le groupe et ses membres sont présents.

    ![SS8](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/243c5fa9a416d9110adabca05519b405bfa1b77b/Resources/s02/Capture%20d'%C3%A9cran%202024-12-12%20101900.png)


   

   
  

    



