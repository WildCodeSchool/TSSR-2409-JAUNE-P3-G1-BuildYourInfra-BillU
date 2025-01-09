## 1. Journalisation 

### Prérequis 

Contenaire Debian 12

Environnent de test sur Proxmox en VM

* Memory      8 GB
    
* Processors  4
    
* Réseau      vmbr525

* Adresse IP de réseau     : 172.18.0.9/16 
  
* Adresse IP de passerelle : 172.18.255.254 
  
* Adresse IP du DNS        : 172.15.255.254 


1.1 Mise en place de la journalisation 

- Installation Pas à pas de Graylog

        sudo apt-get update
        sudo apt-get install curl lsb-release ca-certificates gnupg2 pwgen

![](../Ressources/S06/s06_Graylog_install05.png)

- Installation de MongoBB

        curl -fsSL https://www.mongodb.org/static/pgp/server-6.0.asc | sudo gpg -o /usr/share/keyrings/mongodb-server-6.0.gpg --dearmor  

![](../Ressources/S06/s06_Graylog_install06.png)

        echo "deb [ signed-by=/usr/share/keyrings/mongodb-server-6.0.gpg] http://repo.mongodb.org/apt/debian bullseye/mongodb-org/6.0 main" | sudo tee /etc/apt/sources.list.d/mongodb-org-6.0.list

![](../Ressources/S06/s06_Graylog_install01.png)

        apt-get update

![](../Ressources/S06/s06_Graylog_install02.png)

        wget http://archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.1f-1ubuntu2.23_amd64.deb
        dpkg -i libssl1.1_1.1.1f-1ubuntu2.23_amd64.deb

        apt-get install -y mongodb-org

![](../Ressources/S06/s06_Graylog_install08.png)

        systemctl daemon-reload
        systemctl enable mongod.service

![](../Ressources/S06/s06_Graylog_install10.png)

        systemctl restart mongod.service
        systemctl --type=service --state=active | grep mongod

![](../Ressources/S06/s06_Graylog_install12.png)

- Installation d'OpenSearh

        curl -o- https://artifacts.opensearch.org/publickeys/opensearch.pgp | gpg --dearmor --batch --yes -o /usr/share/keyrings/opensearch-keyring  

        echo "deb [signed-by=/usr/share/keyrings/opensearch-keyring] https://artifacts.opensearch.org/releases/bundle/opensearch/2.x/apt stable main" | sudo tee /etc/apt/sources.list.d/opensearch-2.x.list

        apt-get update

        env OPENSEARCH_INITIAL_ADMIN_PASSWORD=IT-Connect2024! apt-get install opensearch

        nano /etc/opensearch/opensearch.yml

    - Configurez les options suivantes 

            cluster.name: graylog
            node.name: ${HOSTNAME}
            path.data: /var/lib/opensearch
            path.logs: /var/log/opensearch
            discovery.type: single-node
            network.host: 127.0.0.1
            action.auto_create_index: false
            plugins.security.disabled: true

- Configuration de JVM

        sudo nano /etc/opensearch/jvm.options

    - Modifier la memoire

        -Xms1g \
        -Xmx1g

        Par les lignes 

        -Xms4g \
        -Xmx4g

    - Verifier avec la commande 

            cat /proc/sys/vm/max_map_count

    - Activez le demmarrage automatique 

            systemctl daemon-reload
            systemctl enable opensearch
            systemctl restart opensearch


- Installation de graylog 

        wget https://packages.graylog2.org/repo/packages/graylog-6.1-repository_latest.deb
        dpkg -i graylog-6.1-repository_latest.deb
        apt-get update
        apt-get install graylog-server

    - Générer la clé de 96 

            pwgen -N 1 -s 96

![](../Ressources/S06/S06_Graylog_key01.png)


- Collez la clé au niveau du paramétre "password_secret"


            nano /etc/graylog/server/server.conf

- faitez les modification suivantes

![](../Ressources/S06/S06_conf_graylog1.png)
![](../Ressources/S06/S06_conf_graylog2.png)
![](../Ressources/S06/S06_conf_graylog3.png)
![](../Ressources/S06/S06_conf_graylog4.png)


- Démarrer graylog


            systemctl enable --now graylog-server

- Vous pouvez désormais vous connecter avec votre compte admin sur un moteur de recherche internet 

![](../Ressources/S06/S06_Page_Graylog.png)

- Desactivation de la télémetrie 

![](../Ressources/S06/S06_desactivation_de_la_télemetie.png)

- Creation d'un profil

![](../Ressources/S06/S06_Crée_un_profil.png)

![](../Ressources/S06/S06_New_profil.png)

- Creation d'un journal 

![](../Ressources/S06/S06_GELF_UDP.png)

![](../Ressources/S06/S06_onglet_de_parametrage.png)

Vous obtenez comme resultat

![](../Ressources/S06/S06_resultat.png)

Et voici la page de garde de votre journalisation

![](../Ressources/S06/S06_journalisation.png)



## 2. Supervision 

### Prerequis 

### Prérequis pour Windows serveur 2022

Environment de test sur Proxmox en VM

* Memory      4 GB
    
* Processors  2
    
* Réseau      vmbr525

* Adresse IP de réseau     : 172.18.0.5/16 
  
* Adresse IP de passerelle : 172.18.255.254 
  
* Adresse IP du DNS        : 172.15.255.254 

2.1 Installation de PRTG

- Télecharger PRTG a l'aide de ce [lien](https://www.paessler.com/fr) 

- Cliquer sur Téléchargement gratuit 

![](../Ressources/S06/S06_Key_PRTG.png)

- Exécuter le fichier télécharger 

![](../Ressources/S06/S06_PRTG_.EXE.png)

- Choix de la langue

![](../Ressources/S06/S06_PRTG_choix_langue.png)

- Accord de la licence

![](../Ressources/S06/S06_PRTG_accord_de_licence.png)

- Entrer une adresse e-mail et cliquer sur le bouton suivant
- Choisissez le mode d'installation

![](../Ressources/S06/S06_PRTG_Install.png)

- Patienter pendant l'installation PRTG

![](../Ressources/S06/S06_PRTG_connection.png)

- parametrage de PRTG

![](../Ressources/S06/S06_Paramétrage_PRTG.png)

![](../Ressources/S06/S06_PRTG_Ecrand'accueil.png)

- Ajout d'un capteur 

![](../Ressources/S06/S06_PRTG_Ajout_capteur.png)

- Vous pouvez crée un equipement et/ou capteur

![](../Ressources/S06/S06_PRTG_Ajout_capteur2.png)

- Choix de l'equipement a supervisé 

![](../Ressources/S06/S06_PRTG_choix_capteur.png)

- Parametrage du capteur

![](../Ressources/S06/S06_PRTG_config_capteur.png)

- Resultat 

![](../Ressources/S06/S06_resultat_capteur.png)
