---
tags: [Data]
---

# Glossaire

```
cover               protection
building cover      protection des biens immobiliers
contents cover      protection des biens mobiliers

damage              dommage
buildingsDamages    dommages immobiliers
  buildingDamage    dommage immobilier
contentsDamages     dommages mobiliers
  contentDamage     dommage mobilier

belongings          possessions, biens
property            propriété, biens, immobilier

burglary            cambriolage
water damage        dégât des eaux
lightning           foudre
flood               innondation
```

| Anglais              | Français                         |
| -------------------- | -------------------------------- |
| cover                | protection                       |
| building cover       | protection des biens immobiliers |
| contents cover       | protection des biens mobiliers   |
| …………………………………………………… | ……………………………………………………             |
| damage               | dommage                          |
| **buildingsDamages** | **dommages immobiliers**         |
| ›› buildingDamage    | dommage immobilier               |
| **contentsDamages**  | **dommages mobiliers**           |
| ›› contentDamage     | dommage mobilier                 |
| …………………………………………………… | ……………………………………………………             |
| **belongings**       | possessions, biens               |
| **property**         | propriété, biens, immobilier     |
| …………………………………………………… | ……………………………………………………             |
| **SINISTRES**        |                                  |
| ———————————————      | ————————————————                 |
| **burglary**         | cambriolage                      |
| **water damage**     | dégât des eaux                   |
| **lightning**        | foudre                           |
| **flood**            | innondation                      |

# Modèle de données

```
Claim
  - type
  #Customer
  #Sinister
    - type
    - housing
    #Location
  #Company
  #Estimation
  #SinisterDetails
  #Documents

Damages
  BuildingsDamages[]
    BuildingDamage
      - Surface
      - Covering
    BuildingDamage				# Dommage immobilier
    	Room
    		surface
          - size
    			- covering
        Covering

```

## Pesée de l'enjeu

```
Estimation
  - movablesCount
  - roomsCount
  - cost
```

## Société d'assurance

```
Company
  - name
  - acamCode
  - gtaCode
```

```
Amount # Montant (prix, valeur monétaire)
Appointment # Rendez-vous
```

---

## Déclaration de sinistre

```
Claim                 # Déclaration de sinistre
  #Customer           # Assuré (coordonnées)
  #Sinister           # Sinistre
  #Company            # Assureur
  #Estimation         # Estimation - Pesée: enjeu, nb pièces, nb biens - movablesCount - roomsCount - cost
  type                # DDE, DE
  #SinisterDetails    # Données de qualification (tiers, recours,...)
  #documents
```

## Sinistre

```
Sinister          # Définition du sinistre
  type            # Type de sinistre
  housingType     # Type d'habitation
  #Location       # Lieu du sinistre (? PostalAddress ?)
```

---

## Dommages

```
Damages
  buildingsDamages [    # Liste de dommages immobiliers
    #BuildingDamage
  ]
  contentsDomages [     # Liste de dommages mobiliers
    #ContentDamage
  ]
```

### Dommage immobilier

```
BuildingDamage
  - room              # Code de la pièce (Sinapps)
  - size              # Superficie en m2
  - surfaces [        # Liste des surfaces endommagées
      #Surface
  ]
  - pictures[]        # Liste de photos
```

#### Surface

```
Surface         # Surface d'une pièce endommagée
  - name        # Code type de surface
  - size        # superficie en m2
  - condition   # Etat général (neuf, état d'usage, ancien)
  - covering    # Revêtement (peinture, papier peint,…)
```

---

### Dommage mobilier

```
ContentDamage     # Dommage mobilier
  - name          # Nom libre
  - description
  - brandAndModel # Marque et modèle
  - category      #
  - #Age          # Age du bien
  - buyingPrice   # Prix d'achat
  - marketPrice   # Prix de marché
  - invoice       # Lien vers le document
  - pictures[]    # tableau de liens vers les photos
```

#### Age d'un bien

```
Age
  - value
  - unit
```

---

## Demande de créneau horaire

### Données de la requête

#### Requête version compacte

```
AvailabilityRequest
- #Claim
- expertiseType			_# Code Sinapps_
- sinisterType			_# Code Sinapps_
- sinisterDate			_# Date du sinistre_
- dateRange
  - start
  - end
- desiredGranularity		_# Précision du créneau: 'hour', 'halfday', 'day'_
```

#### Requête version initiale

```
AvailabilityRequest
  #Location
  #Company
  #Estimation
  expertiseType			# Code DARVA ou Sinapps
  sinisterType			# Code DARVA ou Sinapps
  sinisterDate			# Date du sinistre
  dateRange
    start
    end
  desiredGranularity		# Précision du créneau: 'hour', 'halfday', 'day'
```

### Réponse

La réponse est une liste de créneaux horaires

```
{
	duration				# durée moyenne estimée du rendez-vous
	timeSlots [				# Liste de créneaux horaires
		#TimeSlot
	]
}
```

## Créneau horaire disponible

```
TimeSlot
	uid             # identifiant unique
	startTime       # Date et heure de début
	endTime         # Date et heur de fin
	location/place  # lieu de rendez-vous. Si omis, c'est le lieu de la demande ou le lieu du sinistre
```
