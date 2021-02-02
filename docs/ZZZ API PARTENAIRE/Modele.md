---
tags: [Data]
---

# Glossaire

```
cover               protection
building cover      protection des biens immobiliers
contents cover      protection des biens mobiliers

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

| Français                         | Anglais            |
| -------------------------------- | ------------------ |
| **PROTECTION**                   | **COVER**          |
| protection des biens immobiliers | building cover     |
| protection des biens mobiliers   | contents cover     |
| ———————————————                  | —————————————      |
| **DOMMAGES**                     | **DAMAGES**        |
| dommages immobiliers             | buildingsDamages   |
|     dommage immobilier           |     buildingDamage |
| dommages mobiliers               | contentsDamages    |
|     dommage mobilier             |     contentDamage  |
| ———————————————                  | —————————————      |
| possessions, biens               | belongings         |
| propriété, biens, immobilier     | property           |
| ———————————————                  | —————————————      |
| **SINISTRES**                    | **SINISTERS**      |
| cambriolage                      | burglary           |
| dégât des eaux                   | water damage       |
| foudre                           | lightning          |
| innondation                      | flood              |

# Modèle de données

## Demande d'intervention

Données envoyées aux prestataire lors de la demande de créneaux horaires
```
MissionRequest              Demande d'intervention
  type                      Type de prestation (REN, EAD, ESS, ...)
  claim                     Déclaration de sinistre (simplifiée)
  dateFrom                  Début de période d'intervention
  dateTo                    Fin de période d'intervention
```

## Déclaration de sinistre

2 versions sont prévues:
- Une version résumée envoyée lors de la première requête. Elle doit contenir le minimum d'informations necessaires pour pouvoir sélectionner des créneaux dans l'agenda.
- Une version complète, envoyée une fois que l'assuré a choisi un créneau horaire, et que le rendez-vous est booké.

### Déclaration résumée

#### Expert:

- Type d'expertise (EAD, ESS, ...)
- Informations sur l'assurance et le contrat
  - Compagnie
  - Réf. produit (contrat assureur)
- Garantie en jeu (DDE, DE, TNG, SECH, VOL)
- Adresse du risque
- Qualification du sinistre, selon la codification Sinapps (origine, cause, détail)
- Des données d'analyse de ClaimsIA (tiers, recours,...)
- La pesée de l'enjeu (ou chiffrage Claims pour les sinistres qui n'ont pas de pesée)

#### RENeur:

- Type de mission
- Informations sur l'assurance et le contrat
  - Compagnie
  - Réf. produit (contrat assureur)
- Garantie en jeu (DDE, DE, TNG, SECH, VOL)
- Adresse du risque
- Qualification du sinistre, selon la codification Sinapps (origine, cause, détail)


```
Claim                       Déclaration
  - type                    Type de pres
  #Customer                 Données assuré
  #Sinister
    - type
    - housing
    #Location
  #Company
  #Estimation
  #SinisterDetails
  #Documents
```

### Déclaration complète

```
```



```
Claim                       Déclaration
  - type                    Type de pres
  #Customer                 Données assuré
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
    BuildingDamage          # Dommage immobilier
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
