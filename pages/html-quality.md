---
layout: page
title: "Qualité du code HTML"
permalink: /html-quality/
---

# Qualité du code HTML

Ce document présente les éléments attestant de la qualité du code HTML du projet.

---

## 1. Headings map des pages publiques

Les pages publiques respectent une structure logique des titres.

### Rendu Headings map
Capture d’écran de la page d'accueil:

![Headings map - page accueil](/images/headings_map_homepage.png)

Capture d’écran de la page d'aide:

![Headings map - page ...](/images/headings_map_helper.png)

---

## 📌 2. Validation du code HTML (Total Validator)

Les pages ont été testées avec l’outil Total Validator.

### Résultats de validation

📷 Capture d’écran du résultat global :

![Validation HTML - global](/images/...)

📷 Capture d’écran détails erreurs (si applicable) :

![Validation HTML - détails](/images/...)

### Conclusion
...

---

## 📌 3. Bonnes pratiques et sémantique HTML

Le projet respecte les bonnes pratiques suivantes :

- Utilisation de balises sémantiques (`header`, `main`, `section`, `article`)
- Hiérarchie correcte des titres
- Séparation claire contenu / structure

### HTML checklist
📷 Résultat checklist :

![HTML checklist](/images/...)

### Commentaires
...

---

## 📌 4. Microdata (schema.org)

Certaines pages utilisent des microdonnées pour enrichir le contenu.

### Microdata utilisée
```html
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
### Résultats de validation

📷 Capture d’écran du résultat global :

![Microdata - page aide](/images/microdata_helper.png)
...
