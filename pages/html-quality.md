---
layout: page
title: "Qualité du code HTML"
permalink: /html-quality/
---

# Qualité du code HTML

Cette page présente les éléments permettant de savoir la qualité du code HTML produit dans le cadre du projet.

---

## 1. Structure des titres (Headings Map)

Une attention particulière a été portée à la hiérarchie des titres afin de garantir une structure claire du contenu et une bonne accessibilité.

### Page d'accueil

<img src="../images/headings_map_homepage.png" alt="Headings Map - Accueil" width="800">

*Figure 1 — Structure des titres de la page d'accueil.*

### Page d'aide

<img src="../images/headings_map_helper.png" alt="Headings Map - Aide" width="800">

*Figure 2 — Structure des titres de la page d'aide.*

### Observations

- Présence d'un unique titre principal (`H1`) par page.
- Respect de la hiérarchie des niveaux de titres.
- Structure cohérente facilitant la navigation et l'accessibilité.

---

## 2. Validation HTML

Les pages du site ont été analysées à l'aide de l'outil **Total Validator** afin de vérifier leur conformité HTML.

### Résultat des pages

#### Page d'accueil

<img src="../images/homepage_validator.png" alt="Headings Map - Accueil" width="800">

*Figure 3 — Résultat de la validation HTML sur la page d'accueil.*

#### Page d'aide

<img src="../images/helper_validator.png" alt="Headings Map - Aide" width="800">

*Figure 4 — Résultat de la validation HTML sur la page d'aide.*

#### Page de login

<img src="../images/login_validator.png" alt="Headings Map - Login" width="800">

*Figure 5 — Résultat de la validation HTML sur la page de login.*

#### Page de register

<img src="../images/register_validator.png" alt="Headings Map - Register" width="800">

*Figure 6 — Résultat de la validation HTML sur la page de register.*

#### Page dashboard

<img src="../images/dashboard_validator.png" alt="Headings Map - Dashboard" width="800">

*Figure 7 — Résultat de la validation HTML sur la page dashboard.*

#### Page de Clothes-Index

<img src="../images/clothes_index_validator.png" alt="Headings Map - Clothes Index" width="800">

*Figure 8 — Résultat de la validation HTML sur la page de clothes index.*

#### Page de Clothes-Create

<img src="../images/clothes_create_valdiator.png" alt="Headings Map - Clothes Create" width="800">

*Figure 9 — Résultat de la validation HTML sur la page de clothes create.*

#### Page de Clothes-Show

<img src="../images/clothes_show_valdiator.png" alt="Headings Map - Clothes Show" width="800">

*Figure 10 — Résultat de la validation HTML sur la page de clothes show.*

#### Page de Clothes-Edit

<img src="../images/clothes_edit_valdiator.png" alt="Headings Map - Clothes Edit" width="800">

*Figure 11 — Résultat de la validation HTML sur la page de clothes edit.*

#### Page de Favorite

<img src="../images/favroite_valdiator.png" alt="Headings Map - Favorite" width="800">

*Figure 12 — Résultat de la validation HTML sur la page de favorite.*

#### Page de Closet-Index

<img src="../images/closet_valdiator.png" alt="Headings Map - Closet Index" width="800">

*Figure 13 — Résultat de la validation HTML sur la page de closet index.*

#### Page de Settings

<img src="../images/settings_valdiator.png" alt="Headings Map - Settings" width="800">

*Figure 14 — Résultat de la validation HTML sur la page de settings.*

### Analyse des résultats

Les erreurs détectées proviennent de l'utilisation de Laravel Livewire, qui ajoute des attributs que le validateur ne reconnaît pas, ainsi que du token CSRF généré automatiquement par Laravel. Ces éléments ne peuvent pas être modifiés car ils sont indispensables au bon fonctionnement de l'application.
Les avertissements sont liés au double menu de navigation (mobile et desktop) présent dans le code, ce qui est tout à fait normal pour un site responsive.

### Conclusion

Ces erreurs et avertissements ne sont donc pas de vraies erreurs de développement, mais simplement des contraintes liées aux outils et à l'architecture du projet.

---

## 3. Respect des bonnes pratiques HTML et sémantique

Le développement du projet a été réalisé en respectant les bonnes pratiques HTML modernes ainsi que les recommandations de structuration sémantique.

L’objectif est de garantir un code lisible, accessible et maintenable.

---

### Structure sémantique du projet

Le projet repose sur une utilisation systématique des balises sémantiques HTML :

- `<header>` : en-tête et navigation principale
- `<main>` : contenu principal des pages
- `<section>` : découpage logique des contenus
- `<footer>` : informations de fin de page

Cette organisation améliore la compréhension du code et facilite l’accessibilité.

---

### Hiérarchie des titres

Une attention particulière a été portée à la hiérarchie des titres :

- un seul `<h1>` par page ;
- utilisation cohérente des `<h2>`, `<h3>`, etc. ;
- structure logique respectant le contenu.

Cela permet une meilleure navigation, notamment pour les lecteurs d’écran.

---

### Accessibilité et bonnes pratiques

Plusieurs règles essentielles ont été respectées :

- utilisation systématique des attributs `alt` pour les images ;
- association correcte des labels aux champs de formulaires ;
- navigation possible au clavier ;
- structure HTML cohérente et lisible ;
- séparation claire entre structure et présentation.

---

### Analyse

Les résultats montrent que :

- la structure HTML est cohérente ;
- les éléments sémantiques sont correctement utilisés ;
- les règles d’accessibilité principales sont respectées ;
- le code reste lisible et maintenable.

---

### Conclusion

Le projet respecte globalement les bonnes pratiques HTML modernes.

Ces choix permettent d’améliorer :
- l’accessibilité ;
- la maintenabilité ;
- le référencement naturel ;
- la qualité globale du code.

---

## 4. Utilisation des microdatas

Une page utilise des microdatas Schema.org afin d'améliorer la compréhension du contenu par les moteurs de recherche.

### Implémentation

```html
@props([
    'title',
    'sub_title',
    'details',
])

<section
    class="bg-linear-to-r from-amber-800 via-amber-50 to-amber-800">
    <div class="section-public max-w-440 m-auto justify-center flex flex-col gap-6">
        <div itemscope itemtype="https://schema.org/FAQPage">
            <div itemscope itemprop="mainEntity" itemtype="https://schema.org/Question" class="flex flex-col gap-3">
                <h2 itemprop="name"
                    class="font-[Bodoni] text-5xl lg:text-7xl text-rose-900 font-normal text-center">{!! $title !!}</h2>
                <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
                    <p itemprop="text"
                       class="text-base lg:text-lg text-rose-900 font-normal text-center">{!! $sub_title !!}</p>
                </div>
            </div>
        </div>

        <div class="flex flex-col gap-3 2xl:grid 2xl:grid-cols-13">
            @foreach($details as $detail)
                <x-public.helper.faq_details
                    :title="$detail['title']"
                    :content="$detail['content']"
                    :image_path="$detail['image_path']"
                    :image_alt="$detail['image_alt']"
                />
            @endforeach
        </div>
    </div>
</section>

```

### Validation

<img src="../images/microdata_helper.png" alt="Validation Microdata" width="800">

*Figure 15 — Vérification des microdatas de la page d'aide.*

### Conclusion

Les microdonnées permettent d'enrichir les informations fournies aux moteurs de recherche et d'améliorer l'indexation du contenu.

---

## 5. Optimisation des images

Les images ont été optimisées afin d'améliorer les performances du site et de réduire les temps de chargement.

### Redimensionnement côté serveur

Lorsque cela est pertinent, plusieurs versions d'une même image sont générées afin d'éviter le téléchargement d'images plus volumineuses que nécessaire.

Cette approche permet :

- de réduire le poids des pages ;
- d'améliorer les temps de chargement ;
- de limiter la consommation de bande passante ;
- d'améliorer les performances mesurées par Lighthouse.

### Utilisation de `srcset`

Les images responsives utilisent l'attribut `srcset` afin de proposer automatiquement une version adaptée à la taille de l'écran.

#### Exemple

```html
<img
     src="{!! $image_path !!}"
     srcset="
        {{ asset('asset/img/public/hero_section/dashboard_image/dashboard-400.webp') }} 400w,
        {{ asset('asset/img/public/hero_section/dashboard_image/dashboard-800.webp') }} 800w,
        {{ asset('asset/img/public/hero_section/dashboard_image/dashboard-1200.webp') }} 1200w,
        {{ asset('asset/img/public/hero_section/dashboard_image/dashboard-1600.webp') }} 1600w"
                sizes="(max-width: 768px) 90vw, 70vw"
                alt="{!! $image_alt !!}"
                width="1600"
                height="900"
                loading="eager"
                fetchpriority="high"
                class="appears_up 2xl:w-308 w-87.5 lg:w-150 shadow-md"
/>
```

### Capture du code généré

<img src="../images/srcset_images_homepage.png" alt="Exemple srcset" width="800">

*Figure 16 — Utilisation de l'attribut srcset.*

### Résultats obtenus

Les optimisations mises en œuvre permettent :

- une meilleure expérience utilisateur sur mobile ;
- une réduction du volume de données téléchargées ;
- un chargement plus rapide des pages ;
- une amélioration des indicateurs de performance.

---

## Conclusion générale

Les différentes vérifications réalisées démontrent le respect des bonnes pratiques HTML du projet :

- structure cohérente des titres ;
- conformité du code HTML ;
- utilisation de balises sémantiques ;
- intégration de microdonnées ;
- optimisation du chargement des images.

Ces éléments contribuent à améliorer l'accessibilité, la maintenabilité et les performances globales de l'application.

---

[Retour à l'accueil](../)
