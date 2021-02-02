---
tags: [Common]
---

# Authentification

> ### WIP
>
> A compléter ou réécrire

L'API Schedule de Claims IA utilise des clés API pour authentifier les demandes.

En mode test, les clés secrètes ont le préfixe `test_`.

### Basic Auth

L'authentification auprès de l'API est effectuée via **HTTP Basic Auth**. La clé API est passée comme valeur du nom d'utilisateur d'authentification. Pas besoin de fournir de mot de passe.

Toutes les demandes d'API doivent être effectuées via HTTPS. Les appels effectués via HTTP simple seront rejetés. Les demandes d'API sans authentification échoueront également.
