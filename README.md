# Micro_Service_Compte-service

# Objectif:

À la suite du cours de la programmation distribué l'objectif de ce TP est de présenter comment vous pouvez développer une micro service, ainsi comment vous pouvez le 
déployer en utilisant SprintBoot.


# Partie 1:

Dans cette partie on va creé un simple micro-service(une application qui permet de gérer les comptes bancaire) avec spring boot.

pour creer un projet basé sur SpringBoot on a besoin de quelques dependances:

![image](https://user-images.githubusercontent.com/102171913/163489747-d650bfd8-0dd1-4cdc-89fd-f3b7227c6aa2.png)

-Les dependances creés stocker dans le fichier pom.xml

Tout d'abord on a creer la classe compte en utilisant les annotations de Lobok et springBoot pour faciliter le travail.
Ensuite on a creer l'interface CompteRepository qui été hirité de la classe JpaRespository.
Puis on a tester notre application par definir des comptes dans le main et on a les stocké dans la base de données comptedb on utilisant H2 

-pour utiliser la base de donnee de type H2 on doit ajouter dans le fichier application.properties les lignes suivant:

![image](https://user-images.githubusercontent.com/102171913/163632090-b3942aaa-1253-43a4-9cdd-250a9f245a04.png)

#### L'execution:

![image](https://user-images.githubusercontent.com/102171913/163632129-7cb9eea1-25e2-46fd-b8c7-27223d869d8b.png)


#### Base de donnees: localhost:8080/h2-console compte_db

![image](https://user-images.githubusercontent.com/102171913/163632182-17255b66-8bb1-4c47-ab6e-9292782c1c92.png)

Avans l'execution de ce code on a besion de changer le port car on a creer plusieur micro service dans la meme machine.

pour changer le port il suffit d'ajouter 
#### server.port = numPort  dans le fichier application.properties

la creation du classe CompteRestController qui permet de retourner la liste des comptes  

![image](https://user-images.githubusercontent.com/102171913/163632351-e7fd3150-b76c-4e14-b4a4-a9f590db85e1.png)
![image](https://user-images.githubusercontent.com/102171913/163635581-43cc01d6-ef39-4420-8920-d4df3e50a28f.png)


#### Remarque:

l'annotation '@GetMapping' contient une expression d’URL qui permet d'afficher tous les comptes 

puis on a ajouté une methode qui permer d'afficher un compte par son code:

![image](https://user-images.githubusercontent.com/102171913/163635454-2b109489-105f-4f69-9f5c-4835702238f4.png)
![image](https://user-images.githubusercontent.com/102171913/163635475-b1d982b5-5aa3-4414-b5d8-6af7f2da5d76.png)

-Pour ajouter un compte il suffit d'ajouter la methode suivant dans la classe CompteRestController, on utilise l'annotation "@PostMapping" :

![image](https://user-images.githubusercontent.com/102171913/163633632-d936823b-f8c6-4f5c-bb72-60352f2df3f9.png)

-pour modifier un compte on utilise l'annotation '@PuMapping'

![image](https://user-images.githubusercontent.com/102171913/163639905-7907f24f-e0df-4c4e-a0f3-c037f4456235.png)

-pour supprimer un compte on utilise l'annotation '@DeleteMapping'

![image](https://user-images.githubusercontent.com/102171913/163640771-995b0980-e60b-4b08-880f-bd67855e4d45.png)


#### L'execution avec postman:

![image](https://user-images.githubusercontent.com/102171913/163633781-b7c9f688-077a-4376-b221-87e9c1aa2793.png)

#### L'ajout d'un  compte:

![image](https://user-images.githubusercontent.com/102171913/163641260-408d2dca-21d9-4610-9245-8fdbf282deb7.png)

#### Modifier :

![image](https://user-images.githubusercontent.com/102171913/163642207-a2a1e2c5-52ce-4269-b9a1-50acdadce326.png)

#### Supprimer:

![image](https://user-images.githubusercontent.com/102171913/163643981-3bbda3ca-3c5e-48f0-8efb-d3ad23caf67d.png)

#### Explorant la documentation API:

![image](https://user-images.githubusercontent.com/102171913/163645745-66bd2cd4-58f6-4e55-a175-70dd7d7a4e78.png)

en important la documentation API dans postman pour facilter le travail tel que on peut afficher,modifier 
#### Exemples: 

#### Afficher la liste des comptes :

![image](https://user-images.githubusercontent.com/102171913/163648294-30947778-f3d6-4476-b692-0271ba759b5a.png)

#### Afficher un compte specifie:

![image](https://user-images.githubusercontent.com/102171913/163648328-7992726e-a579-4073-9c33-51bc19387419.png)

#### Ajouter un compte:

![image](https://user-images.githubusercontent.com/102171913/163648350-ad5f5600-c0b6-4478-ab04-5a6cfeed3471.png)

#### Modifier:

![image](https://user-images.githubusercontent.com/102171913/163648366-22e221a5-97ef-4c83-afdf-c222f7980889.png)

#### Supprimer:

![image](https://user-images.githubusercontent.com/102171913/163648388-ae21d082-c305-48a6-b925-5ddde51857f3.png)

Une autre methode pour tester le micro-service:

#### swagger :

#### Afficher:

![image](https://user-images.githubusercontent.com/102171913/163648523-dae37332-420d-4662-84bb-92d0d4f05732.png)

#### Ajouter:

![image](https://user-images.githubusercontent.com/102171913/163648554-9b7db629-dc35-4c77-822a-dadf164b3935.png)

#### Supprimer:

![image](https://user-images.githubusercontent.com/102171913/163648850-afae3c9a-9ae9-4a24-bc78-0e2e69471b8a.png)

Apres ona cree une interface pour faire la projection pour cela on a utilisé l'annotation '@Projection'

#### Exemple:

#### projection pour afficher le code et le solde:

![image](https://user-images.githubusercontent.com/102171913/163650294-253a077b-f917-42e4-bc0e-f7acf8cdbbde.png)
![image](https://user-images.githubusercontent.com/102171913/163650489-6ba0fc49-7cc4-40c5-92ec-292bdca74d27.png)


#### projection pour afficher le solde et le type:

![image](https://user-images.githubusercontent.com/102171913/163650410-6844c6e2-8a06-445b-bca6-a1d0d6058d02.png)
![image](https://user-images.githubusercontent.com/102171913/163650513-7668fdf9-d274-4b40-be1f-7533f54fa3ef.png)

#### Interface Virement:

 on a creer l'interface Compte service pour definir une methode virement  

Apres on a Creer un autre rest controller pour tester la methode virement et on a creé une classe DTO pour definir les parametre dont on a besoin pour faire un virement :

![image](https://user-images.githubusercontent.com/102171913/163650943-c5a426ba-c163-4863-9b09-c5553dc9436e.png)

#### Teste:
#### Les comptes avant le virement:

![image](https://user-images.githubusercontent.com/102171913/163651081-b44119f8-e6d6-40b9-a880-cd7024f3eb5f.png)


On appplique un virement de 800Dh de compte 1 vers le compte 2:

![image](https://user-images.githubusercontent.com/102171913/163650999-cdb460ac-cba1-42c2-8034-c7200ed0c9fa.png)

#### Les compte apres le virement:

![image](https://user-images.githubusercontent.com/102171913/163651051-ed399a94-e71f-4012-80d1-42a339062dc8.png)





 











