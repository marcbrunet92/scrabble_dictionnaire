# Modèles de l'app Scrabble Solver

`tile_classifier_v1.tflite` : classifieur de cases (A–Z + vide) utilisé par le scanner de
plateau. L'app le retélécharge quand il change ici (une fois par lancement, à l'ouverture
du scanner), sans mise à jour de l'app.

Pour publier un nouveau modèle : remplacer le fichier, commit, push sur `master`.

« v1 » = entrée 64×64 en niveaux de gris, 27 sorties (A–Z puis vide). Un modèle qui change
l'entrée, le découpage des cases ou les classes doit être publié sous un autre nom
(`tile_classifier_v2.tflite`) avec une nouvelle version de l'app : les apps déjà
installées vérifient le modèle et ignorent un modèle incompatible, mais garder la v1 leur
permet de continuer à recevoir des améliorations.

Entraînement : `tools/tile_classifier` dans le dépôt de l'app.
