---
type: architecture
project: OpenRide
topic: data-pipeline
last_verified: 2026-08-23
---

# Pipeline de données OpenRide

## Source unique

Une région OpenRide est préparée à partir d'un fichier :

```text
<region>-latest.osm.pbf
```

Ce PBF est la matière première. Le routage, la recherche et les cartes sont construits localement à partir de lui.

## Artefacts produits

```text
.osm.pbf
   │
   ├──> .orgraph
   │      routage + index spatiaux
   │
   ├──> .orplaces.sqlite
   │      recherche hors ligne
   │
   ├──> .ormap
   │      carte stable v8
   │
   └──> .ormap11
          carte détaillée v11
```

## `.orgraph`

Contient le graphe routier utilisé par [[Routing OpenRide]].

Le pipeline extrait les voies utiles à la moto, construit les arcs dirigés et prépare les structures nécessaires au snapping et aux recherches spatiales rapides.

## `.orplaces.sqlite`

Index SQLite des lieux et points utiles à la recherche hors ligne.

Objectif : ne dépendre d'aucun service distant pour rechercher une ville, un village ou un POI une fois la région installée.

## `.ormap` v8

Format cartographique stable d'OpenRide.

Il contient notamment :

- réseau routier avec niveaux de visibilité ;
- pistes et chemins utilisables ;
- waterways ;
- surfaces d'eau ;
- zones bâties généralisées ;
- forêts principales ;
- labels ;
- plusieurs niveaux de détail.

Voir [[Cartographie OpenRide]].

## `.ormap11` v11

Sibling détaillé de `.ormap`, basé sur un TilePyramid avec surfaces, bâtiments et overlays détaillés.

Il est conçu pour compléter la carte stable, sans rendre les anciennes installations `.ormap` incompatibles.

## Préparation sur Android

Le flux normal pour l'utilisateur final est :

```text
Téléchargement PBF
      ↓
.orgraph
      ↓
.orplaces.sqlite
      ↓
.ormap v8
      ↓
.ormap11 v11
      ↓
Finalisation de la région
```

Le traitement est effectué sur un worker afin de ne pas bloquer l'interface.

Le PBF n'est supprimé qu'après succès complet. Si la génération détaillée échoue alors que les trois premiers artefacts sont valides, le fichier source peut être conservé afin de reprendre la dernière étape.

## Préparation sur macOS

Workflow de développement :

```sh
./scripts/download_routing_data.sh
./scripts/prepare_region.sh
```

`prepare_region.sh` orchestre les préparations du graphe, de la recherche et des deux cartes.

## Principe architectural

> [!important]
> Aucun serveur OpenRide n'est nécessaire pour le routage, la recherche ou la génération cartographique d'une région déjà téléchargée. Le téléchargement du PBF nécessite Internet ; les transformations et l'utilisation quotidienne sont locales.
