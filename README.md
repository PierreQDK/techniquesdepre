
# Prévision du CAC 40 sur l’année 2019

Projet réalisé dans le cadre du Master 1 Économétrie et Statistiques – parcours Économétrie Appliquée (IAE Nantes).

## 📌 Objectif

Ce projet a pour objectif de prévoir l’évolution mensuelle de l’indice boursier CAC 40 sur l’année 2019 à partir de données historiques couvrant la période 2000-2018.

L’objectif est d’évaluer la performance prédictive de plusieurs modèles linéaires dynamiques en termes d’erreur quadratique moyenne (MSE), de R² hors échantillon (R²_OOS), et via le test de Diebold-Mariano :

- ARIMA
- Holt-Winters (LED)
- ADAM ETS
- ADAM ETS + ARIMA (modèle hybride)
- SSARIMA

## 📁 Données

Les données proviennent de Yahoo Finance et couvrent l’évolution mensuelle de la clôture du CAC 40 :
- Données d’apprentissage : Janvier 2000 – Décembre 2018
- Données de test : Janvier 2019 – Décembre 2019

Les données sont récupérées à l’aide de `tidyquant::tq_get`.

## 🛠 Méthodologie

- Détection de points atypiques (X13, TSO)
- Transformation logarithmique
- Tests de stationnarité (ADF, KPSS, PP)
- Différenciation de la série
- Estimation des modèles linéaires dynamiques
- Comparaison via critères AIC, AICc
- Évaluation hors-échantillon (prévision glissante et à 12 mois)
- Visualisation des erreurs quadratiques cumulées (CSPE)
- Test de Diebold-Mariano pour comparer les modèles

## 🧠 Résultats

Le modèle **ADAM ETS + ARIMA** s’est révélé être le plus performant sur la période de prévision :
- Meilleure précision hors-échantillon (MSE le plus faible)
- Meilleur R² hors échantillon
- Erreurs prévisionnelles cumulées les plus faibles
- Test de Diebold-Mariano significatif face au modèle naïf

Ce modèle s’avère robuste et bien adapté à la nature non stationnaire des séries financières.

## 💻 Technologies utilisées

- Langage : **R**
- Packages : `forecast`, `smooth`, `RJDemetra`, `tseries`, `urca`, `ggplot2`, `tidyverse`

## 👥 Auteurs

- Pierre QUINTIN de KERCADIO
- Florian CROCHET

