# UrbanTrafficDetection – Big Data Pipeline
## Project Overview
Le projet vise à prévoir le volume de trafic urbain à partir de données historiques, météorologiques et temporelles en utilisant un pipeline Big Data complet basé sur Apache Spark, avec intégration dans Zeppelin et stockage des résultats dans Hive.

L’objectif est de construire un workflow scalable, distribué et reproductible, couvrant l’ingestion des données, le prétraitement, le machine learning distribué, la visualisation et le stockage des résultats.

## Pipeline Big Data
### 1. Architecture du Projet
<img width="1123" height="544" alt="Image" src="https://github.com/user-attachments/assets/d178d918-48e6-4ee6-94f7-577278a68b43" />
### 2. Installer tous les outils nécessaires
L’ensemble des outils nécessaires au pipeline Big Data ont été installé et configuré à l’aide de **Docker** et d’un fichier **`docker-compose.yaml`**, ce qui permet de déployer un environnement homogène, reproductible et facile à maintenir.

Les composants utilisés sont :

- **Apache Spark** : moteur de calcul distribué pour le traitement des données massives.
- **PySpark** : interface Python pour l’utilisation de Spark MLlib.
- **Apache Zeppelin** : notebook interactif pour l’exécution et la visualisation des traitements Spark.
- **HDFS (Hadoop Distributed File System)** : système de fichiers distribué pour le stockage et l’accès aux données.
- **Apache Hive** : data warehouse permettant le stockage des résultats et l’exécution de requêtes SQL sur les données distribuées.

Cette approche basée sur Docker garantit une installation rapide, portable et cohérente de l’ensemble de l’environnement Big Data, facilitant ainsi le développement et l’expérimentation du pipeline.

### 3. Choix du format de données – Parquet

Le format **Parquet** a été choisi pour le stockage des données traitées, en raison de ses avantages pour les environnements Big Data :

- **Stockage en colonnes** : permet une lecture rapide et ciblée des colonnes nécessaires.
- **Compression efficace** : réduit l’espace disque utilisé.
- **Optimisation pour Apache Spark** : améliore les performances des traitements distribués.

Le fichier final est stocké sous le format : **`traffic_volume_cleaned_encoded.parquet`**

### 4. Dataset utilisé – Metro Interstate Traffic Volume 

Le dataset *Metro Interstate Traffic Volume* contient des données de trafic routier urbain, incluant le volume de circulation, les conditions météorologiques et des informations temporelles. Il est utilisé pour analyser et détecter les patterns de congestion du trafic urbain.

#### * Structure des données :

Les données de ce jeu de données ont été collectées par le **Minnesota Department of Transportation (MnDOT)** entre **2012 et 2018**. Les attributs clés du jeu de données sont :

- **holiday** : variable catégorielle indiquant les jours fériés nationaux ou régionaux.
- **temp** : température moyenne (en kelvin).
- **rain_1h** : quantité de pluie (en mm) sur une heure.
- **snow_1h** : quantité de neige (en mm) sur une heure.
- **clouds_all** : pourcentage de couverture nuageuse.
- **weather_main** : description courte des conditions météorologiques.
- **weather_description** : description détaillée des conditions météorologiques.
- **date_time** : date et heure de la mesure (heure locale CST).
- **traffic_volume** : volume horaire du trafic routier.




