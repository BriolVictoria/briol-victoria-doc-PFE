---
layout: page
title: "Améliorations JavaScript et dégradation gracieuse"
permalink: /js-enhancements/
---

# Améliorations de l’expérience utilisateur avec JavaScript

Cette page présente les améliorations de l'interface grâce à JavaScript ainsi que les mécanismes de dégradation gracieuse mis en place.

L'utilisation de JavaScript dans mon projet n'est pas seulement la pour ajouter de l'interactivité, mais aussi pour avoir une expérience utilisateur plus enrichis en conservant une application fonctionnelle.

---

# 1. Gestion des onglets dynamiques (Tabs)

Un espace de mon projet repose sur un système d'onglets dynamiques qui permet d'afficher différents contenues sans devoir recharger la page.

## Fonctionnalités mises en place

- Navigation entre contenus via clic utilisateur ;
- Défilement automatique des onglets ;
- Mise en évidence visuelle de l’onglet actif ;
- Gestion de l’état actif dans l’interface.

## Exemple d’implémentation

```javascript
const showTab = {
    tabs: document.querySelectorAll(".tab-btn"),
    contents: document.querySelectorAll(".tab-content"),
    currentTab: 0,

    init() {
        this.showTab(0);

        setInterval(() => {
            this.showTab((this.currentTab + 1) % this.tabs.length);
        }, 10000);

        this.tabs.forEach((tab, index) => {
            tab.addEventListener("click", () => {
                this.showTab(index);
            });
        });
    },
    showTab(index) {
        this.tabs.forEach((tab) => {
            tab.classList.remove("bg-rose-500", "text-amber-50", "shadow-lg");
            tab.classList.add("bg-amber-50", "text-rose-500");
        });

        this.contents.forEach((content) => {
            content.classList.add("hidden");
        });

        this.tabs[index].classList.add("bg-rose-500", "text-amber-50", "shadow-lg");
        this.tabs[index].classList.remove("bg-amber-50", "text-rose-500");
        this.contents[index].classList.remove("hidden");

        this.currentTab = index;
    }
}

if (document.querySelector('.tab-btn')) {
    showTab.init();
}

```

## Apport UX

Cette fonctionnalité améliore :

- la navigation dans les contenus ;
- la fluidité de l’interface ;
- la réduction des rechargements de page ;
- l’engagement utilisateur.

---

# 2. Visualisation de données (ECharts)

Le projet utilise la librairie **ECharts** pour afficher des graphiques dynamiques.

## Fonctionnalités

- Affichage de graphiques interactifs ;
- Données injectées dynamiquement via `data-*` ;
- Redimensionnement automatique des graphiques ;
- Compatibilité avec navigation dynamique (Livewire).

## Exemple (graphique couleur)

```javascript
import * as echarts from 'echarts';

function initColorChart() {
    const chartDom = document.getElementById('color_chart');
    const myChart = echarts.init(chartDom);

    const option = JSON.parse(chartDom.dataset.chart);

    myChart.setOption(option);

    addEventListener('resize', () => {
        myChart.resize();
    });
}

addEventListener('DOMContentLoaded', function () {
    initColorChart();
});

addEventListener('livewire:navigated', function () {
   initColorChart();
});
```

## Apport UX

- lecture simplifiée des données ;
- meilleure compréhension visuelle ;
- interface plus moderne et interactive ;
- adaptation automatique aux écrans.

---

# 3. Galerie d’images interactive

Le projet utilise **Fancybox** pour améliorer l’affichage des images.

## Fonctionnalités

- ouverture des images en plein écran ;
- navigation entre images ;
- expérience immersive sans quitter la page.

## Exemple d’implémentation

```javascript
import { Fancybox } from "@fancyapps/ui/dist/fancybox/";
import "@fancyapps/ui/dist/fancybox/fancybox.css";

Fancybox.bind('[data-fancybox]');
```

## Apport UX

- amélioration de la consultation des images ;
- interface plus fluide et moderne ;
- suppression des redirections vers des pages d’image.

---

# 4. Dégradation gracieuse

Une attention particulière a été portée à la compatibilité en cas de désactivation de JavaScript.

## Comportement sans JavaScript

- les contenus de base restent accessibles ;
- les onglets affichent le contenu par défaut ;
- les données restent lisibles ;
- les images restent consultables sans Fancybox.
---

# 5. Conclusion

L’utilisation de JavaScript dans le projet permet d’améliorer l’expérience utilisateur à travers :

- une navigation plus fluide (tabs) ;
- une meilleure visualisation des données (ECharts) ;
- une meilleure visualisation des images (Fancybox).

---

[Retour à l'accueil](../)
