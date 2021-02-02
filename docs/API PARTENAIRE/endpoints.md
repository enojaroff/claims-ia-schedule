# Prendre un RDV

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

# Modifier l'horaire d'un rendez-vous

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

# Modifier les coordonnées du rdv

L'assuré pourrait demander à modifier le rendez-vous
* à une autre adresse
* une autre personne (identité, coordonnées)

### Endpoints

- `  PUT  ` /appointments/**{id}**

# ??? Annuler un rdv ????

Pas d'annulation à l'initiative de l'assuré.
L'annulation pose le problème de l'ordre de mission que le partenaire aura reçu. Impossible d'annuler, sauf si ça vient de l'assurance.

# Lire les données d'un rendez-vous

### Endpoints

- `  GET  ` /appointments/**{id}**



