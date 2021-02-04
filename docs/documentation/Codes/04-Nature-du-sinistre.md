---
tags: [Sinapps, documentation]
---

# Nature du sinistre

La nature d'un sinistre est représentée par un trio de valeurs **NATURE / CAUSE / DETAIL**

Selon les cas, les champs Cause ou Détail peuvent être vides.

<!--
type: tab
title: BDG
-->

## Bris de glace

| **Nature**      | Cause           | Détail |
| --------------- | --------------- | ------ |
| **BrisDeGlace** | ---             | ---    |
| **BrisDeGlace** | **Autre**       | ---    |
| BrisDeGlace     | Accidentel      | ---    |
| BrisDeGlace     | ViceEtMalfacon  | ---    |
| BrisDeGlace     | Vandalisme      | ---    |
| BrisDeGlace     | ForceDeLaNature | ---    |
| BrisDeGlace     | CauseInconnue   | ---    |

<!--
type: tab
title: BDM
-->

## Bris de machine

| Nature        | Cause             | Détail |
| ------------- | ----------------- | ------ |
| BrisDeMachine | Divers            | ---    |
| BrisDeMachine | DommageElectrique | ---    |
| BrisDeMachine | Chute             | ---    |
| BrisDeMachine | Interne           | ---    |
| BrisDeMachine | Externe           | ---    |

<!--
type: tab
title: CATNAT
-->

## Catastrophe naturelle

| Nature                   | Cause                        | Détail                        |
| ------------------------ | ---------------------------- | ----------------------------- |
| **CatastropheNaturelle** | ---                          | ---                           |
| CatastropheNaturelle     | Autre                        | ---                           |
| CatastropheNaturelle     | Avalanche                    | ---                           |
| CatastropheNaturelle     | ChocMecaniqueDesVagues       | ---                           |
| CatastropheNaturelle     | Cyclone                      | ---                           |
| CatastropheNaturelle     | EffondrementDeTerrain        | ---                           |
| CatastropheNaturelle     | EruptionVolcanique           | ---                           |
| CatastropheNaturelle     | ForceDeLaNature              | ---                           |
| CatastropheNaturelle     | Foudre                       | ---                           |
| CatastropheNaturelle     | GlissementMouvementDeTerrain | ---                           |
| <hr>                     | <hr>                         | <hr>                          |
| **CatastropheNaturelle** | **Inondation**               | **DebordementCoursDEau**      |
| **CatastropheNaturelle** | **Inondation**               | **CouleeDeBoue**              |
| **CatastropheNaturelle** | **Inondation**               | **RemonteeDeNappePhreatique** |
| **CatastropheNaturelle** | **Inondation**               | **EauxRuisselement**          |
| <hr>                     | <hr>                         | <hr>                          |
| CatastropheNaturelle     | RazDeMaree                   | ---                           |
| **CatastropheNaturelle** | **Secheresse**               | ---                           |
| CatastropheNaturelle     | Seisme                       | ---                           |
| <hr>                     | <hr>                         | <hr>                          |
| EvtNaturel               | Inondation                   | ---                           |
| <hr>                     | <hr>                         | <hr>                          |
| TempeteNeigeGrele        | Autre                        | ---                           |
| **TempeteNeigeGrele**    | **Grele**                    | ---                           |
| **TempeteNeigeGrele**    | **PoidsDeLaNeigeGlace**      | ---                           |
| **TempeteNeigeGrele**    | **TempeteOuragan**           | **ActionDirecteDuVent**       |

<!--
type: tab
title: CATTEC
-->

## Catastrophe technologique

| Nature                   | Cause             | Détail |
| ------------------------ | ----------------- | ------ |
| CatastropheTechnologique | IncendieExplosion | ---    |
| CatastropheTechnologique | ---               | ---    |

<!--
type: tab
title: CVT
-->

## Choc de véhicule terrestre

| Nature   | Cause                        | Détail |
| -------- | ---------------------------- | ------ |
| Choc     | Animal                       | ---    |
| Choc     | Autre                        | ---    |
| Choc     | ChuteDarbre                  | ---    |
| Choc     | ChuteDeConstruction          | ---    |
| Choc     | ObjetVolantAeronef           | ---    |
| Choc     | VehiculeAutre                | ---    |
| **Choc** | **VehiculeTerrestreAMoteur** | ---    |

<!--
type: tab
title: DEFREC
-->

## Défense recours

| Nature         | Cause             | Détail |
| -------------- | ----------------- | ------ |
| DefenseRecours | Defense           | ---    |
| DefenseRecours | RecoursNonSubroge | ---    |

<!--
type: tab
title: DDE
-->

## Dégât des eaux

| Nature            | Cause                   | Détail                                      |
| ----------------- | ----------------------- | ------------------------------------------- |
| **DegatsDesEaux** | ---                     | ---                                         |
| DegatsDesEaux     | AutresLiquides          | ---                                         |
| DegatsDesEaux     | Condensation            | DefautDUsage                                |
| DegatsDesEaux     | Condensation            | PanneVmc                                    |
| DegatsDesEaux     | Condensation            | ViceConstruction                            |
| DegatsDesEaux     | EffetDuGel              | ---                                         |
| DegatsDesEaux     | EnCours                 | ---                                         |
| DegatsDesEaux     | FaitIntentionnel        | ---                                         |
|                   |                         |                                             |
| **DegatsDesEaux** | **FuiteRupture**        | **AppareilAEffetDEauEtAccessoires**         |
| **DegatsDesEaux** | **FuiteRupture**        | **AppareilDeProductionDEauChaudeSanitaire** |
| DegatsDesEaux     | FuiteRupture            | Autre                                       |
| DegatsDesEaux     | FuiteRupture            | CanalisationAlimentationPriveeAccessible    |
| DegatsDesEaux     | FuiteRupture            | CanalisationAlimentationPriveeNonAccessible |
| **DegatsDesEaux** | **FuiteRupture**        | **CanalisationCollective**                  |
| **DegatsDesEaux** | **FuiteRupture**        | **CanalisationCollectiveNonAccessible**     |
| **DegatsDesEaux** | **FuiteRupture**        | **CanalisationEnterree**                    |
| DegatsDesEaux     | FuiteRupture            | CanalisationEvacuationPriveeAccessible      |
| DegatsDesEaux     | FuiteRupture            | CanalisationEvacuationPriveeNonAccessible   |
| **DegatsDesEaux** | **FuiteRupture**        | **CanalisationNonEnterree**                 |
| **DegatsDesEaux** | **FuiteRupture**        | **CheneauxGouttieres**                      |
| **DegatsDesEaux** | **FuiteRupture**        | **InstallationChauffageCollectif**          |
| **DegatsDesEaux** | **FuiteRupture**        | **InstallationChauffageIndividuel**         |
|                   |                         |                                             |
| DegatsDesEaux     | Gel                     | AppareilAEffetDEau                          |
| DegatsDesEaux     | Gel                     | AppareilInstallationEauCollective           |
| DegatsDesEaux     | Gel                     | AppareilInstallationEauPrivative            |
| DegatsDesEaux     | Gel                     | CanalisationCollectiveAccessible            |
| DegatsDesEaux     | Gel                     | CanalisationCollectiveNonAccessible         |
| DegatsDesEaux     | Gel                     | CanalisationEnterree                        |
| DegatsDesEaux     | Gel                     | CanalisationPriveeAccessible                |
| DegatsDesEaux     | Gel                     | CanalisationPriveeNonAccessible             |
| DegatsDesEaux     | Gel                     | CheneauxGouttieres                          |
|                   |                         |                                             |
| DegatsDesEaux     | Indeterminee            | ---                                         |
|                   |                         |                                             |
| **DegatsDesEaux** | **Infiltration**        | **CarrelageFaience**                        |
| DegatsDesEaux     | Infiltration            | **ConduiteDeChemineeVentialtion**           |
| DegatsDesEaux     | Infiltration            | **Couverture**                              |
| DegatsDesEaux     | Infiltration            | **EtancheiteTerrasse**                      |
| DegatsDesEaux     | Infiltration            | **Facade**                                  |
| DegatsDesEaux     | Infiltration            | **JointPeripherique**                       |
| DegatsDesEaux     | Infiltration            | **MenuiserieFermeeOuNon**                   |
| DegatsDesEaux     | Infiltration            | MenuiserieOuverte                           |
| DegatsDesEaux     | Infiltration            | MurEnterre                                  |
| DegatsDesEaux     | Infiltration            | OuvertureConduitAbsenceToitureToitureBachee |
|                   |                         |                                             |
| DegatsDesEaux     | Inondation              | DebordementDeCoursDEau                      |
| DegatsDesEaux     | Inondation              | Ocean                                       |
| DegatsDesEaux     | Inondation              | RemonteeDeNappePhreatique                   |
| DegatsDesEaux     | Inondation              | RuissellementEauHorsReaseau                 |
|                   |                         |                                             |
| DegatsDesEaux     | InterventionHumaine     | ---                                         |
| DegatsDesEaux     | PluieOuNeige            | ---                                         |
| DegatsDesEaux     | PorositeCapillarite     | ---                                         |
|                   |                         |                                             |
| DegatsDesEaux     | RefoulementEngorgement  | **CanalisationCollective**                  |
| DegatsDesEaux     | RefoulementEngorgement  | **CanalisationPrivative**                   |
| DegatsDesEaux     | RefoulementEngorgement  | **EgoutOrganeCollecteEauCommunale**         |
|                   |                         |                                             |
| DegatsDesEaux     | RenversementDebordement | **AppareilAEffetDEau**                      |
| DegatsDesEaux     | RenversementDebordement | **CheneauxGouttieres**                      |
| DegatsDesEaux     | RenversementDebordement | **DeRecipent**                              |

<!--
type: tab
title: DIV
-->

## Divers

| Nature | Cause                            | Détail |
| ------ | -------------------------------- | ------ |
| Divers | ActionDeChasse                   | ---    |
| Divers | Attentat                         | ---    |
| Divers | Autre                            | ---    |
| Divers | BrisDeteriorationPanne           | ---    |
| Divers | CanalisationsExterieures         | ---    |
| Divers | DeteriorationImmeubleParVehicule | ---    |
| Divers | Emeute                           | ---    |
| Divers | EvenementImmobilier              | ---    |
| Divers | ExtraScolaire                    | ---    |
| Divers | FaitIntentionnel                 | ---    |
| Divers | Fonctionnement                   | ---    |
| Divers | HorsActionDeChasse               | ---    |
| Divers | Mrh                              | ---    |
| Divers | OrigineCriminelle                | ---    |
| Divers | PanneElectromenager              | ---    |
| Divers | Perte                            | ---    |
| Divers | PerteEauInterieure               | ---    |
| Divers | Pollution                        | ---    |
| Divers | PollutionGraduelle               | ---    |
| Divers | Pro                              | ---    |
| Divers | Scolaire                         | ---    |
| Divers | Vandalisme                       | ---    |
| Divers | ViceOuMalfacon                   | ---    |

<!--
type: tab
title: DMMT
-->

## DMMT

| Nature | Cause                                        | Détail |
| ------ | -------------------------------------------- | ------ |
| DMMT   | Accident                                     | ---    |
| DMMT   | Agression                                    | ---    |
| DMMT   | Divers                                       | ---    |
| DMMT   | Incendie                                     | ---    |
| DMMT   | TerrorismeAttentat                           | ---    |
| DMMT   | VandalismeEmeuteMouvementPopulaireTerrorisme | ---    |
| DMMT   | VolDeMarchandises                            | ---    |
| DMMT   | VolDuVehicule                                | ---    |

<!--
type: tab
title: BIENS
-->

## Dommages aux biens

| Nature           | Cause                                        | Détail |
| ---------------- | -------------------------------------------- | ------ |
| DommagesAuxBiens | AppareilMedical                              | ---    |
| DommagesAuxBiens | InstrumentsDeMusique                         | ---    |
| DommagesAuxBiens | PerteContenuCongelateurCellulesRefrigerantes | ---    |

<!--
type: tab
title: DE
-->

## Dommages électriques

| Nature                  | Cause                              | Détail |
| ----------------------- | ---------------------------------- | ------ |
| **DommagesElectriques** | ---                                | ---    |
| DommagesElectriques     | Autre                              | ---    |
| DommagesElectriques     | ExplosionImplosion                 | ---    |
| DommagesElectriques     | FaitIntentionnel                   | ---    |
| **DommagesElectriques** | **FoudreElectriciteAtmospherique** | ---    |
| **DommagesElectriques** | **IncidentSurtensionSurLeReseau**  | ---    |
| **DommagesElectriques** | **Surtension**                     | ---    |
| DommagesElectriques     | ViceOuMalfacon                     | ---    |

<!--
type: tab
title: EXPL
-->

## Explosion

| Nature    | Cause                                        | Détail    |
| --------- | -------------------------------------------- | --------- |
| Explosion | ---                                          | ---       |
| Explosion | ActeCriminel                                 | ---       |
| Explosion | AppareilAutre                                | ---       |
| Explosion | AppareilChauffage                            | ---       |
| Explosion | AppareilElectromenager                       | ---       |
| Explosion | Autre                                        | ---       |
| Explosion | FoyerOuvertFerme                             | ---       |
| Explosion | Indeterminee                                 | ---       |
| Explosion | InstallationElectrique                       | ---       |
| Explosion | InstallationGaz                              | Privative |
| Explosion | VandalismeEmeuteMouvementPopulaireTerrorisme | ---       |

<!--
type: tab
title: INC
-->

## Incendie

| Nature       | Cause                                        | Détail                                     |
| ------------ | -------------------------------------------- | ------------------------------------------ |
| **Incendie** | ---                                          | ---                                        |
| Incendie     | Indeterminee                                 | ---                                        |
| Incendie     | FaitAccidentelDunTiers                       | ---                                        |
| Incendie     | AppareilChauffage                            | FoyerFerme                                 |
| Incendie     | ExplosionImplosion                           | InstallationGaz                            |
| Incendie     | Foudre                                       | ActionDeLElectriciteAtmospherique          |
| Incendie     | Electrique                                   | ActionDeLElectriciteCanalisee              |
| Incendie     | Electrique                                   | CanalisationElectriqueBatiment             |
| Incendie     | AppareilChauffage                            | FoyerOuvert                                |
| Incendie     | AppareilChauffage                            | Autre                                      |
| Incendie     | AccessoireDomestique                         | ---                                        |
| Incendie     | Electrique                                   | AppareilElectromenagerInstallationAmovible |
| Incendie     | Criminel                                     | ---                                        |
| Incendie     | FeuDeForetEcobuage                           | ---                                        |
| Incendie     | AccidentDeMenage                             | Cuisine                                    |
| Incendie     | ForceDeLaNature                              | ---                                        |
| Incendie     | AccidentDeMenage                             | Autre                                      |
| Incendie     | Foudre                                       | ChuteDirecte                               |
| Incendie     | VandalismeEmeuteMouvementPopulaireTerrorisme | ---                                        |
| Incendie     | ExplosionImplosion                           | Appareil                                   |
| Incendie     | Vehicule                                     | AerienChuteDObjetDeLEspace                 |
| Incendie     | FumeeSansIncendie                            | ---                                        |
| Incendie     | Autre                                        | ---                                        |
| Incendie     | FuiteRupture                                 | CanalisationAlimentationPriveeAccessible   |

<!--
type: tab
title: VOL
-->

## Vol

| Nature | Cause                                        | Détail                 |
| ------ | -------------------------------------------- | ---------------------- |
| Vol    | SansEffraction                               | Indetermine            |
| Vol    | SansEffraction                               | UsageFaussesCles       |
| Vol    | SansEffraction                               | Escalade               |
| Vol    | SansEffraction                               | PenetrationClandestine |
| Vol    | SansEffraction                               | AvecViolence           |
| Vol    | SansEffraction                               | Autre                  |
| Vol    | SansEffraction                               | Ruse                   |
|        |                                              |                        |
| Vol    | AvecEffraction                               | SansVol                |
| Vol    | AvecEffraction                               | VolEtVandalisme        |
| Vol    | AvecEffraction                               | AvecVol                |
|        |                                              |                        |
| Vol    | ALExterieur                                  | ---                    |
| Vol    | Indeterminee                                 | ---                    |
| Vol    | DeCles                                       | ---                    |
| Vol    | Alarrache                                    | ---                    |
| Vol    | VandalismeSurSerrure                         | ---                    |
| Vol    | VandalismeEmeuteMouvementPopulaireTerrorisme | ---                    |
| Vol    | Vandalisme                                   | ---                    |
| Vol    | Autre                                        | ---                    |

| Nature             | Cause  | Détail |
| ------------------ | ------ | ------ |
| FoudreSansIncendie | Divers | ---    |

<!--
type: tab
title: Autres
-->

## Autres

| **Nature**         | Cause | Détail |
| ------------------ | ----- | ------ |
| **AutresDommages** | ---   | ---    |

<!-- type: tab-end -->
