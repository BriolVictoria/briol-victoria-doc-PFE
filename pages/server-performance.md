---
layout: page
title: "Performance serveur"
permalink: /server-performance/
---

# Performance côté serveur

Cette page présente l'analyse des performances côté serveur réalisée durant le développement du projet.

L'objectif est de vérifier le comportement de l'application en termes de temps de réponse, d'exécution des requêtes SQL et de performance globale.

---

## 1. Outil utilisé

### Laravel Debugbar

L'analyse des performances a été réalisée à l'aide de **Laravel Debugbar**.

Cet outil permet notamment de :

- mesurer les temps de réponse ;
- visualiser les requêtes SQL exécutées ;
- observer l'utilisation mémoire ;
- détecter d'éventuels problèmes de performance ;
- analyser les informations liées aux routes et aux vues.

---

## 2. Vue globale des performances

### Capture d'écran

<img src="/images/debugbar-overview.png" alt="Vue générale Laravel Debugbar" width="800">

*Figure 1 — Vue générale des informations fournies par Laravel Debugbar.*

---

## 3. Analyse des temps de réponse

Les différentes pages de l'application ont été observées afin d'évaluer leurs temps de chargement.

### Capture d'écran

<img src="/images/debugbar-response-time.png" alt="Temps de réponse Debugbar" width="800">

*Figure 2 — Analyse des temps de réponse.*

### Observations

- Les temps de réponse restent faibles.
- Les pages publiques se chargent rapidement.
- Les fonctionnalités dynamiques conservent des performances satisfaisantes.

---

## 4. Analyse des requêtes SQL

Laravel Debugbar permet d'afficher l'ensemble des requêtes exécutées pour une page donnée.

### Capture d'écran

<img src="/images/debugbar-queries.png" alt="Analyse des requêtes SQL" width="800">

*Figure 3 — Analyse des requêtes SQL exécutées.*

### Observations

- Le nombre de requêtes reste maîtrisé.
- Les requêtes sont exécutées rapidement.
- Aucune requête particulièrement coûteuse n'a été identifiée.

---

## 5. Utilisation mémoire

### Capture d'écran

<img src="/images/debugbar-memory.png" alt="Utilisation mémoire" width="800">

*Figure 4 — Utilisation mémoire observée via Debugbar.*

### Observations

- La consommation mémoire reste raisonnable.
- Aucun comportement anormal n'a été observé lors des tests.

---

## Conclusion

L'analyse réalisée à l'aide de Laravel Debugbar met en évidence des performances satisfaisantes pour l'application.

Les temps de réponse, le nombre de requêtes SQL et l'utilisation mémoire restent cohérents avec les fonctionnalités proposées.

Cette phase d'observation a permis de vérifier le bon comportement du backend et d'identifier d'éventuelles pistes d'optimisation durant le développement.

---

👉 [⬅ Retour à l'accueil](/)
