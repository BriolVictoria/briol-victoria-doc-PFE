---
layout: page
title: "Performance serveur"
permalink: /server-performance/
---

# Performance côté serveur

Cette page présente l'analyse des performances côté serveur réalisée durant le développement du projet.

L'objectif est de vérifier le comportement de l'application et d'identifier d'éventuelles optimisations.

---

## 1. Outil utilisé

### Laravel Debugbar

L'analyse des performances a été réalisée à l'aide de **Laravel Debugbar**.

Cet outil permet notamment de :

- visualiser les requêtes SQL exécutées ;
- observer l'utilisation mémoire ;
- analyser les informations liées aux routes et aux vues ;
- détecter d'éventuels problèmes de performance.

---

## 2. Vue globale des performances

### Capture d'écran

<img src="/images/laravel_debugbar_overview.png" alt="Vue générale Laravel Debugbar" width="800">

*Figure 1 — Vue générale des informations fournies par Laravel Debugbar.*

### Observations

La barre de débogage permet d'obtenir rapidement une vue d'ensemble des informations techniques de la page :

- nombre de requêtes exécutées ;
- utilisation mémoire ;
- informations relatives aux vues ;
- détails sur les routes utilisées.

---

## 3. Analyse des requêtes SQL

### Capture d'écran

<img src="/images/laravel_debugbar_queries.png" alt="Analyse des requêtes SQL" width="800">

*Figure 2 — Analyse des requêtes SQL exécutées.*

### Observations

Les requêtes SQL générées par l'application ont été observées afin de vérifier leur nombre et leur exécution.

Les résultats montrent :

- un nombre de requêtes maîtrisé ;
- une exécution correcte des opérations en base de données ;
- l'absence de requêtes problématiques identifiées lors des tests.

---

## 4. Utilisation mémoire

### Capture d'écran

<img src="/images/laravel_debugbar_memory.png" alt="Utilisation mémoire" width="800">

*Figure 3 — Utilisation mémoire observée via Debugbar.*

### Observations

L'utilisation mémoire reste cohérente avec les fonctionnalités proposées par l'application.

Aucun comportement anormal n'a été observé lors des différentes analyses.

---

## Conclusion

L'analyse réalisée avec Laravel Debugbar montre des performances globalement satisfaisantes.

L'observation des requêtes SQL, des vues et de l'utilisation mémoire a permis de vérifier le bon fonctionnement du backend tout au long du développement.

---

👉 [⬅ Retour à l'accueil](/)
