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

<img src="/images/headings_map_homepage.png" alt="Headings Map - Accueil" width="800">

*Figure 1 — Structure des titres de la page d'accueil.*

### Page d'aide

<img src="/images/headings_map_helper.png" alt="Headings Map - Aide" width="800">

*Figure 2 — Structure des titres de la page d'aide.*

### Observations

- Présence d'un unique titre principal (`H1`) par page.
- Respect de la hiérarchie des niveaux de titres.
- Structure cohérente facilitant la navigation et l'accessibilité.

---

## 2. Validation HTML

Les pages du site ont été analysées à l'aide de l'outil **Total Validator** afin de vérifier leur conformité HTML.

### Résultat global

<img src="/images/..." alt="Validation HTML" width="800">

*Figure 3 — Résultat de la validation HTML.*

### Détails des éventuelles erreurs

<img src="/images/..." alt="Détails validation HTML" width="800">

*Figure 4 — Détail des erreurs et avertissements détectés.*

### Conclusion

...

---

## 3. Respect des bonnes pratiques HTML

Le développement du projet s'appuie sur les recommandations de la HTML Checklist et sur les bonnes pratiques du Web moderne.

### Éléments mis en œuvre

- Utilisation de balises sémantiques (`header`, `main`, `section`, `article`, `footer`) ;
- Hiérarchie correcte des titres ;
- Utilisation appropriée des formulaires et de leurs libellés ;
- Séparation entre structure, présentation et comportement ;
- Respect des principes d'accessibilité.

### Vérification à l'aide de la HTML Checklist

<img src="/images/..." alt="HTML Checklist" width="800">

*Figure 5 — Résultat de la vérification de la HTML Checklist.*

### Conclusion

...

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

<img src="/images/microdata_helper.png" alt="Validation Microdata" width="800">

*Figure 6 — Vérification des microdatas de la page d'aide.*

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

<img src="/images/srcset_images_homepage.png" alt="Exemple srcset" width="800">

*Figure 7 — Utilisation de l'attribut srcset.*

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

[Retour à l'accueil](/)
