# TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU

## Présentation du projet, objectifs finaux

Vous faites parti de la société **BillU**.
Notre formateur joue le rôle du DSI de cette société.
Notre objectif final est de mettre en place une nouvelle infrastructure réseau.

## Introduction : mise en contexte

**BillU** est une filiale du groupe international RemindMe, qui a plus de 2000 collaborateurs dans le monde. Elle est spécialisée dans le développement de logiciels, entre-autre de facturation. Le groupe prévoit un budget conséquent pour développer cette filiale. Le siège Français se situe à Paris (dans le 20 eme arrondissement).
Avec une équipe talentueuse de développeurs et d'experts en finance, elle est déterminée à fournir des logiciels de pointe qui simplifient les processus financiers et améliorent l'efficacité opérationnelle pour ses clients.
BillU comprend actuellement 167 personnes.
L'ensemble du personnel est réparti dans 9 services (appelés "départements").
Des personnels extérieurs travaillent ponctuellement ou à temps plein avec certains services.

## Membres du groupe de projet (rôles)
| Sprint  | Product Owner | Scrum Master  |  Développer |  Développer |
|---|---|---|---|---|
|  S01 | Antoine   | Sam  |  Erwan |  Christophe |
|  S02 |  Erwan | Christophe  | Antoine  |  Sam |
| S03  |  Christophe | Erwan  | Sam | Antoine  |
|  S04 |  Sam | Antoine  | Erwan  | Christophe  |
|  S05 |  Antoine |  Christophe |  Erwan |   |
| S06  |  Erwan |  Antoine |  Christophe |   |
| S07  |   |   |   |   |
|  S08 |   |   |   |   |
|  S09 |   |   |   |   |
| S10  |   |   |   |   |
| S11  |   |   |   |   |
|  S12 |   |   |   |   |


Par sprint :
# S01

1. Faire une proposition d'objectif par sprint pour l'ensemble de la formation
   
   
2. Établir un schéma réseau prévisionnel de l'infrastructure


# S02

1. Création d'un domaine AD sur un serveur Windows Server 2022 en GUI avec les rôles AD-DC et DHCP et DNS et une replication du role AD-DC sur un serveur Windows Server 2022 Core.

  
    
2. Creation d'une arborescense AD avec une creation d'OU et creation des groupes avec une convention de nommage.


3. Integration des utilisateurs a l'AD-DC

  
   
# S03

1. Création de GPO de securité
      1. Politique de mot de passe
      2. Blocage complet ou partiel au panneau de configuration
      3. Ecran de veille avec mot de passe en sortie
      4. Limitation des tentatives d'élévation de prilèges
      5. Politique de sécurité PowerShell

2. Création de GPO Standard
      1. Fond d'écran obligatoire 
      2. Mappage de lecteurs
      3. Gestion de l'alimentation
      4. Déploiement de logiciels telles que firefox



3. Mise en place d'un serveur Debian pour la gestion du parc
      1. Installation du logiciel GLPI 
      2. Synchonisation AD
      3. Inclusion des utilisateurs au GLPI
      4. Gestion des incidents, mise en place du ticketing
      5. Accés et gestion à partir d'un client 


   
# S04

1. Creation de GPO pour la gestion de la télémetrie.

2. Configuration du Firewall PFSense et mise en place de regles 
3. Remplissage des Summary sur l'ensemble des machines virtuelle 

# S05

1. Creation d'un serveur windows pour la gestion des sauvegardes en RAID 1
2. Mise en places des dossiers de partages.
      1. un dossier individuel nommé I
      2. un dossier de service nommé J
      3. un dossier de département nommé K 

# S06


