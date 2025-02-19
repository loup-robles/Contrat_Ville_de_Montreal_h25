# Comparaison LiDAR 2015 et 2018

## Contexte
La classification des données LiDAR de 2015 et 2018 a été faite par 2 algorithmes différents, menant à des disparités dans les données.

## Objectif
Comparer les données sur plusieurs tuiles pour identifier les différences.

## Données
- **LiDAR 2015** : disponible sur le portail des données ouvertes de la Ville de Montréal.
- **LiDAR 2018** : données sur disque physique, transmises par la Ville de Montréal lors du contrat pour la mise à jour de la carte de vulnérabilité face aux pluies abondantes de l'été 2024.

## Méthodologie
1. Télécharger une sélection de 5-6 tuiles LiDAR 2015 sur le portail des données ouvertes de la Ville de Montréal.
2. Convertir les fichiers `.LAZ` en `.LAS` :
    - Sur ArcGIS avec "Convertir des fichiers LAS", aucune compression, toutes les options LAS décochées, fichier LAS sans référence spatiale avec 32188 ou 2950 (4140 ne fonctionne pas).
3. Calculer des statistiques sur chaque tuile.
    - Sur ArcGIS avec "Statistiques d'un jeu de données LAS"
4. Comparer les statistiques entre 2015 et 2018 pour chaque tuiles

## Tuiles sélectionnées
- 299-5042 (sud-ouest du Parc La Fontaine) (faite)
- 297-5043 (ouest du parc Laurier) (faite)
- 297-5040 (Mont-Royal) (faite)
- 300-5046 (Parc Maisonneuve, stade olympique) (faite)
- 292-5048 (Parc-nature de l'Île-de-la-Visitation) (faite)
- 284-5040 (Parc-nature du Bois-de-Liesse) (faite)

## Comparaison

### 299-5042
| Classification     | Nb points 2015 | Nb points 2018 | Pourcentage 2015 | Pourcentage 2018 | Différence 2018-2015 |
|-------------------|----------------|----------------|------------------|------------------|----------------------|
| Tous              | 18.3 M         | 29.1 M         | 100 %            | 100 %            | x                    |
| Non classifié     | 4.6 M          | 6.4 M          | 25.37 %          | 22.14 %          | <mark>-3.23 %        |
| Végétation haute  | 2.3 M          | 12.6 M         | 12.34 %          | 43.2 %           | <mark>+30.86 %       |
| Bâtiments         | 5.4 M          | 6.8 M          | 29.28 %          | 22.27 %          | -7.01 %              |

### 299-5043
| Classification     | Nb points 2015 | Nb points 2018 | Pourcentage 2015 | Pourcentage 2018 | Différence 2018-2015 |
|-------------------|----------------|----------------|------------------|------------------|----------------------|
| Tous              | 21.1 M         | 24.2 M         | 100 %            | 100 %            | x                    |
| Non classifié     | 6.9 M          | 7.6 M          | 32.93 %          | 31.22 %          | <mark> -1.71 %       |
| Végétation haute  | 1.3 M          | 6.0 M          | 5.92 %           | 24.71 %          | <mark> +18.79 %      |
| Bâtiments         | 5.7 M          | 6.3 M          | 27.07 %          | 25.92 %          | -1.15 %              |

### 299-5040
| Classification     | Nb points 2015 | Nb points 2018 | Pourcentage 2015 | Pourcentage 2018 | Différence 2018-2015 |
|-------------------|----------------|----------------|------------------|------------------|----------------------|
| Tous              | 16.8 M         | 26.0 M         | 100 %            | 100 %            | x                    |
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
