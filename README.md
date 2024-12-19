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

   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/bf9d42732558b59a202e69264a42636857a29261/Resources/s02/Capture%20d'%C3%A9cran%202024-12-19%20094815.png)

Integration des utilisateurs a l'AD-DC

   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/a4670ae764c8ae57799fd7569fe3f41c06817a33/Resources/s02/Capture%20d'%C3%A9cran%202024-12-19%20095726.png)

   
# S03

Creation de GPO de securité et de GPO standard.

   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/a4670ae764c8ae57799fd7569fe3f41c06817a33/Resources/GPO%20politique%20des%20MDP.png)

   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/a4670ae764c8ae57799fd7569fe3f41c06817a33/Resources/GPO%20s03-2.1.png)


Mise en place d'un serveur GLPI 

   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/6d0d745b8f9d2cfe4362ade93df1c498701cb16c/Resources/S03/Capture%20d'%C3%A9cran%202024-12-19%20100834.png)

   
# S04

Creation d'un GPO pour la gestion de la télémetrie.

   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/afbcb88fe08def78daa3a28f4faf3df569055974/S04/Capture%20d'%C3%A9cran%202024-12-10%20155437.png)

   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/a78b23284170ab26f6e7fc7748a338756f101f09/S04/Capture%20d'%C3%A9cran%202024-12-10%20155446.png)

Configuration du Firewall PFSense et mise en place de regles 

   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/a78b23284170ab26f6e7fc7748a338756f101f09/S04/Capture%20d'%C3%A9cran%202024-12-12%20180335.png)

   ![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/a78b23284170ab26f6e7fc7748a338756f101f09/S04/Capture%20d'%C3%A9cran%202024-12-12%20180348.png)

   
# S05

Creation d'un serveur windows pour la gestion des sauvegardes en RAID 1 et des Dossiers pratages 

![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/4f3236203f9aa6ff0d278af932faaa275fd6ff66/S05/Mise%20en%20place%20du%20raid.png)

![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/4f3236203f9aa6ff0d278af932faaa275fd6ff66/S05/Mise%20en%20place%20des%20disques.png)

![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/4f3236203f9aa6ff0d278af932faaa275fd6ff66/S05/Raid%20en%20formatage.png)

![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/4f3236203f9aa6ff0d278af932faaa275fd6ff66/S05/Raid%20reussi.png)

![](https://github.com/WildCodeSchool/TSSR-2409-JAUNE-P3-G1-BuildYourInfra-BillU/blob/75b6f1ddfe7216985c15eb1441bedf09c67d88a2/S05/Capture%20d'%C3%A9cran%202024-12-19%20103326.png)
