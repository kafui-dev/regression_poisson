# Régression de Poisson : Prédiction de l'Ozone

Ce projet vise à modéliser le niveau d'ozone à New York en utilisant différentes approches de régression pour données de comptage (Poisson, Quasi-Poisson et Binomiale Négative). L'étude s'appuie sur le jeu de données classique `airquality`.

## Description

Le projet analyse l'influence de facteurs environnementaux tels que le rayonnement solaire (`Solar.R`), le vent (`Wind`) et la température (`Temp`) sur la concentration d'ozone. Une attention particulière est portée à la détection et au traitement de la **surdispersion**, ainsi qu'à l'amélioration des modèles via des **régressions pondérées**.

### Points clés de l'analyse :
- **Analyse exploratoire** des données `airquality`.
- **Modélisation de Poisson** initiale et calcul des ratios de taux d'incidence (IRR).
- **Tests de validation** : Vérification de la distribution, test de surdispersion (Z-Score de Hilbe), test de Hosmer-Lemeshow et analyse des résidus de Pearson.
- **Modèles alternatifs et pondérés** : Implémentation de modèles Quasi-Poisson et Binomial Négatif, ainsi que leurs versions pondérées pour corriger la surdispersion et améliorer la précision.
- **Comparaison de performance** : Utilisation de métriques multicritères (AIC, BIC, R², RMSE) pour identifier le meilleur modèle.

## Structure du projet

- `regPoisson_ozone.qmd` : Le notebook Quarto contenant l'intégralité du code R, les visualisations et les interprétations statistiques.
- `regPoisson_ozone.html` : Le rapport généré au format HTML.
- `libraries.R` : Script listant les bibliothèques R nécessaires.
- `renv/` & `renv.lock` : Fichiers de gestion de l'environnement R pour assurer la reproductibilité.
- `regression_poisson.Rproj` : Fichier de projet RStudio.

## Installation

### Prérequis
Assurez-vous d'avoir [R](https://www.r-project.org/) installé sur votre machine. L'utilisation de [RStudio](https://posit.co/download/rstudio-desktop/) est recommandée pour ouvrir le projet.

### Dépendances
Les packages suivants sont requis :
- `ggplot2` (visualisation)
- `gridExtra` (mise en page des graphiques)
- `caTools` (séparation des données train/test)
- `MASS` (modèle binomial négatif)
- `ResourceSelection` (test de Hosmer-Lemeshow)
- `performance` (comparaison des modèles)

Vous pouvez les installer en exécutant :
```r
install.packages(c("ggplot2", "gridExtra", "caTools", "MASS", "ResourceSelection", "performance"))
```

Si vous utilisez `renv`, vous pouvez restaurer l'environnement avec :
```r
renv::restore()
```

## Utilisation

1. Ouvrez le fichier `regression_poisson.Rproj` dans RStudio.
2. Ouvrez le fichier `regPoisson_ozone.qmd`.
3. Cliquez sur le bouton **Render** (ou `Ctrl+Shift+K`) pour générer le rapport HTML et exécuter les analyses.

## Données
Le projet utilise le dataset `airquality` intégré à R, qui contient des mesures quotidiennes de la qualité de l'air à New York de mai à septembre 1973.

## Résultats
L'analyse montre que le **modèle Binomial Négatif** (particulièrement sa version pondérée) est le plus performant pour prédire le niveau d'ozone, en raison de sa capacité à absorber la surdispersion observée dans les données initiales.

---
Projet réalisé en groupe dans le cadre d'une étude sur les modèles linéaires généralisés (GLM).

Membres du groupe :
- DESSOU Lysias
- HOMEVO Kafui

