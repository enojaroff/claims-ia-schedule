# Données transmises

Liste des informations transmises lors des différents échanges

<!-- title: Liste des champs transmis -->

| Données                      | Créneau horaire | Rendez-vous | Remarques                         |
| :--------------------------- | :-------------: | :---------: | :-------------------------------- |
| Processus                    |      \|->       |    \|->     | Champ libre                       |
| Assureur                     |      \|->       |    \|->     |                                   |
| Contrat                      |                 |    \|<-     | Nom du contrat                    |
| N° contrat                   |                 |    \|<-     |                                   |
| Ref Claims IA                |                 |             |                                   |
| Ref Sinistre                 |                 |    \|->     | Ref assureur                      |
| Qualité de l'assuré          |                 |    \|<-     | CP, lOC,..                        |
| Adresse du risque            |                 |    \|<-     |                                   |
| Type de sinistre             |      \|->       |    \|->     | _DDE, DE, CATNAT, VOL_            |
| Type d'expertise             |      \|->       |    \|->     | VISIO, EAD, ESS, CONTRADICTOIRE   |
| Date du sinistre             |      \|->       |    \|->     |                                   |
| Date de la déclaration       |                 |    \|->     |                                   |
| Type d'habitation            |      \|->       |    \|->     |                                   |
| Adresse de l'habitaion       |      \|->       |    \|->     |                                   |
| Enjeu                        |      \|->       |    \|->     | Varie selon le type de sinistre   |
| Enjeu DM                     |      \|->       |    \|->     |
| Enjeu DI                     |      \|->       |    \|->     |                                   |
| Lieu de RDV                  |      \|->       |    \|->     | Si **ESS**                        |
| _Géocodage lieu RDV_         |      \|->       |    \|->     | V2                                |
| Liste des dommages immo      |                 |    \|<-     | Avec ou sans chiffrage ?          |
| Liste des dommages mobiliers |                 |    \|<-     | Avec ou sans chiffrage ?          |
| Pièces-jointes               |                 |    \|<-     | URL des documents                 |
| Identité de l'assuré         |                 |    \|<-     | Différent du contact RDV          |
| Identité du contact RDV      |                 |    \|<-     | Si la personne n'est pas l'assuré |
| <hr>                         |      <hr>       |    <hr>     | <hr>                              |
| USAGE FUTUR                  |                 |             |                                   |
| <hr>                         |      <hr>       |    <hr>     | <hr>                              |
| `ESS` : Lieu de RDV souhaité |      \|->       |    \|->     |                                   |
| `EAD` : Données de connexion |                 |    \|<-     |                                   |

Réponse

- ## Liste de créneaux

<!-- theme: info -->

> _**\|->** : Données envoyées par Claims IA dans la requête<br>
> **\|<-** : Données récupérées par le partenaire via des endpoints coté Claims IA

CONTEXTE

ESS

```
  --> Contact
        email
        téléphone
  --> Adresse du bien               (pas forcément limité à ESS)

  <-- Lieu de rendez-vous           (si différent du souhaité)
  <-- Informations complémentaires  (à définir)
```

VISIO

```
  --> Contact
        email
        téléphone
  --> Adresse du bien               (pas forcément limité à ESS)

  <-- Informations complémentaires  (Procédure de connexion visio)
```

[Codes Sinapps utilisés](docs/sinapps/Type-de-risque.md)
