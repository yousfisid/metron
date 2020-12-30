# Apache Metron 

## IMPORTANT POUR LA CORRECTION DU PROJET 

Consulter les fichiers : ARTICLE.md et e-mail

## Mise en place du LAB

Avant de déployer la solution Apache Metron, vous devez vous assurer d’avoir les bons outils avec les bonnes versions :

* Python 2.7
* Pip 
* VirtualBox
* JAVA 8
* Vagrant / Vagrant Hostmanager
* docker
* Maven 
* Ansible

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
![pip](https://user-images.githubusercontent.com/44205421/103375062-736fd680-4ad9-11eb-94e4-9cffe4e2e56e.png)

### Installation de VirtualBox

```
$ sudo apt-get install virtualbox
```
![Virtualbox](https://user-images.githubusercontent.com/44205421/103375173-c5186100-4ad9-11eb-9364-85dafa1c60b9.png)

### Installation de JAVA

```
$ sudo add-apt-repository ppa:webupd8team/java
$ sudo apt install oracle-java8-installer
```
![java](https://user-images.githubusercontent.com/44205421/103375165-c053ad00-4ad9-11eb-8a64-ae32ff3fb31a.png)

### Installation de Vagrant 

```
$ sudo apt update
$ sudo apt install vagrant
```
![vagrant](https://user-images.githubusercontent.com/44205421/103375119-9c906700-4ad9-11eb-91a4-81f0c4204e2c.png)

### Installation de Maven

```
$ sudo apt-get install maven
```
![maven](https://user-images.githubusercontent.com/44205421/103375158-bcc02600-4ad9-11eb-80b5-5531e41d95a1.png)

### Installation de Ansible 

```
$ sudo apt update
$ sudo apt install ansible
```
![ansible](https://user-images.githubusercontent.com/44205421/103375170-c2b60700-4ad9-11eb-8166-8aa13f34e0b8.png)

>  ### Définir les chemins de Java et de Maven 
> 
> Ouvrir le fichier /etc/environments : sudo nano /etc/environments
> Ajouter les lignes suivantes : (les chemins peuvent être trouver en checkant la version de java ou maven)
>
>> JAVA_HOME = “java path”
>
>> MAVEN_HOME="maven path"

Vous pouvez vérifier que votre LAB est prêt en lançant la commande suivante :  
```
$ cd metron/metron-deployment/scripts
$ ./platform-info.sh
```
![capture4](https://user-images.githubusercontent.com/44205421/103375677-17a64d00-4adb-11eb-845b-e9290ace6db5.png)

## Deploiement d’Apache Metron
Une fois le LAB mis en place, il faut cloner le Github d’Apache Metron :
 
```
$ git clone https://github.com/yousfisid/metron.git
$ cd metron/metron-deployment/development/ubuntu14
$ vagrant up 
$ vagrant provision
```

> Note: Essayez de relancer plusieurs fois si cela ne fonctionne pas 

Une fois lancé, Vagrant va fonctionner en tant que “node1”


> ### Ambari : 
>> sur http://node1:8080/
> ### Kibana :
>> sur http://node1:5000/
> ### Monit : 
>> sur http://node1:2812/
>


## Problèmes rencontrés lors du déploiement de la solution Apache Metron

Lors du déploiement de la solution Apache Metron nous avions rencontré beaucoup de problèmes…

* Des fichiers .yml contenant des erreurs de syntax
* Des fichiers .yml écrit dans une version antérieur (installed remplacé par present) 
* Parfois des erreurs mais l'erreur n'est pas renvoyée (stderr : "" --> vide)

Nous avions eu plusieurs erreurs durant notre deploiement, mais nous n'avions pas le reflexe de prendre des screenshots… Voici les dernières que nous avions eu :

#### Problème 1 : erreur de syntax
![Bug5](https://user-images.githubusercontent.com/44205421/103387172-9bbffb00-4b02-11eb-9c18-7a49135397ee.png)

#### Problème 2 : "State: installed" remplacé par "state: present"

![unknown](https://user-images.githubusercontent.com/44205421/103387244-f78a8400-4b02-11eb-80d0-f15b3b8a3b87.png)

Les fichiers ont été modifié sur le git comme on peut le voir ici en lançant un git status : 

![capture5](https://user-images.githubusercontent.com/44205421/103387184-a7132680-4b02-11eb-8910-0d60a9638d7a.png)

#### Problème 3 : 
![Bug1](https://user-images.githubusercontent.com/44205421/103387178-a11d4580-4b02-11eb-9099-7a084a13d693.png)

#### Avancement : 

![SUCCESS](https://user-images.githubusercontent.com/44205421/103387161-8ba81b80-4b02-11eb-97b6-823dd4ce61ef.png)

