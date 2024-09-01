# Analyse des Sentiments avec un Modèle RNN

## Description
Ce projet utilise un modèle de réseau de neurones récurrents (RNN) pour effectuer une analyse des sentiments sur des avis de consommateurs. Les avis sont classés en deux catégories : positifs et négatifs. Le modèle est entraîné sur un ensemble de données d'avis, en utilisant une combinaison d'embedding, de SimpleRNN, et de couches denses avec régularisation.

## Données
Les données utilisées pour ce projet proviennent d'une feuille Google Sheets accessible via un lien public. Le dataset contient 50 000 avis, chacun ayant un texte d'avis (`review`) et une étiquette de sentiment (`sentiment`), où les sentiments sont mappés à `0` (négatif) et `1` (positif).

## Modèle
Le modèle RNN est constitué des éléments suivants :
- Une couche d'embedding pour représenter les mots.
- Une couche RNN simple avec 64 unités et une régularisation L2.
- Deux couches denses pour la classification avec régularisation L2 et Dropout pour éviter le surapprentissage.
- Une couche de sortie avec une activation sigmoïde pour la classification binaire.

Le modèle est entraîné avec l'optimiseur Adam et la fonction de perte `binary_crossentropy`. Un callback d'arrêt anticipé est utilisé pour éviter le surentraînement.

## Prérequis
Assurez-vous d'avoir Python installé, ainsi que les bibliothèques listées dans le fichier `requirements.txt` :

```bash
pip install -r requirements.txt
