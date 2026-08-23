---
type: decision
project: OpenRide
status: accepted
---

# ADR - Roadbook secondaire

## Contexte

OpenRide peut proposer une expérience de type roadbook pour certains usages moto et trail, mais ce mode ne doit pas remplacer la navigation cartographique générale.

## Décision

Le roadbook est conservé comme option secondaire. L'interface et le flux de navigation par défaut restent centrés sur la carte.

## Raisons

- la carte est plus polyvalente pour la navigation quotidienne ;
- le roadbook répond à un besoin spécifique plutôt qu'universel ;
- maintenir une expérience principale claire évite de complexifier l'interface ;
- le mode roadbook peut évoluer indépendamment.

## Conséquences

Les choix UX du [[Drive Mode]] doivent être optimisés en priorité pour la navigation cartographique classique.
