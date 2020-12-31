# Article Big data : 


> FAIT PAR : Sid Ahmed YOUSFI / Aymen NEFZAOUI / Saad HASNAOUI



## Introduction :



Nul ne peut aujourd'hui ignorer les dangers liés à l'utilisation d'Internet : virus, spams et pirates informatiques sont les maîtres mots utilisés par les médias. De plus en plus de sociétés ouvrent leur système d'information à leurs partenaires ou leurs fournisseurs et donnent l'accès internet à leurs employés. Avec l’essor d’Internet, et l’utilisation par la majorité des entreprises et des organisations de processus informatiques, les menaces visant les systèmes d’informations n’ont cessé d’augmenter et de se sophistiquer, faisant aujourd’hui de la sécurité informatique une nécessité pour tous les types de structure. C'est pourquoi il est nécessaire de connaître les risques liés à l'utilisation d'internet et les principales parades.

Depuis quelques années, le volume de données créées dans le monde ne cesse de grandir. Ainsi, en 2010 ce volume est passé de 1.2 zettaoctets (Zo) à 1.8 Zo en 2011 et à 2.8 Zo en 2012. En moyenne, on estime que ce volume de données double tous les 18 mois. Selon l’étude Digital Age réalisée par IDC, le volume total de données stockées dans le monde atteindra 175 Zo en 2025. Ces données générées sont exploitées pour créer des services, faire du machine learning mais aussi de la sécurité informatique.

## Le SIEM : 

Les systèmes de gestion des informations et des événements de sécurité (SIEM, Security Information and Event Management) sont des solutions permettant d’avoir une vision unifiée du pilotage de sécurité du SI. Afin d’avoir cette vision finale unifiée, des traces d’activités (logs) sont collectées de diverses sources (Architecture distribuée et d’énormes données en input) et analysées afin de notifier des comportements inhabituels. Par exemple, le SIEM va utiliser les données à sa disposition et analyser les comportements habituels d’un utilisateur (analyse comportementale). En ce sens, une connexion à 3h00 du matin via une adresse IP qui est localisée en Russie ne peut qu’être suspecte et susciter l’attention. Un autre cas d’usage serait celui des tentatives d’accès par VPN. Si une multitude de tentatives de connexion au réseau VPN ont lieu depuis différentes localisations dans un bref laps de temps, le SIEM pourra les considérer comme des activités suspectes.


Dans ce rapport, nous allons parler de cette solution (SIEM) qui permet de remonter en temps réel les alertes liées à la sécurité informatique.


## Fonctionnement d’un SIEM

Le SIEM (Security Information and Event Management) répond à un besoin fort de sécuriser les infrastructures en s’adressant aux DSI, RSSI et exploitants soucieux de disposer d’un outil efficace pour maîtriser le niveau de sécurité du SI. Il fournit le moyen de détecter les attaques et les menaces de sécurité en temps réel, capable de visualiser, comprendre et enregistrer les activités du SI aussi bien en temps réel que de manière différée, afin d’utiliser cette connaissance pour améliorer la posture de sécurité de l’entreprise, réduire ses risques et l’aider à simplifier ses processus de mise en conformité.

Les solutions de SIEM disposent communément des fonctions principales suivantes :

La collecte des événements produits par les équipements et applications du SI : firewalls, antivirus, serveurs web, applications métier, systèmes de détection d'intrusions,
La centralisation et le stockage des événements issus des modules de collecte,
La normalisation, l’enrichissement, l’analyse et la corrélation des événements de sécurité, 
La présentation synthétique (tableaux de bords, statistiques, ...) de la sécurité du SI, 
L'envoi d'alarmes pour notifier des incidents de sécurité.

 
 
## Apache Metron

Apache Metron est une plateforme d'analyse et de stockage dédiée à la sécurité informatique. C’est un framework de sécurité informatique qui permet aux entreprises d'intégrer, traiter et stocker différents flux de données pour détecter les anomalies et permettre aux organisations de réagir rapidement.
Il fournit un cadre d'analyse de sécurité évolutif basé sur la technologie Hadoop. Il surveille le trafic réseau et les journaux de la machine en consommant un flux continu de données.





![metron-overview](https://user-images.githubusercontent.com/44205421/103366174-33e9c000-4ac2-11eb-912c-781c0584cb18.png)




# Déploiement d’Apache Metron

Afin de déployer Apache metron il faudra utiliser plusieurs technologies :

### Vagrant 

Lors du développement d'une application ou d'un site Web, il y a sans aucun doute une erreur dans un environnement donné, et nous ne pouvons pas répliquer l'erreur localement sur le poste de travail. Vagrant permet d'avoir le même environnement de développement que notre serveur grâce à la virtualisation.
En effet, Vagrant est un outil qui permet de créer une machine virtuelle lors du développement d'applications afin d'obtenir l'environnement requis sans changer la configuration de l'ordinateur. L'objectif est de travailler dans le même environnement que la production ou la mise en scène pendant le développement.
Mais veuillez noter que Vagrant et l'extension Virtualbox ne peuvent pas être utilisés directement en production, c'est donc nécessaire de simuler l'environnement de production pour la pré-production ou le développement.
N.B : Afin de pouvoir utiliser Vagrant sur votre ordinateur, VirtualBox doit être installé à l'avance.

### Ansible

Ansible est un logiciel de gestion de configuration open source qui automatise le déploiement d'applications et la livraison continue des mises à jour. En effet, Ansible est une solution qui permet d'effectuer le déploiement, l'exécution des tâches et la gestion de la configuration sur plusieurs ordinateurs en même temps. Il est sans agent et utilise SSH pour définir les opérations à effectuer. Ces opérations elles-mêmes sont écrites en YAML. Lorsque vous utilisez Ansible, vous pouvez utiliser des modules. Il existe une liste de modules qui ont été écrits, mais vous pouvez aussi écrire vos propres modules. Il est bon d'utiliser des commandes pour gérer un groupe de machines. Néanmoins, il est difficile d'imaginer exécuter des commandes les unes après les autres pour lire le script, nous pouvons donc utiliser ansible-playbook pour écrire le script en YAML


### Hadoop

Aujourd'hui, Hadoop est devenu la principale plateforme de Big Data. Il est utilisé pour stocker et traiter de grandes quantités de données. En effet il s'agit d'un framework logiciel open source pour stocker des données et lancer des applications sur des clusters d'ordinateurs standard. La solution offre un espace de stockage énorme pour tous les types de données, une puissance de traitement énorme et la capacité de prendre en charge des tâches presque illimitées.


### Ambari

Apache Ambari c’est  fournir, gérer, surveiller et protéger une plate-forme entièrement open source pour les clusters Apache Hadoop. Avec Apache Ambari, aucune conjecture n'est requise lors de l'utilisation de Hadoop. Apache Ambari nous permettra donc d’installer et configurer HDP en toute sécurité en facilitant la maintenance et la gestion continues des clusters de toutes tailles.



# Ingestion des fichiers, flux et log système et enrichissement des données 

Une fois que metron est déployé , il va falloir gérer les fichiers logs et et les flux que on va récupérer et les enrichir  , pour cela on utilisera les technologies appelé Apache nifi et kafka car ces outils permettent  de travailler sur la donnée avec une grande facilité.

### Apache NIFI

Apache NiFi est un projet open source de la Fondation Apache. Il permet d’injecter automatiquement des flux de données entre différents systèmes sources dans d'autres systèmes cibles. 
Basé sur le paradigme de programmation basé sur les flux, NiFi fournit aussi  une interface Web qui vous permet de créer des flux de données dans Drag and Drog. Par conséquent, le flux de données peut être défini, contrôlé et d'une certaine manière assuré en temps réel.
En résumé Apache NiFi fournit un flux de données complet, possède une tolérance aux pannes, une scalabilité et est conçu pour traiter de grandes quantités de données en temps réel.
Il est compatible avec Kerberos, qui fournit l'authentification, Apache Ranger, qui fournit la sécurité des autorisations d'accès, et Apache Knox, qui fournit une sécurité et une sécurité au niveau de l'authentification pour les appels REST et HTTP.

### Apache Kafka
L’ensemble des briques technologiques utilisées communiquent au travers d’un bus de messagerie Apache Kafka. Au sein d’Apache Kafka, les données sont stockées de manière ordonnée et durable, et peuvent être lues de manière déterministe. Les données sont distribuées et répliquées, ce qui permet à ce système de garantir une tolérance aux pannes ainsi que la capacité à être scalable sur le plan horizontal.


# Stockage / Archivage des logs: 

#### HDFS
Le système de fichier distribué HDFS (pour Hadoop Distributed File System) est utilisé pour le stockage et l’archivage des logs collectés par le SIEM. HDFS est un système de fichiers distribué Big Data fonctionnant en cluster et permettant la gestion en lecture / écriture de très importants volumes de données. C’est un environnement scalable, tolérant aux pannes et haute disponibilité.


# Alertes et Visualisation

### Indexation / Visualisation des données (logs, événements, flows, ...) : Elasticsearch

Elasticsearch est un moteur d’indexation et de recherche temps réel distribué utilisant Apache Lucene, qui est une librairie libre et open source d’indexation et de recherche. Elasticsearch a été développé pour fonctionner en mode distribué. L’ensemble (le cluster) est composé de nœuds. Un nœud maître est choisi et sera automatiquement remplacé en cas de défaillance. Chaque nouveau nœud rejoint le cluster qui lui a été désigné. Les données collectées (logs, événements, flows, ...) sont indexées dans Elasticsearch.


# Le plus de ce SIEM

### Gestion de la scalabilité 

La solution s’appuie sur un ensemble de briques technologiques permettant de gérer la scalabilité et la montée en charge de manière horizontale et verticale.
Les 4 technologies principales utilisées (Elasticsearch, HDFS, Apache NiFi, Apache Kafka) fonctionnent en cluster et sont scalables horizontalement par ajout de nouveaux nœuds de traitement. Une scalabilité verticale (CPU, RAM et disque) est également possible dans une certaine limite sur chaque nœud constituant les différents éléments des clusters.

### Gestion de la haute disponibilité

Les 4 technologies principales utilisées (Elasticsearch, HDFS, Apache NiFi, Apache Kafka) fonctionnent nativement en mode haute disponibilité.

# Fonctionnement de Apache Metron :

![metron-ecosystem](https://user-images.githubusercontent.com/44205421/103360879-588d6a00-4ab9-11eb-8605-c51e2920366e.png)


Le déploiement de metron mettra en place 2 cluster (hdp et hdf) , Comme on peut le noter ci-dessus, Apache Metron agit comme un pipeline de traitement de flux de sécurité en temps-réel destiné à :

**Capturer** les événements télémétriques générés par les diverses classes de sources de données ingérées. Durant cette phase Metron utilise son propre composant d’ingestion ou des outils comme Apache NiFi pour traiter les flux de données à travers leurs propres topics Kafka. Metron peut également traiter de gros volumes d’événements comme PCAP, NetFlow,… à partir d’un TAP réseau.

**Traiter** les flux routés par Kafka au sein d’une topologie Storm sur lequel s’appuie Metron Streaming pour ses traitements. Durant cette phase, les données sont analysées, normalisées, validées, puis étiquetées.

**Enrichir** les événements préalablement traités, à travers diverses opérations comme l’enrichissement des informations de connexion utilisées par lesdits événements (IP, hostname, GPS,…) pour une meilleure identification.

**Etiqueter** les événements traités et enrichis, qui consiste à vérifier leurs informations afin de valider leur degré de dangerosité, puis de les étiqueter en fonction des résultats du processus de vérification. De cette façon, en cas de faille de sécurité suite à l’ingestion d’un événement, le système sera en mesure d’éviter que des événements similaires se reproduisent à l’avenir.

**Stocker** les événements télémétriques préalablement capturés, traités, enrichis et étiquetés au sein d’un « coffre » appelé Security Data Vault (HDFS, etc…) ou d’un magasin PCAP dans le cas de gros paquets réseaux. Les événements ayant levé des alertes sont indexés dans un magasin d’alertes.
