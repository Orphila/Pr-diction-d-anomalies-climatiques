# Climate forecast challenge

Ce projet a été réalisé dans le cadre d'un concours de machine learning organisé sur le site de l'ENS. Vous pouvez retrouver le lien du challenge et des détails sur l'enjeu, l'objectif, les fichiers fournis etc au lien suivant: https://challengedata.ens.fr/challenges/80.

Pour résumer le tout, on dispose des donées concernant des températures sur l'ensemble du globe terrestre sur 10 ans, et le but est d'utiliser un algorithme de régression afin de prévoir l'évolution de ces données climatiques à partir des températures des années précedentes, pour anticiper l'apparition naturelles d'anomalies. J'ai intégré au rapport le notebook ainsi que les fichiers fournis.

Il s'agit de mon tout premier projet de machine learning (hors projets d'entraînement type titanic etc).


# Partie 1 : traitement du dataset

On sélectionne le fihier csv X-test. La séparation des données pour l'entrainenemnt et le test du modèle est déjà faite.

Il y a un travail de features engineering important vu le format des données : Les températures sur les années qu'on utilise pour la prédiction sont réparties sur un modèle séparant le globe en 3072 points, et la prédiction doit le faire sur 192 points. Le format voulu est donc pour chacun des 22 modèles fournit, ont ait pour chacun des 192 points (donc les lignes ) des features correspondant aux 10 années de mesure (les colonnes).

# Partie 2 : prédiction avec XGBoost

Pour réaliser cette régression, on choisit d'utiliser l'algorithme XGBoost.

XGBoost est un algorithme de boosting de gradient (Gradient Boosting) pour les modèles de régression. Il utilise une technique appelée "boosting" pour combiner plusieurs modèles de décision faibles pour créer un modèle plus robuste. Les modèles de décision faibles sont générés en utilisant l'algorithme de gradient boosting à partir des arbres de décision, d'où le nom "XGBoost". Il est souvent utilisé pour les tâches de régression car il peut gérer efficacement les variables catégoriques et numériques et il est également rapide à entraîner.

Il ne reste plus qu'a entraîner le modèle et tester avec différents paramètres.

# Partie 3 : résultats et amélioration possibles

Pour estimer la validité des prédictions, nous proposons d'utiliser deux mesures différentes : le coefficient de détermination (R2), qui montre la compétence de la prédiction moyenne, et la fiabilité, qui mesure la précision de l'écart dans la prédiction. La métrique caractérise ainsi la précision de l'utilisation de la moyenne et la cohérence de l'erreur prédite avec l'erreur effective.

Ici j'ai obtenu un score de -1,9, ce qui semblait correct mais il semblerait que beaucoup ait mieux fait durant ce challenge. Il est donc possible d'obtenir un meilleur résultat, surement en utilisant d'autres algorithmes, comme possiblement un SVR.

Pour conclure, il est bien possible de prévoir avec une certaine précision des données climatiques, mais pour être tout à fait objectif, je ne suis pas sur que les données fournies soient celles qui nous permettent d'avoir le meilleur modèle. Je pense qu'avoir des données sur des régions plus précises permettrait d'obtenir des résultats plus précis également.

Au niveau personnel, c'était un challenge très intéressant, qui m'a permis de commencer à me former sur des projets concrets de machine learning, et pour ça j'en conclue que c'est une réussite. Mes prochains projets seront plus élaborés, et j'espère obtenir de meilleurs résultats.
