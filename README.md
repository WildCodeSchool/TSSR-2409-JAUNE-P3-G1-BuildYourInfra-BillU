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
| S07  |  Christophe | Erwan  |  Antoine |   |
|  S08 |  Antoine |  Christophe | Erwan  |   |
|  S09 |  Erwan |  Antoine |  Christophe |   |
| S10  | Christophe | Erwan | Antoine |   |
| S11  |   |   |   |   |
|  S12 |   |   |   |   |


Par sprint :
# S01

- Faire une proposition d'objectif par sprint pour l'ensemble de la formation
   
- Établir un schéma réseau prévisionnel de l'infrastructure

- Établir les tables de routage des routeurs

- Établir une convention de nommage


# S02

- Création d'un domaine AD sur un serveur Windows Server 2022 en GUI avec les rôles AD-DC et DHCP et DNS et une réplication du rôle AD-DC sur un serveur Windows Server 2022 Core.

- Création d'une arborescente AD avec une création d'OU et création des groupes avec une convention de nommage.

- Gestion de l'arborescence AD

- Intégration des utilisateurs a l'AD-DC

  
   
# S03

- Création de GPO de sécurité 

	- Politique de mot de passe
   
	- Blocage complet ou partiel au panneau de configuration
   
	- Ecran de veille avec mot de passe en sortie
   
	- Imitation des tentatives d'élévation de privilèges
   
	- Politique de sécurité PowerShell

- Création de GPO Standard
	- Fond d'écran obligatoire 
	- Mappage de lecteurs
	- Gestion de l'alimentation
	- Déploiement de logiciels telles que Firefox



- Mise en place d'un serveur Debian pour la gestion du parc

	- Installation du logiciel GLPI 
	- Inclusion des utilisateurs au GLPI
	- Gestion des incidents, mise en place du ticketing
	- Accès et gestion à partir d'un client 


   
# S04

- Création de GPO pour la gestion de la télémétrie.

- Configuration du Firewall PFSense et mise en place de réglés 

- Remplissage des Summary sur l'ensemble des machines virtuelle 

# S05

- Création d'un serveur Windows pour la gestion des sauvegardes en RAID 1
  
- Mise en places des dossiers de partages avec restrictions d'accès

	- un dossier individuel nommé I

	- un dossier de service nommé J

	- un dossier de département nommé K 

# S06

- Mise en place d'une gestion des logs centralisée
  
	- Installation du logiciel GrayLog 

- Mise en place d'une supervision de l'infrastructure réseau
 	- Installation de PRTG sur un serveur Windows


- Modification AD Nouveau fichier RH 
	- Intégration des nouveaux utilisateurs
   
	- Modifications de certaines informations sur les effectifes 

# S07

- Mise en place d'un serveur de messagerie
	- Installation iRedMail sur CT dédié

- Mise en place d'un serveur de gestion de mot de passe
	- Installation Passbolt ou Bitwarden sur CT

# S08
 ## Infrastructure BillU
 
- Installation du rôle WSUS 

- Répartition des rôles FSMO sûr différents DC du domaine

 ## Partenariat Ecotechsolution-BillU
 
- Installation d'un tunnel VPN site à site

- Instauration d'une relation d'approbation entre les domaines AD des 2 entreprises

# S09

- Mettre en place un serveur de téléphonie sur IP

- Mettre en place un serveur WEB

# S10 
- Configuration d'un pc d'administration

- Audit ACTIVE DIRECTORY

- Audit SERVEURS LINUX
 
## Choix techniques

## Difficultés rencontrées

## Solutions trouvées

## Améliorations possibles
