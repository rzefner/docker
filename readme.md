Procedure deploiement logiciel "stock des chaussures" :

dans un premier temps, il faut copier l'ensemble des dossiers dans un dossier vide contenu sur le lien : https://github.com/rzefner/docker
à la racine de votre disque (Dossier "postgres" et "tomcat")

- d'abord il faut se placer dans le dossier "postgres"
- lancer les commandes suivantes:
$ docker build -t mypostgres .
$ docker run -d --name db -v dbdata:/var/lib/postgres/data mypostgres

- Puis à partir du dossier "tomcat"
- lancer les commandes suivantes:
$ docker build -t mytomcat3 .
$ docker run -d --name mytomcat3 --link db -p 9228:8080 mytomcat3

- une fois ces commandes executées
- à partir de votre navigateur web, pour se connecter à l'application il faut rentrer l'url : 
localhost:8080/dbproject/accueil.jsp


auteur : Zefner Remi