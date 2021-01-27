---
tags: [Data]
---

# Glossaire

```
cover                     protection
building cover            protection des biens immobiliers
contents cover            protection des biens mobiliers

damage                    dommage
buildingsDamages          dommages immobiliers
    buildingDamage        dommage immobilier
contentsDamages           dommages mobiliers
    contentDamage         dommage mobilier

belongings                possessions, biens
property                  propriété, biens, immobilier

burglary                  cambriolage
water damage              dégât des eaux
lightning                 foudre
flood                     innondation
```

| Anglais              | Français                         |
| -------------------- | -------------------------------- |
| cover                | protection                       |
| building cover       | protection des biens immobiliers |
| contents cover       | protection des biens mobiliers   |
|                      |                                  |
| **DOMMAGES**         |                                  |
| damage               | dommage                          |
| **buildingsDamages** | **dommages immobiliers**         |
| _›› buildingDamage_  | _dommage immobilier_             |
| **contentsDamages**  | **dommages mobiliers**           |
| _›› contentDamage_   | _dommage mobilier_               |
|                      |                                  |
| belongings           | possessions, biens               |
| property             | propriété, biens, immobilier     |
|                      |                                  |
| **SINISTRES**        |                                  |
| burglary             | cambriolage                      |
| water damage         | dégât des eaux                   |
| lightning            | foudre                           |
| flood                | innondation                      |
|                      |                                  |

# Echanges

## Prendre un RDV

### Flux

1. --> Demande de créneaux horaires disponibles
2. <-- Liste de créneaux
3. --> Réservation d'un créneau

### Endpoints

#### `  POST  ` /availabilities
  - Body
    - Claim Resume

#### `  POST  ` /appointments
  - Body
    - Timeslot
    - Claim Data

## Modifier l'horaire d'un rendez-vous

### Flux

1. --> Demander des créneaux horaires disponibles
   - Préciser qu'il s'agit d'un rdv existant
   - Donner l'identifiant du rdv
2. <-- Liste de créneaux
3. --> Réservation d'un créneau

### Endpoints

#### `  GET  ` /appointments
  - _parameters_
    - datefrom
    - dateto
    - sinisterType

#### `  PUT  ` /appointments/**{id}**/schedule
#### `  PUT  ` /appointments/**{id}**/contact

## Modifier les coordonnées du rdv

L'assuré pourrait demander à modifier le rendez-vous
* à une autre adresse
* une autre personne (identité, coordonnées)

### Endpoints

- `  PUT  ` /appointments/**{id}**

## ??? Annuler un rdv ????

Pas d'annulation à l'initiative de l'assuré.
L'annulation pose le problème de l'ordre de mission que le partenaire aura reçu. Impossible d'annuler, sauf si ça vient de l'assurance.

## Lire les données d'un rendez-vous

### Endpoints

- `  GET  ` /appointments/**{id}**

## 

# Modèle de données

```
Claim
    - type
    - #Customer
    - #Sinister
        - type
        - housing
        - #Location
    - #Company
    - #Estimation
    - #SinisterDetails
    - #Documents

Damages
    - BuildingsDamages[]
        - BuildingDamage
            - Surface
            - Covering
        - BuildingDamage        # Dommage immobilier
            - Room
            - surface
                - size
                - covering

```

## Pesée de l'enjeu

    Estimation
        - movablesCount
        - roomsCount
        - cost

## Société d'assurance

    Company
        - name
        - acamCode
        - gtaCode

    Amount        # Montant (prix, valeur monétaire)
    Appointment   # Rendez-vous

---

## Déclaration de sinistre

```

Claim                       # Déclaration de sinistre
    - reference             # numéro de dossier Claims IA
    - #Customer             # Assuré (coordonnées)
    - #Sinister             # Sinistre
    - #Company              # Assureur
    - #Estimation           # Estimation Pesée: enjeu, nb pièces, nb biens
        - movablesCount
        - roomsCount
        - cost
    - #Qualification          # Données de qualification (tiers, recours,...)
    - #Damages              # Dommages immoboliers et mobiliers
    - #documents            # Pièces-jointes

```

## Qualification du sinistre

```
Qualification
    - origin                    # Origine de la cause
    - cause                     # Cause du sinistre
    - causeDetail               # Détail de la cause
    - #QualificationComplement  # Informations complémentaires de Claims IA
```

## Qualification Claims IA

```
QualificationComplement
    - thirdParty                # tiers impliqué (o/n)
    - responsability            # 'insured', 'none'
    - remedy                    # recours possible (o/n)
    - recourse                  # action en remboursement (o/n)
```

## Sinistre

```
Sinister                    # Définition du sinistre
    - type                  # Type de sinistre (DDE, DE, ...)
    - housingType           # Type d'habitation
    - #Location             # Lieu du sinistre (? PostalAddress ?)
```

---

## Dommages

    Damages
        - buildingsDamages [      # Liste de dommages immobiliers
            - #BuildingDamage
        ]
        - contentsDomages [       # Liste de dommages mobiliers
            - #ContentDamage
        ]

### Dommage immobilier

    BuildingDamage
        - room                    # Code de la pièce (Sinapps)
        - size                    # Superficie en m2
        - surfaces [              # Liste des surfaces endommagées
            #Surface
        ]
        - pictures[]              # Liste de photos

#### Surface

    Surface                       # Surface d'une pièce endommagée
        - name                    # Code type de surface
        - size                    # superficie en m2
        - condition               # Etat général (neuf, état d'usage, ancien)
        - covering                # Revêtement (peinture, papier peint,…)

---

### Dommage mobilier

    ContentDamage                 # Dommage mobilier
        - name                    # Nom libre
        - description
        - brandAndModel           # Marque et modèle
        - category                #
        - #Age                    # Age du bien
        - buyingPrice             # Prix d'achat
        - marketPrice             # Prix de marché
        - invoice                 # Lien vers le document
        - pictures[]              # tableau de liens vers les photos

#### Age d'un bien

    Age
        - value
        - unit

---

---

## Demande de créneau horaire

### Données de la requête

#### Requête version compacte

    AvailabilityRequest
        - #Claim
        - expertiseType           # Code Sinapps
        - sinisterType            # Code Sinapps
        - sinisterDate            # Date du sinistre
        - dateRange
            - start
            - end
        - desiredGranularity      # Précision du créneau: 'hour', 'halfday', 'day'

#### Requête version initiale

    AvailabilityRequest
        - #Location
        - #Company
        - #Estimation
        - expertiseType           # Code DARVA ou Sinapps
        - sinisterType            # Code DARVA ou Sinapps
        - sinisterDate            # Date du sinistre
        - dateRange
            - start
            - end
        - desiredGranularity      # Précision du créneau: 'hour', 'halfday', 'day'

### Réponse

La réponse est une liste de créneaux horaires

    {
        duration                  # durée moyenne estimée du rendez-vous
        timeSlots [               # Liste de créneaux horaires
            #TimeSlot
        ]
    }

## Créneau horaire disponible

    TimeSlot
      - uid                       # identifiant unique
      - startTime                 # Date et heure de début
      - endTime                   # Date et heur de fin
      - location/place            # lieu de rendez-vous. Si omis, c'est le lieu de la demande ou le lieu du sinistre
