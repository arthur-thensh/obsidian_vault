---
type: technical-note
project: OpenRide
platform: Android
---

# Android OpenRide

## État

Une version Android fonctionnelle existe et a déjà été testée avec les données de carte, routage et recherche copiées dans l'espace privé de l'application.

## Paquet

`com.arthurthion.openride`

## Pipeline de développement

Le projet dispose de scripts pour vérifier l'environnement Android, compiler l'application et pousser les données nécessaires sur l'appareil ou l'émulateur.

## Données applicatives

Les jeux de données sont conservés sous l'espace privé de l'application, notamment pour :

- les cartes ;
- le routage ;
- la recherche ;
- les téléchargements.

## Points d'attention

- Scoped Storage impose d'utiliser l'espace privé de l'application pour certains fichiers.
- Les performances de rendu doivent être vérifiées sur matériel mobile.
- Les tests sur émulateur sont utiles pour automatiser les scénarios de navigation.

## Liens

- [[Tests OpenRide]]
- [[Drive Mode]]
- [[Cartographie OpenRide]]
