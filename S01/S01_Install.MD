# Planification & Structuration d'une nouvelle infrastructure réseau

## Prérequis techniques

- Comprendre et exploiter une infrastructure réseau
- Maîtriser le découpage réseau 
- Connaissance GNS3/Packet Tracer


## Planification d'une infrastructure réseau 

### Nomenclature 

Afin d'avoir une uniformisation de l'ensemble du parc informatique et de ses différents éléments physiques et non-physiques. Dans le cadre, de BillU vous trouverez dans le tableau les différentes correspondances. 

Chaque matériel respectera la forme suivante Entreprise(3)-Ville(3)-site(2)-département(3)-type(3)-ID(5)
Aujourd'hui BillU compte 1 seul site et donc le préfixe des 8 premiers caractères resteras le même. Quant à l'ID il est formé de 3 premiers chiffres par ordre d'attribution et des 2 derniers chiffres de l'année de mise en service (ex: 24 pour 2024). 

Exemple: 

**BIL-PAR-01-CRP-LAP-00124** = 1er laptop mis en service de 2024 du service Communication et Relations publiques , du site 01 de la ville de Paris

|                    Départements                    | Nomenclature | 
|:--------------------------------------------------:|:------------:|
|        Communication et Relations publiques        |      CRP     |
|                Département Juridique               |      JUR     | 
|               Développement logiciel               |      DVL     |     
|                      Direction                     |      DIR     |    
|                         DSI                        |      DSI     |     
|               Finance et comptabilité              |      FEC     |      
| QHSE (Qualité, Hygiène, Sécurité et Environnement) |      QSE     |   
|                 Service Commercial                 |      SCL     |           
|                 Service recrutement                |      SRH     |     


| Type de matériel | Nomenclature |
|:----------------:|:------------:|
|      Laptop      |      LAP     |
|      PC Fixe     |      PCF     |
|      Switch      |      SWI     |
|      Routeur     |      RTR     |
|      Serveur     |      SRV     |
|        VM        |      VMS     |
|    Conteneurs    |      CTS     |



### Structure physique 

Après avoir consulté la structuration de l'entreprise et son nombre d'employés, faire un premier schéma basique sur lequel s'appuyer.
![](../Resources/Sch%C3%A9ma%20provisoire.png)

Une fois avoir validé votre schéma comme solution possible vous pouvez créer une version qui visualisation que l'on qualifiera de "matérielle" avec l'ensemble du parc informatique (cf ci-dessous) 
![](../Ressources/S01/schema_draw_reseau.png)

### Structurer son architecture réseau

À l'aide d'un logiciel d'émulation de réseau comme GNS3 ou Packet Tracer, vous pouvez mettre en place votre architecture réseau, et vérifier son bon fonctionnement avant de la mettre en place en production.

![](../Ressources/S01/schema_reseau_pt.png)



