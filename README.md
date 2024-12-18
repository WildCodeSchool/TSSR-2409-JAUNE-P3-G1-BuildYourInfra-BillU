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
| S06  |   |   |   |   |
| S07  |   |   |   |   |
|  S08 |   |   |   |   |
|  S09 |   |   |   |   |
| S10  |   |   |   |   |
| S11  |   |   |   |   |
|  S12 |   |   |   |   |


Par sprint :
# S01

1. Faire une proposition d'objectif par sprint pour l'ensemble de la formation
   
   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/980f2ce906fb85a4b45f7f7f81248ef34d80e733/Resources/Planning.png)
3. Établir un schéma réseau prévisionnel de l'infrastructure

   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/980f2ce906fb85a4b45f7f7f81248ef34d80e733/Resources/Sch%C3%A9ma%20provisoire.png)

# S02

Création d'un domaine AD sur un serveur Windows Server 2022 en GUI avec les rôles AD-DC et DHCP et DNS et une replication du role AD-DC sur un serveur Windows Server 2022 Core.

   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/980f2ce906fb85a4b45f7f7f81248ef34d80e733/Resources/s02/capture_install_adds_role.png)

   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/980f2ce906fb85a4b45f7f7f81248ef34d80e733/Resources/s02/adds_config_path.png)

   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/980f2ce906fb85a4b45f7f7f81248ef34d80e733/Resources/s02/S02%20WinCORE%2004%20final.png)

   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/980f2ce906fb85a4b45f7f7f81248ef34d80e733/Resources/s02/S02%20WinCORE%2003%20Change%20Domain.png)
    
Creation d'une arborescense AD avec une creation d'OU et creation des groupes avec une convention de nommage.

  

   ![](

Integration des utilisateurs a l'AD-DC

# S03

Creation de GPO de securité et de GPO standard.

Mise en place d'un serveur GLPI 

# S04

Creation d'un GPO pour la gestion de la télémetrie.

Configuration du Firewall PFSense et mise en place de regles 

# S05

Creation d'un serveur windows pour la gestion des sauvegardes en RAIS 1 et des Dossiers pratages 
