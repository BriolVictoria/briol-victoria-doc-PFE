---
layout: page
title: "Performance serveur"
permalink: /server-performance/
---

# Performance serveur

Ce document présente l'analyse des performances serveur de l'application à l'aide des outils Laravel Debugbar et Laravel Telescope.

L'objectif est d'évaluer les temps de réponse, les requêtes SQL et le comportement global de l'application côté backend.

---

# 1. Outils utilisés

Les outils suivants ont été utilisés pour analyser les performances serveur :

- Laravel Debugbar : analyse des requêtes et du temps d'exécution
- Laravel Telescope : suivi des requêtes, jobs, exceptions et événements

---

# 2. Analyse avec Laravel Debugbar

## Aperçu global

<img src="/images/debugbar-overview.png" alt="Laravel Debugbar aperçu" width="800">

---

## Temps de réponse

Les temps de réponse observés restent globalement :

- ...
- ...
- ...

---

## Requêtes SQL

L'analyse des requêtes SQL permet de mettre en évidence :

- le nombre total de requêtes exécutées ;
- les éventuelles requêtes répétées ;
- les optimisations possibles.

### Capture des requêtes

<img src="/images/debugbar-queries.png" alt="Requêtes SQL Debugbar" width="800">

---

## Conclusion Debugbar

...

---

# 3. Analyse avec Laravel Telescope

## Vue générale

<img src="/images/telescope-overview.png" alt="Laravel Telescope aperçu" width="800">

---

## Observations principales

L'analyse via Telescope permet d'observer :

- les requêtes HTTP ;
- les requêtes base de données ;
- les jobs exécutés ;
- les éventuelles erreurs ou exceptions.

---

## Détails des requêtes

<img src="/images/telescope-queries.png" alt="Requêtes Telescope" width="800">

---

## Gestion des jobs et événements

...

---

## Conclusion Telescope

...

---

# 4. Synthèse globale des performances

Dans l'ensemble, l'application présente :

- des temps de réponse globalement satisfaisants ;
- une gestion correcte des requêtes SQL ;
- une architecture serveur cohérente ;
- des pistes d'optimisation sur certaines requêtes répétitives.

Des améliorations peuvent être envisagées sur :

- la réduction du nombre de requêtes ;
- l'optimisation des requêtes complexes ;
- la mise en cache de certaines données.

---

# Conclusion générale

L'analyse des performances serveur montre un comportement globalement stable et conforme aux attentes d'une application web moderne utilisant Laravel.

---

👉 [⬅ Retour à l'accueil](/)
