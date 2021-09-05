# bank-account-management
you will find below a description in French and English  

vous trouverez ci-dessous une description en français et en anglais



-> 

video demo link : https://www.dailymotion.com/video/x83yqhi

video password : bank-account-management-video

## English 


the project revolves around these functionalities:

Allow administrator, branch manager, cashier and customer to authenticate.

Allow the administrator to manage the bankers.

Allow the branch manager, the client and the cashier to view a client's information.

Allow the branch manager to view information on cashiers.

Allow the cashier to manage customers and their accounts.

Allow the cashier and the customer to manage banking operations and consult their history.

![1](https://user-images.githubusercontent.com/44647099/132127309-ee2ce2e6-784a-414f-b864-cc64de0e57e2.jpg)

* Database

![2](https://user-images.githubusercontent.com/44647099/132127366-29794ec0-1c4d-463c-9c76-f543dc0500b5.jpg)

### BackEnd

* Bankers management

use case diagram

![3](https://user-images.githubusercontent.com/44647099/132127543-398489a6-6b8f-49c9-b044-bd7b84cc0b6a.png)

class diagram

![4](https://user-images.githubusercontent.com/44647099/132127556-add3e1d0-b4eb-43d8-95e0-9aeabc564e6f.jpg)

package diagram

![6](https://user-images.githubusercontent.com/44647099/132127559-b3ca3171-d994-410e-a315-eb37ca40e454.jpg)

sequence diagram : "verification of the existence of an employee"

![7](https://user-images.githubusercontent.com/44647099/132127560-5c68a099-fecd-48cd-a758-4c48d40e2dba.png)

The getConnection () method will be launched from the "Employee" controller followed by a "connect" response of type java.sql.connection. Then there will be a creation of a new employee with an "emp" tag to contain the information that will be returned by the database.
The use of the hash function is also mandatory to compare between the information entered and the information stored in the database since it is encrypted.
Indeed, to verify the existence of an employee, an “executeQuery (sql)” query after the creation of the “sql” query in the form of a “string” will be launched and followed by a response following a verification. performed in the database.
Through the retrieved response, a modification of the attributes of “emp” will be performed. And finally, the connection will be closed and thus convert the object "emp" to a type "JSON" and return it.

* Account and customer management

use case diagram

![8](https://user-images.githubusercontent.com/44647099/132127743-3defdeb0-78c8-4d03-9476-827a4828d2b5.jpg)

class diagram

![9](https://user-images.githubusercontent.com/44647099/132127745-577b78fa-b2e8-43b9-8a47-75c00474f9f0.png)

package diagram

![10](https://user-images.githubusercontent.com/44647099/132127748-3bdc8bb0-5ad6-404a-b989-fb52f633f718.png)

sequence diagram : "getClient"

![12](https://user-images.githubusercontent.com/44647099/132127823-3563c30d-bb40-4e35-aa38-f921f5a873d9.png)

In order to display the contact details of the client, first the getConnection () method will be launched from the "Client" controller followed by a "connect" response of type java.sql.connection. Then there will be a creation of a new customer with a "clt" tag to contain the information that will be returned by the database.
Then a sql query will be created and for it to be executed we have created a "statement" and then a result will be sent to the "Client". So a modification of the "clt" from this result.
There will also be a creation of a list of "lcmp" accounts. A new “sql2” query will be created and through “statement2” this query will be executed by the “executeQuery (Sql2)” method and we then retrieve “results2” which contains the list of the client's accounts. For each element of this list, there will be an instantiation of a new "cmp" account by modifying its attributes based on the content of "results2". Finally, there is an addition of this element to "lcmp" and this list will be assigned to "clt.Lcompte".
After these treatments, you must close the connection, convert the client “clt” to “JSON” and return the result.

sequence diagram : "Credit"

![13](https://user-images.githubusercontent.com/44647099/132127824-005c0fc4-ca45-4b8d-b339-253571f49321.png)

In order to credit an account, first the getConnection () method will be launched from the "Account" controller followed by a "connect" response of type java.sql.connection. Then there will be a creation of a new account with a "cmp" label to contain the information that will be returned by the database on the account status before modification.
Then a sql query will be created and for it to be executed we have created a "statement" and then a result will be sent to the "Account". So, a modification of "cmp" from this result.
Then, an instantiation of the history "his" will be performed as well as the calculation of the final balance.
This diagram also includes the recording of the initial balance and the initial overdraft in "his" and these two values after modification. After that, a new request will be made to start adding the amount of money. Thus, a test will be performed according to the recovered result. Indeed, if the addition is carried out successfully, there will be a reference on the diagram “Add History”, closing of the connection and return of a message “addition carried out successfully” otherwise closing of the connection and return of a message "problem in crediting".

sequence diagram : "update history"

![14](https://user-images.githubusercontent.com/44647099/132127826-de90349c-e85a-46a0-806d-685ab1b6524a.png)

if a customer credits or debits the account, there is a record of the history and therefore of the last manipulation. Indeed, this scenario will unfold in the same way as the others.


### FrontEnd

* Human-Machine Interface (HMI)

use case diagram

![20](https://user-images.githubusercontent.com/44647099/132128411-b71374f2-41fa-431d-893e-b18e7151f125.jpg)

package diagram



red: this is a package that contains a file name.module.ts and another name-routing.module.ts.

blue: it is a component which contains a file name.component.html and name.component.ts.

purple: this is the set of files whose packages are represented by red and blue.


![22](https://user-images.githubusercontent.com/44647099/132128414-b215cca3-7f7e-4085-85f4-43614005876d.png)


components

![21](https://user-images.githubusercontent.com/44647099/132128413-d27925b0-6d31-432b-9fbc-ca2bba6aebd4.png)

redirects table

![55](https://user-images.githubusercontent.com/44647099/132128641-84a15bb0-0b80-496f-bef8-493de22c4dc2.PNG)

* Integration 

use case diagram

![24](https://user-images.githubusercontent.com/44647099/132128416-906eac8e-da81-4cf7-a030-1811a66178ac.jpg)

class diagram

![25](https://user-images.githubusercontent.com/44647099/132128418-d92e28f4-5006-4f23-9a25-13e106d6ae18.png)

package diagram

![26](https://user-images.githubusercontent.com/44647099/132128425-15ddcd96-7c1e-4569-8384-e3fd1209f043.png)

sequence diagram : "adding a customer"

![27](https://user-images.githubusercontent.com/44647099/132128427-8e86a1e7-90f0-41d4-bb7e-23270aafd1d5.png)

At the beginning, the “FrontEnd Client” fills in the fields that are on the “add” view then validate so that this view sends to the “add” controller an “onSubmitClient (value)” request. The latter must imperatively check the validity of the filling in of the fields.
Indeed, if they are correctly filled, there will be a “clt1” instantiation of the client from the “client” model. All the fields filled in correctly will be put in the attributes which correspond to them in “clt1”. This action will be followed by a message confirming the processing carried out by the user. If the “FrontEnd Client” approves the action and therefore the controller receives this confirmation. This controller executes the “addClient (clt1)” method found in the “ClientService” service which will send an “HTTP Request” to the WEB API which will return an “HTTP Response”. Finally, a message will be displayed to the “FrontEnd Client” and the fields will be emptied.
If any of the fields are not valid, the view identifies it.


## Français 

le projet s’articule autour de ces fonctionnalités :

Permettre à l’administrateur, le chef d’agence, le caissier et le client de s’authentifier.

Permettre à l’administrateur de gérer les banquiers.

Permettre au chef d’agence, au client et au caissier de consulter les informations d’un client.

Permettre au chef d’agence de consulter les informations sur les caissiers.

Permettre au caissier de gérer les clients et leurs comptes.

Permettre au caissier et au client de gérer les opérations bancaires et de consulter leur historique.

![1](https://user-images.githubusercontent.com/44647099/132127309-ee2ce2e6-784a-414f-b864-cc64de0e57e2.jpg)


* Base de données

![2](https://user-images.githubusercontent.com/44647099/132127366-29794ec0-1c4d-463c-9c76-f543dc0500b5.jpg)

### BackEnd

* Gestion des banquiers

diagramme de cas d'utilisation

![3](https://user-images.githubusercontent.com/44647099/132127543-398489a6-6b8f-49c9-b044-bd7b84cc0b6a.png)

diagramme de classe

![4](https://user-images.githubusercontent.com/44647099/132127556-add3e1d0-b4eb-43d8-95e0-9aeabc564e6f.jpg)

diagramme de package

![6](https://user-images.githubusercontent.com/44647099/132127559-b3ca3171-d994-410e-a315-eb37ca40e454.jpg)

diagramme de séquence : "vérification de l'existence d'un employé"

![7](https://user-images.githubusercontent.com/44647099/132127560-5c68a099-fecd-48cd-a758-4c48d40e2dba.png)

La méthode getConnection() sera lancée de la part du contrôleur « Employé » suivie d’une réponse « connect » de type java.sql.connection. Ensuite, il y aura une création d’un nouvel employé avec une étiquette « emp » pour contenir les informations qui seront retournées par la base de données.
L’utilisation de la fonction de hachage est obligatoire aussi pour comparer entre les informations entrées et les informations stockées dans la base de données puisqu’elles sont cryptées.
En effet, pour vérifier l’existence d’un employé une requête “executeQuery(sql)” après la création de la requête “sql” sous la forme d’un “string” sera lancée et suivie d’une réponse suite à une vérification effectuée dans la base de données.
A travers la réponse récupérée, une modification des attributs de « emp » sera effectuée. Et enfin, la connexion sera fermée et ainsi convertir l’objet « emp » en un type « JSON» et le retourner.


* Gestion des comptes et des clients

diagramme de cas d'utilisation

![8](https://user-images.githubusercontent.com/44647099/132127743-3defdeb0-78c8-4d03-9476-827a4828d2b5.jpg)

diagramme de classe

![9](https://user-images.githubusercontent.com/44647099/132127745-577b78fa-b2e8-43b9-8a47-75c00474f9f0.png)

diagramme de package

![10](https://user-images.githubusercontent.com/44647099/132127748-3bdc8bb0-5ad6-404a-b989-fb52f633f718.png)

diagramme de séquence : "getClient"

![12](https://user-images.githubusercontent.com/44647099/132127823-3563c30d-bb40-4e35-aa38-f921f5a873d9.png)

Afin d’afficher les coordonnées du client, tout d’abord la méthode getConnection() sera lancée de la part du contrôleur « Client » suivie d’une réponse « connect » de type java.sql.connection. Ensuite, il y aura une création d’un nouveau client avec une étiquette « clt » pour contenir les informations qui seront retournées par la base de données.
Ensuite, une requête sql sera créée et pour qu’elle soit exécutée nous avons créé un « statement » et puis un résultat sera envoyé au « Client ». Ainsi, une modification de la « clt » à partir de ce résultat.
Il y aura aussi une création d’une liste de comptes ”lcmp”. Une nouvelle requete “sql2” sera créée et à travers “statement2” cette requête sera exécutée par la méthode “executeQuery(Sql2)” et nous récupérons alors le “resultats2” qui contient la liste des comptes du client. Pour chaque élément de cette liste, il y aura une instanciation d’un nouveau compte « cmp » en modifiant ses attributs en se basant sur le contenu du « resultats2 ». Enfin, il y a un ajout de cet élément à « lcmp » et cette liste sera affectée à « clt.Lcompte ».
Après ces traitements, il faut fermer la connexion, convertir le client “clt” en “JSON” et retourner le résultat.

diagramme de séquence : "Créditer"

![13](https://user-images.githubusercontent.com/44647099/132127824-005c0fc4-ca45-4b8d-b339-253571f49321.png)

Afin de créditer un compte, tout d’abord la méthode getConnection() sera lancée de la part du contrôleur « Compte » suivie d’une réponse « connect » de type java.sql.connection. Ensuite, il y aura une création d’un nouveau compte avec une étiquette « cmp » pour contenir les informations qui seront retournées par la base de données sur l’état du compte avant modification.
Ensuite, une requête sql sera créée et pour qu’elle soit exécutée nous avons créé un « statement » et puis un résultat sera envoyé au « Compte ». Ainsi, une modification de « cmp » à partir de ce résultat.
Puis, une instanciation de l’historique “his” sera effectuée ainsi que le calcul du solde final.
Ce diagramme comporte aussi l’enregistrement du solde initial et du découvert initial dans “his” et ces deux valeurs après modification. Après, une nouvelle requête sera faite pour lancer l’ajout de la somme d’argent. Ainsi, un test sera effectué selon le résultat récupéré. En effet, si l’ajout est effectué avec succès, il y aura une référence sur le diagramme “Ajouter Historique”, fermeture de la connexion et retour d’un message “ajout effectuer avec succès” sinon fermeture de la connexion et retour d’un message”problème dans créditer”.

diagramme de séquence : "mise à jour de l’historique"

![14](https://user-images.githubusercontent.com/44647099/132127826-de90349c-e85a-46a0-806d-685ab1b6524a.png)

si un client crédite ou débite le compte, il y a un enregistrement de l’historique et donc de la dernière manipulation. En effet, ce scénario se déroulera de la même manière que les autres.

### FrontEnd

* Interface Homme-Machine (IHM)

diagramme de cas d'utilisation

![20](https://user-images.githubusercontent.com/44647099/132128411-b71374f2-41fa-431d-893e-b18e7151f125.jpg)

diagramme de package

rouge : il s'agit d'un package qui contient un fichier name.module.ts et un autre name-routing.module.ts.

bleu : c'est un composant qui contient un fichier name.component.html et name.component.ts.

violet : c'est l'ensemble des fichiers dont les packages sont représentés en rouge et en bleu.


![22](https://user-images.githubusercontent.com/44647099/132128414-b215cca3-7f7e-4085-85f4-43614005876d.png)


components

![21](https://user-images.githubusercontent.com/44647099/132128413-d27925b0-6d31-432b-9fbc-ca2bba6aebd4.png)

tableau des redirections

![55](https://user-images.githubusercontent.com/44647099/132128641-84a15bb0-0b80-496f-bef8-493de22c4dc2.PNG)

* L'intégration 

diagramme de cas d'utilisation

![24](https://user-images.githubusercontent.com/44647099/132128416-906eac8e-da81-4cf7-a030-1811a66178ac.jpg)

diagramme de classe

![25](https://user-images.githubusercontent.com/44647099/132128418-d92e28f4-5006-4f23-9a25-13e106d6ae18.png)

diagramme de package

![26](https://user-images.githubusercontent.com/44647099/132128425-15ddcd96-7c1e-4569-8384-e3fd1209f043.png)

diagramme de séquence : "ajout d'un client"

![27](https://user-images.githubusercontent.com/44647099/132128427-8e86a1e7-90f0-41d4-bb7e-23270aafd1d5.png)

Au début, le “Client FrontEnd” remplit les champs qui se trouvent sur la vue “ajouter” puis valider pour que cette vue envoie au contrôleur “ajouter” une demande “onSubmitClient(value)”. Ce dernier doit impérativement vérifier la validité du remplissage des champs.
En effet, s’ils sont correctement remplis, il y aura une instanciation “clt1” du client à partir du modèle “client”. Tous les champs remplis correctement seront mis dans les attributs qui leurs correspondent dans “clt1”. Cette action sera suivie par un message de confirmation du traitement effectué par l’utilisateur. Si le “Client FrontEnd” approuve l’action et donc le contrôleur reçoit ainsi cette confirmation. Ce contrôleur exécute la méthode “ajouterClient(clt1)” qui se trouve dans le service “ClientService” qui va envoyer une “HTTP Request” à la WEB API qui va lui retourner une “HTTP Response”. Enfin, un message sera affiché au “Client FrontEnd” et les champs seront vidés.
Si un des champs n’est pas valide, la vue l’identifie.


