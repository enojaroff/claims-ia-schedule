# Données transmises au partenaire (EXP, REN)

Liste des informations transmises par Claims IA au partenaire.
Les données sont soit :

- **\|––>** envoyées dans la requête émise par Claims IA (_endpoint partennaire_)
- **\|<––** fournies en réponse à une requête du partenaire (_endpoint Claims IA_)

<!-- title: Liste des champs transmis -->

| Données                      | Créneaux hor. | Rendez-vous | Remarques                         |
| :--------------------------- | :-----------: | :---------: | :-------------------------------- |
| Processus                    |     \|––>     |    \|––>    | Champ libre                       |
| Assureur                     |     \|––>     |    \|––>    | Identifiant de l'assureur         |
| Contrat                      |               |    \|<––    | Nom du contrat                    |
| N° contrat                   |               |    \|––>    | Réf. assureur du contrat          |
| Ref Claims IA                |               |    \|––>    | Réf. interne de la déclaration    |
| Ref Sinistre                 |               |    \|––>    | Réf. assureur du sinistre         |
| Qualité de l'assuré          |               |    \|<––    | CPO, LOC, PNO, ...                |
| Adresse du risque            |               |    \|<––    |                                   |
| Type de sinistre             |     \|––>     |    \|––>    | _DDE, DE, CATNAT, VOL_            |
| Type d'expertise             |     \|––>     |    \|––>    | VISIO, EAD, ESS, CONTRADICTOIRE   |
| Date du sinistre             |     \|––>     |    \|––>    |                                   |
| Date de la déclaration       |               |    \|––>    |                                   |
| Type d'habitation            |     \|––>     |    \|––>    |                                   |
| Adresse de l'habitaion       |     \|––>     |    \|––>    |                                   |
| Enjeu                        |     \|––>     |    \|––>    | Varie selon le type de sinistre   |
| Enjeu DM                     |     \|––>     |    \|––>    |
| Enjeu DI                     |     \|––>     |    \|––>    |                                   |
| Lieu de RDV                  |     \|––>     |    \|––>    | Si **ESS**                        |
| _Géocodage lieu RDV_         |     \|––>     |    \|––>    | V2                                |
| Liste des dommages immo      |               |    \|<––    | Avec ou sans chiffrage ?          |
| Liste des dommages mobiliers |               |    \|<––    | Avec ou sans chiffrage ?          |
| Pièces-jointes               |               |    \|<––    | URL des documents                 |
| Identité de l'assuré         |               |    \|<––    | Différent du contact RDV          |
| Identité du contact RDV      |               |    \|<––    | Si la personne n'est pas l'assuré |
| <hr>                         |     <hr>      |    <hr>     | <hr>                              |
| USAGE FUTUR                  |               |             |                                   |
| <hr>                         |     <hr>      |    <hr>     | <hr>                              |
| `ESS` : Lieu de RDV souhaité |     \|––>     |    \|––>    |                                   |
| `EAD` : Données de connexion |               |    \|<––    |                                   |

