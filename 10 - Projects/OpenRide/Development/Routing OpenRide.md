---
type: technical-note
project: OpenRide
topic: routing
---

# Routing OpenRide

## Objectif

Calculer localement des itinéraires moto et des boucles sans dépendre d'un service externe.

## Données

Le moteur utilise un graphe généré à partir des données OpenStreetMap préparées pour OpenRide.

## Éléments déjà présents

- graphe de routage offline ;
- index spatiaux pour accélérer la recherche des nœuds et segments ;
- génération de boucles moto ;
- scoring des boucles selon distance, répétition et qualité du résultat.

## Contraintes

- temps de calcul compatible avec un usage mobile ;
- comportement déterministe et testable ;
- stockage compact ;
- cohérence entre carte affichée et réseau routable.

## Liens

- [[Architecture OpenRide]]
- [[Tests OpenRide]]
- [[Drive Mode]]
