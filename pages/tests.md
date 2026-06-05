---
layout: page
title: "Tests automatisés"
permalink: /tests/
---

# Tests automatisés

Ce document présente un ensemble représentatif des tests automatisés réalisés dans le cadre du projet.

L'application dispose de **57 tests automatisés au total**, couvrant à la fois les fonctionnalités serveur (backend) et les scénarios utilisateur (browser testing).

---

# 1. Répartition des tests

Les tests sont répartis en deux catégories :

- Tests côté serveur 
- Tests de type browser

Cette séparation permet de valider à la fois la logique métier et les parcours utilisateur complets.

---

# 2. Tests côté serveur

Les tests backend permettent de vérifier le bon fonctionnement des règles métier, des contrôleurs et des modèles.

## Exemples de tests réalisés

- Authentification utilisateur
- Inscription utilisateur
- Gestion des rôles et permissions
- Création d’enregistrements
- Mise à jour de données
- Suppression de ressources
- Validation des formulaires
- Accès aux routes protégées

### Exemple de test

```php
it('verifies if a user cannot register without a name', function () {
    $response = $this->post(route('register', app()->getLocale()), [
        'name' => '',
        'email' => 'vic@test.com',
        'password' => 'password',
        'password_confirmation' => 'password',
    ]);

    $response->assertSessionHasErrors('name');
});
```

---

# 3. Tests Browser 

Les tests browser simulent le comportement réel d’un utilisateur dans l’application.

## Exemples de scénarios testés

- Navigation sur le site public
- Connexion utilisateur
- Remplissage de formulaires
- Création de contenu
- Interaction avec les interfaces dynamiques
- Vérification des messages d’erreur
- Flux complet utilisateur (inscription → action principale)

### Exemple de test browser

```php
it('can logout', function () {
    $user = User::factory()->create();
    actingAs($user);

    visit(route('dashboard'))
        ->assertSee('Dashboard')
        ->click('.logout_browser_selector')
        ->assertSee('Log in');
});
```

---

# 4. Volume de tests

L’application contient au total :

- **57 tests automatisés**
  - environ 30+ tests backend
  - environ 15+ tests browser
  - tests supplémentaires pour cas limites et erreurs

---

# 5. Résultats des tests

### Capture des résultats

<img src="../images/tests_results.png" alt="Résultats des tests automatisés" width="800">

---

# 6. Analyse

Les tests permettent de garantir :

- la stabilité des fonctionnalités principales ;
- la non-régression lors des modifications ;
- la fiabilité des parcours utilisateurs ;
- la robustesse des règles métier.

Quelques cas limites ont été ajoutés afin de renforcer la couverture globale.

---

# Conclusion

La présence de 57 tests automatisés démontre un effort important de qualité logicielle et de fiabilité de l'application.

Les tests couvrent à la fois la logique serveur et les interactions utilisateur, garantissant un comportement cohérent de l’ensemble du système.

---

[Retour à l'accueil](../)
