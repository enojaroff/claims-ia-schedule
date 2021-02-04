---
tags: [documentation]
---

# Erreurs

L'**API Claims IA** utilise des codes de réponse HTTP conventionnels pour indiquer le succès ou l'échec d'une requête API. 

En général: 

-   Les codes de la catégorie **`2xx`** indiquent le succès. 
-   Les codes de la catégorie **`4xx`** indiquent une erreur qui a échoué compte tenu des informations fournies (par exemple, un paramètre requis a été omis, une charge a échoué, etc.). 
-   Les codes de la catégorie **`5xx`** indiquent une erreur avec les serveurs.

Certaines erreurs `4xx` qui pourraient être traitées par programme incluent un code d'erreur qui explique brièvement l'erreur signalée.
