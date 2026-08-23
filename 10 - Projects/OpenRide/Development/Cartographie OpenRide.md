---
type: technical-note
project: OpenRide
topic: map
---

# Cartographie OpenRide

## Objectif

Afficher une carte offline exploitable en navigation moto avec un coût de rendu compatible avec les appareils mobiles.

## Données

Le pipeline cartographique est construit à partir de données OpenStreetMap préparées en formats internes OpenRide.

## Points déjà travaillés

- rendu des routes et chemins ;
- bâtiments ;
- surfaces ;
- eau et continuité des cours d'eau ;
- préparation ORMap ;
- index spatiaux ;
- réduction du coût de rendu.

## Contraintes

La lisibilité des routes et chemins est prioritaire. Les bâtiments et autres éléments de contexte ne doivent pas dominer visuellement la carte ni pénaliser fortement les performances.

## Sujets à poursuivre

- continuité visuelle des surfaces et rivières ;
- simplification des bâtiments ;
- pyramides de tuiles et niveaux de détail ;
- rendu optimisé pour [[Drive Mode]].
