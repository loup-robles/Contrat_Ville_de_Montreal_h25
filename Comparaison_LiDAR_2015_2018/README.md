# Comparaison LiDAR 2015 et 2018

## Contexte
La classification des données LiDAR de 2015 et 2018 a été réalisée à l'aide de deux algorithmes différents, entraînant des disparités dans les résultats.

## Objectif
Comparer les données de plusieurs tuiles afin d’identifier les différences dans la classification des nuages de points.

## Données
- **LiDAR 2015** : disponible sur le portail des données ouvertes de la Ville de Montréal.
- **LiDAR 2018** : données sur disque physique, transmises par la Ville de Montréal lors du contrat pour la mise à jour de la carte de vulnérabilité face aux pluies abondantes de l'été 2024.

## Méthodologie
1. Sélection de 5 à 6 tuiles LiDAR 2015 sur le portail des données ouvertes de la Ville de Montréal.

2. Conversion des fichiers **.LAZ** en **.LAS** :

- Sur *ArcGIS*, utiliser l'outil **Convertir des fichiers LAS** avec les paramètres suivants :
	-  Aucune compression
	-  Toutes les options LAS décochées
	-  Fichier LAS sans référence spatiale avec **EPSG : 32188** ou **EPSG : 2950** (4140 ne fonctionne pas).
 
3. Calculer des statistiques sur chaque tuile.

    - Sur ArcGIS avec **Statistiques d'un jeu de données LAS**

5. Comparer les statistiques entre 2015 et 2018 pour chaque tuiles


# 1er Échantillon de test 

## Tuiles sélectionnées
- **299-5042** (sud-ouest du Parc La Fontaine)
- **297-5043** (ouest du parc Laurier)
- **297-5040** (Mont-Royal)
- **300-5046** (Parc Maisonneuve, stade olympique)
- **292-5048** (Parc-nature de l'Île-de-la-Visitation)
- **284-5040** (Parc-nature du Bois-de-Liesse)


![alt text](image.png)


## Comparaison

### 299-5042
| Classification     | Nb points 2015 | Nb points 2018 | Pourcentage 2015 | Pourcentage 2018 | Différence 2018-2015 |
|-------------------|----------------|----------------|------------------|------------------|----------------------|
| Tous              | 18.3 M         | 29.1 M         | 100 %            | 100 %            | x                    |
| Non classifié     | 4.6 M          | 6.4 M          | 25.37 %          | 22.14 %          | <mark>-3.23 %        |
| Végétation haute  | 2.3 M          | 12.6 M         | 12.34 %          | 43.2 %           | <mark>+30.86 %       |
| Bâtiments         | 5.4 M          | 6.8 M          | 29.28 %          | 22.27 %          | -7.01 %              |

### 297-5043
| Classification     | Nb points 2015 | Nb points 2018 | Pourcentage 2015 | Pourcentage 2018 | Différence 2018-2015 |
|-------------------|----------------|----------------|------------------|------------------|----------------------|
| Tous              | 21.1 M         | 24.2 M         | 100 %            | 100 %            | x                    |
| Non classifié     | 6.9 M          | 7.6 M          | 32.93 %          | 31.22 %          | <mark> -1.71 %       |
| Végétation haute  | 1.3 M          | 6.0 M          | 5.92 %           | 24.71 %          | <mark> +18.79 %      |
| Bâtiments         | 5.7 M          | 6.3 M          | 27.07 %          | 25.92 %          | -1.15 %              |

### 297-5040
| Classification     | Nb points 2015 | Nb points 2018 | Pourcentage 2015 | Pourcentage 2018 | Différence 2018-2015 |
|-------------------|----------------|----------------|------------------|------------------|----------------------|
| Tous              | 29.2 M         | 26.0 M         | 100 %            | 100 %            | x                    |
| Non classifié     | 1.4 M          | 8.2 M          | 8.47 %           | 31.57 %          | <mark>+23.1 %        |
| Végétation haute  | 1.9 M          | 8.9 M          | 11.51 %          | 34.46 %          | <mark>+22.95 %       |
| Bâtiments         | 2.9 M          | 3.9 M          | 17.8 %           | 14.88 %          | -2.92 %              |

### 300-5046
| Classification     | Nb points 2015 | Nb points 2018 | Pourcentage 2015 | Pourcentage 2018 | Différence 2018-2015 |
|-------------------|----------------|----------------|------------------|------------------|----------------------|
| Tous              | 21.1 M         | 24.2 M         | 100 %            | 100 %            | x                    |
| Non classifié     | 6.9 M          | 7.6 M          | 32.93 %          | 31.22 %          | <mark>-1.71 %        |
| Végétation haute  | 1.3 M          | 6.0 M          | 5.92 %           | 24.71 %          | <mark>+18.79 %       |
| Bâtiments         | 5.7 M          | 6.3 M          | 27.07 %          | 25.92 %          | -1.15 %              |

### 292-5048
| Classification     | Nb points 2015 | Nb points 2018 | Pourcentage 2015 | Pourcentage 2018 | Différence 2018-2015 |
|-------------------|----------------|----------------|------------------|------------------|----------------------|
| Tous              | 16.0 M         | 27.8 M         | 100 %            | 100 %            | x                    |
| Non classifié     | 4.5 M          | 6.0 M          | 28.04 %          | 21.66 %          | <mark>-6.38 %        |
| Végétation haute  | 3.0 M          | 14.6 M         | 18.88 %          | 52.69 %          | <mark>+33.81 %       |
| Bâtiments         | 2.3 M          | 3.0 M          | 14.02 %          | 10.81 %          | -3.21 %              |

### 284-5040
| Classification     | Nb points 2015 | Nb points 2018 | Pourcentage 2015 | Pourcentage 2018 | Différence 2018-2015 |
|-------------------|----------------|----------------|------------------|------------------|----------------------|
| Tous              | 17.0 M         | 31.7 M         | 100 %            | 100 %            | x                    |
| Non classifié     | 6.5 M          | 7.5 M          | 38.27 %          | 23.53 %          | <mark>-14.74 %       |
| Végétation haute  | 1.8 M          | 16.7 M         | 10.41 %          | 52.75 %          | <mark>+42.34 %       |
| Bâtiments         | 1.1 M          | 1.4 M          | 6.31 %           | 4.47 %           | -1.84 %              |


## Conclusion

Sur cet échantillon, on observe une baisse globale du pourcentage de données non classifiées entre 2015 et 2018, à l'exception d’une seule tuile. Cette dernière correspond à une partie du Mont-Royal.
En revanche, le nombre de points classifiés en **"Végétation haute"** augmente significativement entre les deux années, avec une hausse moyenne de 27 % entre 2015 et 2018.

### Pistes expliquant ces différences

La forte augmentation du pourcentage de points classifiés en **"Végétation haute"** entre 2015 et 2018 peut s'expliquer par plusieurs facteurs. Le portail des données ouvertes de la Ville de Montréal indique que les données **LiDAR 2015** ont été mises à jour en **novembre 2015**. Cependant, il n’est pas précisé si cette mise à jour correspond à la date de production ou simplement à la date de traitement des données.

Si la donnée a effectivement été acquise en novembre 2015, une période où la végétation est réduite, cela pourrait expliquer cette différence dans la classification.

Pour valider cette hypothèse, il serait nécessaire d’obtenir les dates exactes de production des données LiDAR **2015** et **2018**.


## À faire pour le LiDAR

L’échantillon sélectionné étant trop restreint, il ne permet pas de tirer des conclusions définitives sur les différences de classification entre 2015 et 2018.

➡ **Trouver une solution pour réaliser ce résumé statistique sur l’ensemble des tuiles.**

Pour chaque tuile :
  - Calculer les statistiques de **2015** et **2018**
  - Calculer le poucentage de points **"non classifiés"**
  - Faire la différence de 2018 sur 2015
  - Relever le numéro des tuiles dont ce pourcentage est supérieur à **30%**
 
## 📚 Recherches effectuées sur le traitement des données LiDAR en Python  

Utilisation de la bibliothèque **laspy** :  
- 📌 [Documentation principale](https://laspy.readthedocs.io/en/latest/)  
- 📌 [Guide d'installation](https://laspy.readthedocs.io/en/latest/installation.html)  


➡ Question posée à Rodolphe pour la méthodologie du code.

## Réponse de Rodolphe

	resulats2015 = []
		for t2015 in tuiles2015:
		resultats2015.append(calculsStats(t2015))

# Semaine du 03 mars: 

## Reprise du Code pour le Calcul Automatique des Différences de Classification  

![image](https://github.com/user-attachments/assets/68b66866-8bb6-466e-96ed-108882314d6d)  

### 🚀 Progrès et ajustements  

Pour effectuer les calculs sur toutes les tuiles, j’ai envisagé de créer un Google Drive afin d’y stocker toutes les tuiles LiDAR. Les fichiers étant trop volumineux, cette solution s’est avérée inadaptée.  

#### 🔧 Solution adoptée  
✅ Installation d'**Anaconda** pour travailler sous **Jupyter Notebook**.  
✅ Ajout des **149 premières tuiles** (de **296** à **279**).  
⏳ **Prochaine étape** : Reprendre à **280** pour compléter l’ensemble des données.  

#### 💻 Développement du Code  
🔹 Finalement, le code a été repris et exécuté sous **Spyder**.  
🔹 Création d’un script permettant de **calculer automatiquement le pourcentage de points classifiés** selon une classification donnée **"x"**.  
🔹 Les résultats sont intégrés dans un **DataFrame**, comprenant :  
   - Une **colonne indiquant le nom de la tuile** traitée.  
   - Une **colonne contenant le résultat du calcul**.  
Reprise du Code pour le calcul automatique de la différence du pourcentage de point selon leur classification


### 1er Prototype fonctionnel

	resultats2018 = []
	tuiles2018 = []

	def pourcentage2018(dossier):

    		for f in os.listdir(dossier):
        
        		if f.endswith('.las'):
            
            			chemin_fichier = os.path.join(dossier, f)
            
            
            		with lp.open(chemin_fichier) as g:
                
                		t2018 = g.read()
               
                		num_points = len(t2018)
                
                
                		num_points_classcode = len(t2018[t2018.classification == 5])
               
                		pourcentage_points_classecode = (num_points_classcode/num_points) *100
                
                		numero_tuile = f[:8]
               
                		resultats2018.append(pourcentage_points_classecode)
                
                		tuiles2018.append(numero_tuile)
                
                
                
    	return resultats2018, tuiles2018

	dossier = r"D:\UNIVERSITE\UQAM\Projet\DISQUE_5_DANS_8\LIDAR\TEST"
	resultats =  pourcentage2018(dossier)

	for pourcentage_points_classecode in resultats2018:
    		print(f"{pourcentage_points_classecode}% de points non classifiés")
	for numero_tuile in tuiles2018:
    		print(f"Tuile {numero_tuile}")

![image](https://github.com/user-attachments/assets/b9dde783-7bf5-4188-90fe-aa4898c9d4ce)

# Semaine du 10 mars :
### 2ème prototype fonctionnel

Avancé du code, Code terminé avec un code pour calculer les pourcentage des points classifiés en "x" code de classe pour les tuiles 2018 :



	import lazrs
	import pandas as pd
	import laspy as lp
	import os


	# Calcul du pourcentage de points classifiés en "x" code de classe pour l'année 2018:
    
	resultats2018 = [] # Liste vide contenant les réultats du calcule du pourcentage de points classifié selon "x" classecode

	tuiles2018 = [] # Liste vide contenant le nom de la tuile qui est calculé

	def pourcentage2018(dossier): # Fonction qui calcule
    
    		for f in os.listdir(dossier):
            
        		if f.endswith('.las'): # S'assurer que seuls les fichier .las sont sélectionnés
                
            		chemin_fichier = os.path.join(dossier, f)
                
            			with lp.open(chemin_fichier) as g: # Ouvrir le 
                    
               			t2018 = g.read()
                   
                		num_points = len(t2018) # Nombre de points dans la tuile
                
                		if num_points > 0: # Filtre pour ne pas diviser par 0 mais scénario impossible ici.
                    
                    			num_points_classcode = len(t2018[t2018.classification == 1]) # Nombre de points classifié selon le code de classe choisi
                   
                    			pourcentage_points_classecode = (num_points_classcode/num_points) *100 # Calcule du pourcentage
                    
                		else:
                    			pourcentage_points_classecode = 0.0
                
                		numero_tuile = f[:8] # Chercher le nom de la tuile (les 9 premiers caractères du fichier)
                   
                		resultats2018.append(pourcentage_points_classecode) # Ajouter le pourcentage à la liste resultats2018
                    
                		tuiles2018.append(numero_tuile) # Ajouter le nom de la tuile à la liste tuiles2018
                
    		df_resultats2018 = pd.DataFrame(
        	{'Tuile2018': tuiles2018,
         	'Pourcentage de points classifiés 2018 (Classe 1)': resultats2018
    		}) # Mettre le résultat des deux listes dans un dataframe
                    
                    
                    
    		return df_resultats2018

	dossier = r"D:\UNIVERSITE\UQAM\Projet\DISQUE_5_DANS_8\LIDAR_2018\LAS_classifiees\266-279"
	df_resultats_2018 =  pourcentage2018(dossier)


Un second pour les tuiles 2015 : 

	# Calcul du pourcentage de points classifié en "x" code de classe pour l'année 2015:
    
	resultats2015 = [] # Liste vide contenant les réultats du calcule du pourcentage de points classifié selon "x" classecode

	tuiles2015 = [] # Liste vide contenant le nom de la tuile qui est calculé

	def pourcentage2015(dossier): # Fonction qui calcule
    
   		for f in os.listdir(dossier):
            
        		if f.endswith('.las'): # S'assurer que seuls les fichier .las sont sélectionnés
                
            			chemin_fichier = os.path.join(dossier, f)
                
            			with lp.open(chemin_fichier) as g: # Ouvrir le 
                    
                		t2015 = g.read()
                   
                		num_points = len(t2015) # Nombre de points dans la tuile
                
                		if num_points > 0: # Filtre pour ne pas diviser par 0 mais scénario impossible ici.
                    
                    			num_points_classcode = len(t2015[t2015.classification == 1]) # Nombre de points classifié selon le code de classe choisi
                   
                    			pourcentage_points_classecode = (num_points_classcode/num_points) *100 # Calcule du pourcentage
                    
                		else:
                    			pourcentage_points_classecode = 0.0
                
                		numero_tuile = f[:8] # Chercher le nom de la tuile (les 9 premiers caractères du fichier)
                   
                		resultats2015.append(pourcentage_points_classecode) # Ajouter le pourcentage à la liste resultats2018
                    
                		tuiles2015.append(numero_tuile) # Ajouter le nom de la tuile à la liste tuiles2018
                
    		df_resultats2015 = pd.DataFrame(
        	{'Tuile2015': tuiles2015,
         	'Pourcentage de points classifiés 2015 (Classe 1)': resultats2015
    		}) # Mettre le résultat des deux listes dans un dataframe
                    
                    
                    
    		return df_resultats2015

	dossier = r"D:\UNIVERSITE\UQAM\Contrat\Comparaison_2015_2018\LiDAR_2015\LAS2015_classifiees_266-279"
	df_resultats_2015 =  pourcentage2015(dossier)


# 2ème échantillon de test.

## 🛠️ Test du Code sur un Échantillon Réduit  

Pour tester ce code, j’ai effectué un test sur un **échantillon réduit** comprenant **5 tuiles** de 2015 et **5 tuiles** de 2018.  

### 🎯 Objectif du Test  
L’objectif était simplement de **vérifier le bon fonctionnement du code**, sans chercher à comparer directement les valeurs entre 2015 et 2018.  

### ⚠️ Différences dans l’échantillon  
🚨 **Les tuiles sélectionnées ne sont pas les mêmes pour 2015 et 2018**, car je n'avais pas prévu de soustraire les résultats entre les deux années.  
🔍 Le test visait uniquement à s’assurer que les **résultats étaient cohérents** :  
- **Le calcul du pourcentage était correct**.  
- **Chaque tuile était bien associée à son résultat dans le DataFrame*


# 3ème échantillon de test

## 🔄 Fusion des DataFrames pour l'Analyse des Différences  

Les codes pour le calcul des pourcentages étant **fonctionnels**, j’ai ajouté une **section fusionnant les deux DataFrames** en un seul.  

### 🎯 Objectif  
L’objectif est de **regrouper toutes les données** dans un **unique DataFrame** afin de faciliter l’analyse des différences entre 2015 et 2018.  

### 🔧 Méthode  

**Fusion des DataFrames** avec la méthode **.merge**



	# Fusion des 2 DataFrame et soustraction des résultats

	df_comparaison = df_resultats_2018.merge(df_resultats_2015[["Tuile2015", "Pourcentage de points classifiés 2015 (Classe 1)" ]], left_on="Tuile2018", right_on="Tuile2015", how="left")
	df_comparaison["Différence"] = df_comparaison["Pourcentage de points classifiés 2018 (Classe 1)"] - df_comparaison["Pourcentage de points classifiés 2015 (Classe 1)"]

	print(df_comparaison)
 

### 🧪 Test de Fusion avec Données Non Concordantes  

Apres quoi j'ai réalisé le premier test complet, sur un échantillon réduit : 


| Tuile      | 2015     | 2018     |
|------------|---------|---------|
| 295-5029   | ✅       | ❌       |
| 295-5030   | ✅       | ✅       |
| 295-5031   | ✅       | ✅       |
| 295-5032   | ✅       | ✅       |
| 295-5033   | ✅       | ✅       |
| 295-5034   | ❌       | ✅       |



J’ai **délibérément choisi** des données **non parfaitement concordantes** entre **2015 et 2018** afin d’observer le comportement du code lors de la fusion des deux DataFrames.  

### 🎯 Objectif  
Tester la gestion des **valeurs manquantes** et vérifier si la fusion des DataFrames entraîne des erreurs ou un décalage des lignes.  

### ✅ Résultats  
- **Résultat positif** :  
  - Lorsque le code ne peut pas effectuer la soustraction entre 2018 et 2015 (car une tuile est absente d’un des jeux de données), le **DataFrame insère un "NaN"**.  
  - **Aucun décalage** observé dans les lignes du DataFrame.  

🔍 **Conclusion** : Le code gère correctement les données non concordantes et maintient l’intégrité des résultats.  


# 4ème échantillon

## 📊 Test de Grande Ampleur sur le premier fichiers de tuiles (266-279)  

### 🚀 Résultats du Test  
- **Succès pour 2015** ✅  
- **Échec pour 2018** ❌ : Un fichier semble être corrompu.  

### 🔍 Détection du Fichier Corrompu  
Pour identifier le fichier problématique, j’ai exécuté le code suivant :

	dossier = r"D:\UNIVERSITE\UQAM\Projet\DISQUE_5_DANS_8\LIDAR_2018\LAS_classifiees\266-279"

	for f in os.listdir(dossier):
    		if f.endswith('.las'):
        	chemin_fichier = os.path.join(dossier, f)
       		 with open(chemin_fichier, "rb") as fichier:
            		signature = fichier.read(4)
        	print(f"{f} → Signature : {signature}")

Le script permet de relever la **signature des fichiers**.  
🔹 Un fichier `.LAS` doit avoir une **signature = `b'LASF'`**.  
🔹 Une tuile **(279-5031)** était corrompue.  
🚀 **Action** : Je l’ai retirée du dossier avant de relancer le code.  

✅ **Succès** : Le script fonctionne correctement après cette correction.  

---

## 📂 Export des Résultats et Visualisation  

Le code suivant permet de **transposer les résultats dans un fichier CSV**.  
📌 **Procédure** :  
1. Ouverture du fichier dans **Excel**.  
2. Réenregistrement au format **CSV**.  
3. Import dans **ArcGIS**.
4. **Jointure avec le fichier shapefile des tuiles LiDAR 2015** pour visualiser les résultats.  

![image](https://github.com/user-attachments/assets/9f175a29-fffb-4374-b055-a16a2489d0a3)

🔎 **Observation** :  
➡️ **Augmentation du pourcentage de points non classifiés** pour **les tuiles de l’extrême est de l’île**.  

---

## 📅 Semaine du 17 mars  

### 📌 Analyse des données "non-classifiées" (2015 vs 2018)  

🔹 Exécution du script pour **toutes les tuiles** classifiées en **"non-classifiées"** en 2015 et 2018.  
🔹 Fusion des **5 CSV par année (2015 et 2018)** dans **ArcGIS** (`Comparaison_LiDAR_Classe1`).  
🔹 **Jointure** entre le fichier fusionné et la couche **shapefile des tuiles LiDAR**.  

### 📊 Résultats de l'analyse  

![image](https://github.com/user-attachments/assets/1ba3e2fd-4767-4def-af80-c4937dd12f0b)

🔸 **Légende** :  
✔️ **Vert foncé** → Forte diminution du pourcentage de points "non-classifiés" entre 2015 et 2018.  
⚠️ **Orange / Rouge** → Augmentation de plus de **15% à 30%** du pourcentage de points "non-classifiés" entre 2018 et 2015.  

📌 **Tendance générale** :  
➡️ **60% des tuiles** ont un **taux plus élevé de points "non-classifiés" en 2018** qu'en 2015.  

---

### 🌿 Analyse des données "Végétation haute" (2015 vs 2018)  

🔹 **Même script**, seule la classification change :  

	num_points_classcode = len(t2015[t2015.classification == 5])  # Nombre de points classifiés selon le code choisi


📌 **Procédure identique** :  
1. Ouverture du fichier dans **Excel**.  
2. Réenregistrement au format **CSV**.  
3. Import dans **ArcGIS**.
4. **Jointure avec le fichier shapefile des tuiles LiDAR 2015** pour visualiser les résultats.

![image](https://github.com/user-attachments/assets/ca46a135-a92c-4225-b6b6-ea6b7f46a9bd)

🔎**Observation étonnante** :
➡️ Pour une grande majorité de l'île, le nombre de points classifiés en "végétation haute" a augmenté d’au moins 10% entre 2015 et 2018. Ce résultat vient contredire ceux obtenus lors de notre premier échantillon test.

# 📌 Résumé des résultats

- **60% des tuiles** ont un pourcentage plus élevé de points **"non-classifiés" en 2018** qu'en 2015.
- **9.7% des tuiles** montrent une augmentation du pourcentage de points classifiés en **"végétation haute" en 2018** par rapport à 2015.


# Suite du travail

- Effectuer le code pour les points classifiés en **"Végétation-moyenne"** et **"végétation-basse"**
- Trouver une méthode pour assigner une classification aux valeurs non-classifiées dans les tuiles ou leur poucentage dépasse une valeur seuil **"x"**
