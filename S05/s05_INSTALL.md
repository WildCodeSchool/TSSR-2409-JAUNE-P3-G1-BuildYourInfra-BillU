# Mise en place de dossiers réseau pour les utilisateurs

1. Stockage des données sur un volume spécifique

2. Sécurité de partage des dossiers par groupe AD

3. Mappage des lecteurs sur les clients (au choix) : GPO
 - Un **dossier individuel** , avec une lettre de mappage réseau **I**, accessible uniquement par cet utilisateur
 - Un **dossier de service**, avec une lettre de mappage réseau **J**, accessible par tous les utilisateurs d'un même service.
 - Un **dossier de département**, avec une lettre de mappage **K**, accessible par tous les utilisateurs d'un même département.



# STOCKAGE AVANCÉ - Mettre en place du RAID 1 sur un serveur

Mise en place d'un serveur 
Création du RAID 1 



# SÉCURITÉ D'ACCÈS - Restriction d'utilisation

1. Pour les utilisateurs standard : connexion autorisée de 7h00 à 20h, du lundi au samedi sur les clients (bloquée le reste du temps)
2. Pour les administrateurs : bypass
3. Gestion des exceptions : prévoir un groupe bypass



# SAUVEGARDE - Mettre en place une sauvegarde de données

1. Faire le bon choix des données à sauvegarder (ex.: dossiers partagés des utilisateurs)
2. Emplacement de la sauvegarde sur un disque différents de celui des données d'origine
3. Mettre en place une planification de sauvegarde (script, AT, GPO, logiciel, etc.)
