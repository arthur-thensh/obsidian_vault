---
type: decision
project: OpenRide
status: accepted
---

# ADR - Navigation offline

## Contexte

OpenRide doit fonctionner comme une application de navigation moto utilisable sans connexion réseau permanente.

## Décision

Les données nécessaires à la carte, au routage et à la recherche sont préparées et stockées localement. Le calcul d'itinéraire est effectué sur l'appareil.

## Raisons

- fonctionnement en zones mal couvertes ;
- indépendance vis-à-vis d'API externes ;
- maîtrise du comportement du routage ;
- meilleure confidentialité ;
- possibilité de construire des fonctions spécifiques à la moto.

## Conséquences

Le projet doit gérer lui-même l'import, les formats de données, le stockage, les mises à jour régionales et les performances de traitement sur mobile.
