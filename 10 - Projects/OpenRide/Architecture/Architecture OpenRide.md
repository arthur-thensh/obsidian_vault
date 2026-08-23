---
type: architecture
project: OpenRide
---

# Architecture OpenRide

## Vue générale

OpenRide est organisé autour de plusieurs sous-systèmes :

1. import et préparation des données OpenStreetMap ;
2. stockage cartographique offline ;
3. graphe de routage ;
4. index de recherche de lieux ;
5. génération d'itinéraires et de boucles ;
6. rendu cartographique ;
7. interface et navigation en conduite ;
8. intégration Android.

## Données offline

Le projet utilise plusieurs formats générés à partir des données OSM. La cartographie, le routage et la recherche sont séparés afin de permettre des traitements et optimisations spécifiques.

## Rendu

Le rendu doit rester suffisamment léger pour fonctionner correctement sur mobile. Les bâtiments, surfaces, cours d'eau, routes et autres overlays doivent donc être simplifiés ou structurés pour limiter le coût CPU et mémoire.

## Navigation

Le mode principal reste une navigation cartographique classique. Le [[Drive Mode]] doit privilégier la lisibilité en mouvement plutôt qu'une vue top-down trop éloignée.

## Liens

- [[Cartographie OpenRide]]
- [[Routing OpenRide]]
- [[Android OpenRide]]
- [[Décisions OpenRide]]
