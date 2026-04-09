# Régression de Poisson : Prédiction de l'Ozone

Ce projet vise à modéliser le niveau d'ozone à New York en utilisant différentes approches de régression pour données de comptage (Poisson, Quasi-Poisson et Binomiale Négative). L'étude s'appuie sur le jeu de données classique `airquality`.

## Description

Le projet analyse l'influence de facteurs environnementaux tels que le rayonnement solaire (`Solar.R`), le vent (`Wind`) et la température (`Temp`) sur la concentration d'ozone. Une attention particulière est portée à la détection et au traitement de la **surdispersion**, un phénomène courant dans les modèles de Poisson où la variance est supérieure à la moyenne.

### Points clés de l'analyse :
- **Analyse exploratoire** des données `airquality`.
- **Modélisation de Poisson** initiale et calcul des ratios de taux d'incidence (IRR).
- **Tests de validation** : Vérification de la distribution et test de surdispersion (Z-Score de Hilbe).
- **Modèles alternatifs** : Implémentation de modèles Quasi-Poisson et Binomial Négatif pour corriger la surdispersion.

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

Vous pouvez les installer en exécutant :
```r
install.packages(c("ggplot2", "gridExtra", "caTools", "MASS"))
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

---
Projet réalisé en groupe dans le cadre d'une étude sur les modèles linéaires généralisés (GLM).

Membres du groupe :
- DESSOU Lysias
- HOMEVO Kafui

