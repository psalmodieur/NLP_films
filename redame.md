# Brief analyse de commentaire de film

## Le projet

Ce brief à pour objectif d'analyser les commentaires des films Inception et Sonic the hedgehog sur Allociné pour pouvoir faire de l'analyse de sentiment et prédire si un commentaire est positif ou négatif.

## Le fonctionnement du projet

Nous avons commencé par faire un web scrapping sur les pages des deux films afin d'en récupérer les commentaires et les notes attribués par les utilisateurs. Un commentaire lié à une notes inférieur à 3 est jugé comme négatif. Une fois les commentaire récuppérés nous les avons nettoyer de leurs différent mots inutiles (les stop words) et nous les avons vectorisé (c'est à dire nous avons fait une matrice avec l'ensembles des mots contenus dans les commentaires et si le mot est présent dans un commentaire *x* on associe un 1 à cet emplacement et un 0 sinon).

Une fois les commentaires vectorisé nous avons appliqué une régression logistique pour créer notre modèle d'analyse de sentiment.

Ce modèle nous permet par la suite de faire des prédiction sur un commentaire saisie par l'utilisateur.

## Les limites du projet

Pour l'instant le modèle que nous avons n'est pas bon, il ne permet pas de faire de prédiction juste et renvois systématiquement qu'un commentaire est positif. Ceci est du à un manque de donnée de commentaire négatif, la majorité des données venant du film inceptions qui a des critiques très positives (on peut le remarquer sur la matrice de confusion du modèle). En effectuant de la data augmentatio  sur les commentaires négatifs ce problème devrait disparaitre.