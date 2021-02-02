# Donnees_transmises


Liste des informations transmises par Claims IA au partenaire.
Les données sont soit :

- **\|––>** envoyées dans la requête émise par Claims IA (_endpoint partennaire_)
- **\|&lt;––** fournies en réponse à une requête du partenaire (_endpoint Claims IA_)

| Données                      | Créneaux hor. | Rendez-vous | Remarques                         |
| :--------------------------- | :-----------: | :---------: | :-------------------------------- |
| Assureur                     |     \|––>     |    \|––>    | Identifiant de l'assureur         |
| Contrat                      |               |  \|&lt;––   | Nom du contrat                    |
| N° contrat                   |               |    \|––>    | Réf. assureur du contrat          |
| Ref Claims IA                |               |    \|––>    | Réf. interne de la déclaration    |
| Ref Sinistre                 |               |    \|––>    | Réf. assureur du sinistre         |
| Qualité de l'assuré          |               |  \|&lt;––   | CPO, LOC, PNO, ...                |
| Type assuré                  |     \|-->     |    \|-->    | Particulier, PRO                  |
| Adresse du risque            |               |  \|&lt;––   |                                   |
| Type de sinistre             |     \|––>     |    \|––>    | _DDE, DE, CATNAT, VOL_            |
| Type d'expertise             |     \|––>     |    \|––>    | VISIO, EAD, ESS, CONTRADICTOIRE   |
| Date du sinistre             |               |    \|––>    |                                   |
| Date de la déclaration       |               |    \|––>    |                                   |
| Type d'habitation            |     \|––>     |    \|––>    |                                   |
| Adresse du risque            |               |    \|––>    |                                   |
| Enjeu                        |     \|––>     |    \|––>    | TTC                               |
| Enjeu DM                     |     \|––>     |    \|––>    | TTC                               |
| Enjeu DI                     |     \|––>     |    \|––>    | TTC                               |
| Lieu de RDV                  |     \|––>     |    \|––>    |                                   |
| _Géocodage lieu RDV_         |     \|––>     |    \|––>    | V2                                |
| Liste des dommages immo      |               |  \|&lt;––   | Avec ou sans chiffrage ?          |
| Liste des dommages mobiliers |               |  \|&lt;––   | Avec ou sans chiffrage ?          |
| Pièces-jointes               |               |  \|&lt;––   | URL des documents                 |
| Identité de l'assuré         |               |  \|&lt;––   | Différent du contact RDV          |
| Identité du contact RDV      |               |  \|&lt;––   | Si la personne n'est pas l'assuré |
| <hr>                         |     <hr>      |    <hr>     | <hr>                              |
| USAGE FUTUR                  |               |             |                                   |
| <hr>                         |     <hr>      |    <hr>     | <hr>                              |
| Processus                    |     \|––>     |    \|––>    | Champ libre. A définir            |
| <hr>                         |     <hr>      |    <hr>     | <hr>                              |
| `ESS` : Lieu de RDV souhaité |     \|––>     |    \|––>    |                                   |
| `EAD` : Données de connexion |               |  \|&lt;––   |                                   |

