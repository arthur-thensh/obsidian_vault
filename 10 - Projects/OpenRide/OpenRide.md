---
type: project
status: active
repository: arthur-thensh/openride
---

# OpenRide

## Objectif

Application de navigation moto multiplateforme centrée sur la navigation cartographique classique, avec fonctionnement offline et génération d'itinéraires adaptés à la moto.

## Principes du projet

- Données cartographiques et routage disponibles hors ligne.
- Traitements effectués localement autant que possible.
- Interface principale centrée sur la carte et la navigation.
- Le roadbook reste un mode secondaire et optionnel.
- Développement principalement en C avec CMake.

## État général

Le projet dispose déjà d'un pipeline cartographique, d'un moteur de routage, d'un index de recherche, d'un générateur de boucles moto et d'une application Android fonctionnelle.

## Sections

- [[Architecture OpenRide]]
- [[Android OpenRide]]
- [[Cartographie OpenRide]]
- [[Routing OpenRide]]
- [[Drive Mode]]
- [[Tests OpenRide]]
- [[Décisions OpenRide]]

## Travail en cours

- Améliorer l'expérience de navigation en conduite.
- Poursuivre l'intégration du pipeline ORMap détaillé.
- Réduire le coût de rendu sur mobile.
- Maintenir une procédure de test reproductible.

## Dépôt

GitHub : `arthur-thensh/openride`
