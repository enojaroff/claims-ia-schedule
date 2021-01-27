# Données transmises

Liste des informations transmises lors des différents échanges

<!-- title: Liste des champs transmis -->

| Données                            | Créneau horaire | Rendez-vous | Remarques                       |
| :--------------------------------- | :-------------: | :---------: | :------------------------------ |
| Assureur                           |        O        |      O      |                                 |
| Contrat                            |        O        |      O      | Nom du contrat                  |
| _N° contrat_                       |                 |             |                                 |
| **_Assuré_**                       |                 |      O      |                                 |
| **_Qualité de l'assuré_**          |                 |      O      |                                 |
| Lieu du sinistre                   |        O        |      O      |                                 |
| Type de sinistre                   |        O        |      O      | _DDE, DE, CATNAT, VOL_          |
| Type d'expertise                   |        O        |      O      |                                 |
| Date du sinistre                   |        O        |      O      |                                 |
| Date de la déclaration             |        O        |      O      |                                 |
| Type d'habitation                  |        O        |      O      |                                 |
| Adresse de l'habitaion             |        O        |      O      |                                 |
| Pesée Claims                       |        O        |      O      | Varie selon le type de sinistre |
| Lieu de RDV                        |        O        |      O      | Si **ESS**                      |
| **_Liste des dommages immo_**      |        R        |      O      | Avec ou sans chiffrage ?        |
| **_Liste des dommages mobiliers_** |        R        |      O      | Avec ou sans chiffrage ?        |
| **_Pièces-jointes_**               |                 |      O      |                                 |
| **_Identité de l'assuré_**         |                 |      O      | Différent du contact RDV        |
| **_Identité du contact DV_**       |                 |      O      |                                 |
| <hr>                               |      <hr>       |    <hr>     | <hr>                            |
| `ESS` : Lieu de RDV souhaité       |        O        |      O      | Usage futur                     |
| `EAD` : Données de connexion       |        O        |      O      | Usage futur                     |

<!-- theme: info -->

> _**O**: Oui<br> **R**: Liste réduite aux seuls éléments, sans indication d'âge, de valeur et de vétusté_
>
> - _Pour les biens immobiliers: surfaces, revêtement_
> - _Pour les biens mobiliers, catégorie, sous-catégorie, nom_


```
ESS

  --> Contact
        email
        téléphone
  --> Adresse du bien               (pas forcément limité à ESS)
  --> Lieu de rendez-vous souhaité  (usage futur)

  <-- Lieu de rendez-vous           (si différent du souhaité)
  <-- Informations complémentaires


VISIO

  --> Contact
        email
        téléphone
  --> Terminal                      (usage futur)
  --> connexion                     (usage futur)

  <-- Informations complémentaires (Procédure de connexion visio)


TELEPHONE

  --> Contact
        email
        téléphone

  <-- Informations complémentaires
```

[Codes Sinapps utilisés](docs/sinapps/Type-de-risque.md)
