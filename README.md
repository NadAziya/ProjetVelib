# Application de suivi des stations Vélib' en temps réel à Paris

## Description

Cette application permet de récupérer les données en temps réel sur les stations Vélib' à Paris, de les stocker dans une base de données MongoDB et de les visualiser sur une carte interactive générée avec Folium. Elle est utile pour suivre la disponibilité des vélos mécaniques et électriques à travers la ville.

## Fonctionnalités

- **Récupération des données en temps réel :** Les informations des stations Vélib' sont obtenues via l'API d'OpenData Paris.
- **Stockage des données :** Les données sont stockées dans MongoDB pour une gestion efficace et des mises à jour régulières.
- **Visualisation sur une carte interactive :** Une carte générée avec Folium affiche les stations avec des marqueurs indiquant le nombre de vélos disponibles.

## Pré-requis

- **Python 3.x**
- **Bibliothèques Python :**
  - `requests` pour les requêtes HTTP.
  - `pymongo` pour interagir avec MongoDB.
  - `folium` pour créer la carte interactive.
  - `webbrowser` et `os` pour afficher la carte générée.
  - `time` pour gérer les intervalles de mise à jour.
- **MongoDB** installé localement ou sur un serveur distant.
- **Connexion Internet** pour accéder à l'API d'OpenData Paris.

## Installation

1. Clonez ce dépôt ou téléchargez les fichiers.
2. Installez les dépendances Python :
   ```bash
   pip install requests pymongo folium
   ```
3. Assurez-vous que MongoDB est en cours d'exécution et accessible via `mongodb://localhost:27017/` (modifiable dans le code si nécessaire).

## Fichiers

- `insertMongo.py` : Script pour récupérer et insérer les données dans MongoDB.
- `mapVelib.py` : Script pour créer une carte interactive avec les données récupérées.
- `tp3.py` : Script complet pour la mise à jour automatique des données en temps réel et la génération dynamique de la carte.
- `map_paris_velib_realtime.html` : Carte générée affichant les stations et leur disponibilité (mise à jour automatiquement).

## Utilisation

1. **Lancer l'application :**
   Exécutez `tp3.py` pour démarrer le processus de récupération des données et de mise à jour en temps réel :
   ```bash
   python tp3.py
   ```

2. **Visualisation :**
   Une carte interactive s'ouvre automatiquement dans votre navigateur, indiquant la localisation des stations et le nombre de vélos disponibles.

3. **Intervalles de mise à jour :**
   Les données sont mises à jour toutes les 60 secondes par défaut. Ce paramètre peut être modifié dans le fichier `tp3.py`.

## Notes importantes

- La collection MongoDB est effacée avant chaque nouvelle insertion pour garantir que seules les données les plus récentes sont disponibles.
- La carte est sauvegardée en tant que fichier HTML (`map_paris_velib_realtime.html`) à chaque mise à jour.

## Exemple de sortie

Sur la carte, chaque station est représentée par un marqueur. Lorsque vous cliquez sur un marqueur, une info-bulle affiche :

- Le nom de la station.
- Le nombre de vélos disponibles.


