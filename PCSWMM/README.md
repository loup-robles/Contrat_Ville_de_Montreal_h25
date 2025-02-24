## Reprise du Projet PCSWMM.

## Rencontre avec Catherine MORIN

commencer par lui demander 
Questions : 

Nous pour faire notre modele 1d-2d on a fait :
- Create 2D Layer
- 4
![2D](https://github.com/user-attachments/assets/e3195f26-3e80-4839-9fbc-ba6c9fe5266a)
  - La couche frontiere représente la zone d'étude (le sous-bassin réduit)
  - La couche Noeuds 2D est la couche crée par le l'outil
  - La couche d'obstruction représente les batiments
  - DS Boundary condition est la couche limite du flux en aval (comment la choisir et la délimiter?)
  - MNT
- Polygone des routes
On veut attribuer une roughness de Manning moins élevé aux polygones délimitant les routes qu'au reste du territoire. On cherche à dire au logiciel que l'eau ruisselle mieux sur l'emprise des routes qu'ailleurs.
- Générer les points 2D
- 
![image](https://github.com/user-attachments/assets/75cce9c0-1658-41de-b713-ab69b6c77cb0)

- Créer le maillage 2D
- 
![image](https://github.com/user-attachments/assets/f392426d-6f7b-4a0d-9b37-839379a4f1c8)

- connecter 1D et 2D
Interogation sur ce point : Pour connecter le reseau 1D au 2D on utilise les jonctions on renommant leur étiquettes "CONNECT2D". quels jonctions doit on renommer? sur quel critère?

- Add downtsream boundary line

- possible d'exporter les données ailleurs de PCSWMM?
- 
