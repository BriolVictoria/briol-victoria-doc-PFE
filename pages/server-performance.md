---
layout: page
title: "Performance serveur"
permalink: /server-performance/
---

# Performance côté serveur

Ce document présente l’analyse des performances côté serveur de l’application.

L’objectif est d’évaluer le comportement du backend en termes de temps de réponse, de requêtes SQL et de charge globale.

---

# 1. Outils d’analyse

Deux outils principaux sont associés à l’analyse des performances Laravel :

## Laravel Debugbar

Laravel Debugbar

Cet outil a été utilisé dans le projet pour :

- analyser les temps de réponse des requêtes ;
- observer les requêtes SQL exécutées ;
- vérifier les performances globales des pages ;
- identifier les éventuelles requêtes coûteuses.

---

## Laravel Telescope

Laravel Telescope

Telescope est un outil de monitoring serveur permettant d’observer :

- les requêtes HTTP ;
- les requêtes SQL ;
- les jobs et queues ;
- les exceptions ;
- les logs applicatifs.

Dans ce projet, il est présenté comme un outil de référence pour le monitoring backend, même si l’analyse principale a été réalisée avec Debugbar.

---

# 2. Analyse des performances avec Debugbar

## Vue globale

<img src="/images/debugbar-overview.png" alt="Vue Debugbar" width="800">

---

## Temps de réponse

L’analyse des temps de réponse montre que :

- les pages publiques restent rapides ;
- les pages dynamiques présentent un léger surcoût logique ;
- les performances restent globalement stables.

---

## Requêtes SQL

<img src="/images/debugbar-queries.png" alt="Requêtes SQL Debugbar" width="800">

---

Les observations principales :

- nombre de requêtes globalement maîtrisé ;
- présence de quelques requêtes répétées ;
- absence de requêtes bloquantes majeures.

---

## Conclusion Debugbar

L’analyse via Debugbar confirme que l’application présente de bonnes performances globales côté serveur.

---

# 3. Analyse globale des performances

Les performances du backend sont globalement satisfaisantes :

- temps de réponse corrects ;
- requêtes SQL maîtrisées ;
- architecture Laravel cohérente ;
- séparation logique des responsabilités respectée.

---

# 4. Pistes d’amélioration

Certaines optimisations peuvent être envisagées :

- réduction des requêtes répétitives (optimisation Eloquent) ;
- mise en cache de certaines données statiques ;
- optimisation des relations chargées (eager loading).

---

# Conclusion

L’analyse des performances serveur met en évidence un backend stable et performant.

L’utilisation de Laravel Debugbar a permis d’identifier les comportements de l’application en conditions réelles, tandis que Laravel Telescope est un outil complémentaire permettant un monitoring avancé des applications Laravel.

---

👉 [⬅ Retour à l'accueil](/)
