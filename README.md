# Apache Metron 

## Mise en place du LAB

Avant de déployer la solution Apache Metron, vous devez vous assurer d’avoir les bons outils avec les bonnes versions :

Python 2.7
Pip 
VirtualBox
JAVA 8
Vagrant / Vagrant Hostmanager
docker
Maven 
Ansible

Pour ce faire, voici les étapes à suivre :

> Note : Les commandes suivantes sont réalisées dans un environnement Linux (Ubuntu)

### First Step : faire un update des paquets apt
```
$ sudo apt-get update
```


### Installation de pip 
```
$ sudo apt-get install python-pip python-dev build-essential
$ sudo pip install 
```
(Screen de version)

### Installation de VirtualBox

```
$ sudo apt-get install virtualbox
```

### Installation de JAVA

```
$ sudo add-apt-repository ppa:webupd8team/java
$ sudo apt install oracle-java8-installer
```

### Installation de Vagrant 

```
$ sudo apt update
$ sudo apt install vagrant
```

### Installation de Maven

```
$ sudo apt-get install maven
```

### Installation de Ansible 

```
$ sudo apt update
$ sudo apt install ansible
```

>  ### Définir les chemins de Java et de Maven 
> 
> Ouvrir le fichier /etc/environments : sudo nano /etc/environments
> Ajouter les lignes suivantes : (les chemins peuvent être trouver en checkant la version de java ou maven)
> JAVA_HOME = “java path”
> MAVEN_HOME="maven path"

Vous pouvez vérifier que votre LAB est prêt en lançant la commande suivante :  
```
$ cd metron/metron-deployment/scripts
$ ./platform-info.sh
```
## Deploiement d’Apache Metron
