# Micro_Service_Compte-service

# Objectif:

À la suite du cours de la programmation distribué l'objectif de ce TP est de présenter comment vous pouvez développer une micro service, ainsi comment vous pouvez le 

déployer en utilisant SprintBoot.


# Partie 1:

pour creer un projet basé sur SpringBoot on a besoin de quelques dependances:

![image](https://user-images.githubusercontent.com/102171913/163489747-d650bfd8-0dd1-4cdc-89fd-f3b7227c6aa2.png)

-Les dependances creés stocker dans le fichier pom.xml

-pour utiliser la base de donnee de type H2 on doit ajouter dans le fichier application.properties les lignes suivant:

![image](https://user-images.githubusercontent.com/102171913/163632090-b3942aaa-1253-43a4-9cdd-250a9f245a04.png)

#### L'execution:

![image](https://user-images.githubusercontent.com/102171913/163632129-7cb9eea1-25e2-46fd-b8c7-27223d869d8b.png)


#### Base de donnees: localhost:8080/h2-console compte_db

![image](https://user-images.githubusercontent.com/102171913/163632182-17255b66-8bb1-4c47-ab6e-9292782c1c92.png)

la creation du classe CompteRestController qui permet de retourner la liste des comptes  

![image](https://user-images.githubusercontent.com/102171913/163632351-e7fd3150-b76c-4e14-b4a4-a9f590db85e1.png)


#### Reamarque:

l'annotation '@GetMapping' contient une expression d’URL qui permet d'afficher tous les comptes 

Avans l'execution de ce code on a besion de changer le port car on a creer plusieur micro service dans la meme machine.

pour changer le port il suffit d'ajouter 
#### server.port = numPort  dans le fichier application.properties

#### L'execution dans le navigateur url/comptes:

![image](https://user-images.githubusercontent.com/102171913/163633448-2c7d844d-a85d-461d-a6fe-47e51e22c5ff.png)


-Pour ajouter un compte il suffit d'ajouter la methode suivant dans la classe CompteRestController, en utilisant l'annotation "PostMapping" :

![image](https://user-images.githubusercontent.com/102171913/163633632-d936823b-f8c6-4f5c-bb72-60352f2df3f9.png)

#### L'execution avec postman:

![image](https://user-images.githubusercontent.com/102171913/163633781-b7c9f688-077a-4376-b221-87e9c1aa2793.png)










