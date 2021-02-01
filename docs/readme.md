# Introduction

**Claims MRH** est une application de selfcare permettant à un assuré de déclarer un sinistre en ligne.
A l'issue de sa déclaration, l'assuré pourra être redirigé vers un expert ou un artisan selon la nature et la gravité du problème.

L'API RDV de Claims IA permet la prise de rendez-vous expertise ou REN depuis l'application Claims MRH. A ce titre, elle doit être implémentée par les sociétés qui souhaitent fournir ce service de prise de rendez-vous.

La prise de rendez-vous s'effectue en 3 temps:

- **Etape 1** : Claims IA fait de demande de créneaux disponibles pour le rendez-vous.
  - La demande est accompagnée d'informations sur la déclaration de sinistre
  - Le partenaire fournit en retour une liste de créneaux
- **Etape 2** : L'utilisateur choisit un des créneaux horaires proposés
- **Etape 3** : Claims IA réserve un créneau, qui devient affecté au rendez-vous
  - Le partenaire fournit en retour les informations sur le rendez-vous

![Flux normal](../assets/images/flux2.png "Flux normal")

**Etape 4** : En différé, le partenaire peut récupérer
- les informations détaillées sur le dossier de déclaration
- les documents fournis par l'assuré


L'API intègre également d'autres méthodes (optionnelles en v1) pour
- Modifier certaines informations du rendez-vous
- Annuler et replanifier un rendez-vous

L'API respecte le standard REST et utilise le protocole HTTP. Les messages échangés sont au format JSON.


Une clé est nécessaire pour utiliser l'API. Cette clé doit être fournie par la société qui implémente l'API.
