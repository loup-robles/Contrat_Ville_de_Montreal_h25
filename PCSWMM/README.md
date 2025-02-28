## Reprise du Projet PCSWMM.

## Rencontre avec Catherine MORIN

commencer par lui demander si elle serait ouverte à nous partager quelques éléments de leur métohodologie

Questions : 

Nous pour faire notre modele 1d-2d on a fait :
- Create 2D Layer

![2D](https://github.com/user-attachments/assets/e3195f26-3e80-4839-9fbc-ba6c9fe5266a)
  - La couche frontiere représente la zone d'étude (le sous-bassin réduit)
  - La couche Noeuds 2D est la couche crée par le l'outil
  - La couche d'obstruction représente les batiments
  - DS Boundary condition est la couche limite du flux en aval (comment la choisir et la délimiter?)
  - MNT
- Polygone des routes
On veut attribuer une roughness de Manning moins élevé aux polygones délimitant les routes qu'au reste du territoire. On cherche à dire au logiciel que l'eau ruisselle mieux sur l'emprise des routes qu'ailleurs.
- Générer les points 2D

![image](https://github.com/user-attachments/assets/75cce9c0-1658-41de-b713-ab69b6c77cb0)

- Créer le maillage 2D

![image](https://github.com/user-attachments/assets/f392426d-6f7b-4a0d-9b37-839379a4f1c8)

- connecter 1D et 2D
Interogation sur ce point : Pour connecter le reseau 1D au 2D on utilise les jonctions on renommant leur étiquettes "CONNECT2D". quels jonctions doit on renommer? sur quel critère?

- dessiner la downtsream boundary line
- Pour les options de simulations: Comment créer un scénarios et l'utiliser pour les calculs? J'ai essayé d'en créer de nouveau mais il semblait utiliser toujours le même à chaque fois.

## Résumé des questions : 

1. Comment choisir la DS Boundary line ?
2. Comment choisir les points de jonctions à renommer pour connecter 1D au 2D ?
3. Comment créer un scénario et l'utiliser pour le calcul ?
4. Comment gérer les *storages* ? est-ce pertinent de créer un *storage* par regard d'égout ?
5. Possible d'exporter les données ailleurs de PCSWMM? Dans une base de données PostGIS ?


## Réponse :

- Reduire la résolution du projet ou reduire la zone (tester avec une résolion de 40m)
- Decouper en réseau et automatiser (couper avec des tuiles logique selon le ruissellement)
- Évaluer le volume de chaque cuvette pour calculer selon le volume de pluie cb ca prendrais de la remplir
- Chaque storage simule la capatité du nombre de puisard d'une zone (si le puisard est plus bas il a une plus grosse capacité)
- Une pluie 10 ans permettrait pas de remplir toutes les cuvettes
- Pour limiter le temps de traitement : faire par batch

Certaines questions non posées demeuraient sans réponses (questions 1, 2 et 3). Contact avec le support PCSWMM pour avoir des réponses.
Réponse de ellen@chiwater.com : 

*Hi Loup*,

 

*I am one of the engineers and was forwarded your questions. We don’t generally offer technical support to users with the Educational Grant, but I’ll do my best to point you in the right direction! I’ve included your original questions below with responses in blue.*

*The 1D-2D connection is done by renaming the labels of some junctions. In the tutorials, only a few junctions are renamed. How do you determine which junctions should be renamed? There are hundreds of junctions in the PCSWMM project I received. Should I rename all of them?
The “Tag” of nodes is updated to “Connect2D” to represent the areas where there is a connection between the 1D system and the 2D system. I.e. where there are catchbasins, or where there are ditches/streams. Where there are catchbasins, you’ll use orifices to connect the 1D elements to the 2D mesh. Where there are no flow control devices, you’ll use direct connections. Please refer to the following article for more details: https://support.chiwater.com/77628/connect-1d-to-2d*

*On what features is the downstream boundary line drawn?
The downstream boundary line is wherever your mesh ends. It could be a river, a hillside, or some arbitrary boundary. It’s what allows flow to leave the mesh. In other words, the boundary of your model. If you don’t include it, the mesh boundary will act as a wall and water will back up. To quote the relevant article “The downstream layer is recommended when the flood waters reach the extent of the bounding layer and the user is not interested in the flooding downstream”: https://support.chiwater.com/77737/downstream-layer?p=TdlTdl&h=TdlTdl,1,2,3*

*In the project I received, the scenarios are already built. However, when I try to add a new scenario, every time I start the simulation, I get the same results as if the software is still using the old scenario instead of the one I just created. How can I assign the new scenario and ensure that it’s used for the modeling?
It’s difficult to say what’s happening here without seeing it, but I have a few notes. First, when you “duplicate” a scenario, you need to open the new scenario before proceeding – the same scenario will stay open otherwise. Secondly, 2D layers are background layers (shapefiles), which means if your scenarios are using the same 2D Nodes, 2D Cells, Downstream, Bounding, etc. layers, editing them for one scenario will edit them for all the others. You need to create different versions of these layers for different scenarios if you want to see a difference between scenarios. Third, if you want to compare the model difference between two scenarios (and ensure there is actually a difference), you can use the “Status” and “Details” panels with the comparison tools to see the differences: https://support.chiwater.com/79801/comparing-scenario-results*

*Lastly, is it possible to connect PCSWMM with a relational database, such as PostGIS, to push data into the software and retrieve results from the database?
Automatic sync is not possible. We used to sync automatically with external sources, but this caused some users problems when external software edited the SWMM layers and it became unusable with the SWMM engine on which PCSWMM is built. Pushing and pulling to/from databases is possible using scripting, though: https://support.chiwater.com/175035/script-example-work-with-azure-database-for-postgresql . You can also use the import  and export  as you need: https://support.chiwater.com/77958/importing-data*


--> Mettre en application les pistes du support


