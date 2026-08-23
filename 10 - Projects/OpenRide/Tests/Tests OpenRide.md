---
type: tests
project: OpenRide
---

# Tests OpenRide

## Objectif

Conserver une base de tests reproductible pour les composants critiques et les scénarios de navigation.

## Couverture connue

Le projet dispose de tests unitaires sur plusieurs briques, notamment :

- caméra cartographique ;
- formats ORMap ;
- installation de régions ;
- MBTiles/MVT ;
- style cartographique ;
- sélection cartographique ;
- graphe de routage.

## Tests Android

Les scénarios Android doivent pouvoir être reproduits sur émulateur afin de limiter la dépendance à un appareil physique.

## Direction souhaitée

Automatiser autant que possible :

1. construction ;
2. installation ;
3. chargement des données ;
4. activation du GPS simulé ;
5. lancement d'un itinéraire ;
6. capture de logs et, si utile, vidéo du [[Drive Mode]].

## Règle

Les résultats de test importants doivent être liés aux changements techniques qui les ont motivés.
