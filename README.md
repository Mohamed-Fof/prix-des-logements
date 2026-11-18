# Analyse des déterminants du prix des logements

Ce dépôt présente l'évolution d'un même projet en deux étapes complémentaires.

## Version 1 — Analyse économétrique avec Gretl

Le rapport et la présentation correspondent au travail réalisé dans le cadre de la licence. Cette version étudie les déterminants du prix des logements avec plusieurs modèles MCO :

- modèle niveau-niveau ;
- modèle log-niveau ;
- modèle log-niveau avec interactions ;
- tests de normalité et d'hétéroscédasticité, notamment White et Breusch-Pagan.

Le rapport retient le modèle log-niveau pour son compromis entre ajustement et interprétabilité.

## Version 2 — Extension Machine Learning avec Google Colab

Le notebook `Regression_lineaire.ipynb` constitue une amélioration réalisée après le travail sous Gretl. Il reprend la même base `Housing`, conserve une régression linéaire comme référence et ajoute :

- une préparation des variables ;
- une séparation entraînement/test ;
- une validation croisée ;
- un modèle `RandomForestRegressor` ;
- une comparaison avec les métriques RMSE et R².

Cette extension ne remplace donc pas les résultats économétriques du rapport : elle les complète par une évaluation orientée prédiction. Les différences de modèles et de résultats entre les documents sont attendues, car ils correspondent à deux étapes du projet.

## Résultats de l'extension Machine Learning

Sur le découpage utilisé dans le notebook :

| Modèle | RMSE | R² test |
|---|---:|---:|
| Régression linéaire | 16 016,40 $ | 0,6160 |
| Random Forest | 17 598,83 $ | 0,5364 |

La régression linéaire obtient ici le meilleur résultat prédictif sur l'échantillon de test. Cette conclusion est spécifique au protocole et aux données utilisés dans le notebook ; elle ne remet pas en cause le choix économétrique du modèle log-niveau dans le rapport.

## Reproduction

Le notebook peut être ouvert dans Google Colab depuis son badge. Il télécharge la base depuis ce dépôt, dans `Data/housing.csv`.
