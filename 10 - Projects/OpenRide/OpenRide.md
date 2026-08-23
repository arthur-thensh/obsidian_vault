---
type: project
status: active
repository: arthur-thensh/openride
version: v0.32.0
stack:
  - C17
  - SDL3
  - CMake
platforms:
  - macOS
  - Android
  - iOS-planned
last_verified: 2026-08-23
---

# OpenRide

## Objectif

OpenRide est une application de navigation moto **entièrement utilisable hors ligne**, écrite principalement en C17 avec SDL3. Le même cœur C doit servir macOS, Android puis iOS, les couches spécifiques aux plateformes restant aussi fines que possible.

Le mode principal reste une navigation cartographique classique. Le roadbook est une fonctionnalité secondaire et optionnelle.

## État actuel vérifié

Version annoncée par le dépôt : **v0.32.0**.

Fonctionnel aujourd'hui :

- carte OpenStreetMap hors ligne ;
- format stable `.ormap` v8 ;
- carte détaillée `.ormap11` v11 avec TilePyramid ;
- surfaces, zones bâties, eau et waterways vectoriels ;
- styles Road, Trail et Topo ;
- moteur de routage hors ligne ;
- profils Rapide, Balade et Trail ;
- index spatiaux des nœuds et segments ;
- snapping sur les segments routiers ;
- navigation turn-by-turn ;
- ronds-points et sorties ;
- suivi de progression et recalcul hors itinéraire ;
- GPS simulé sur macOS et GPS réel Android ;
- filtrage GPS ;
- Drive Mode avec orientation selon le cap et zoom automatique ;
- recherche locale ;
- favoris et historique ;
- import/export et enregistrement GPX ;
- génération de boucles moto ;
- préparation d'une région directement sur Android à partir d'un `.osm.pbf`.

## Architecture documentaire

- [[Architecture OpenRide]]
- [[Pipeline de données OpenRide]]
- [[Cartographie OpenRide]]
- [[Routing OpenRide]]
- [[Android OpenRide]]
- [[Drive Mode]]
- [[Tests OpenRide]]
- [[Workflow de développement OpenRide]]
- [[Décisions OpenRide]]

## Pipeline d'une région

```text
.osm.pbf
   ├──> .orgraph
   ├──> .orplaces.sqlite
   ├──> .ormap v8
   └──> .ormap11 v11
```

Le `.osm.pbf` est la source unique de préparation d'une région. Les données de carte, recherche et routage sont ensuite exploitées localement sans serveur OpenRide.

## Organisation principale du dépôt

```text
openride/
├── android/
├── data/
├── docs/
├── include/openride/
├── scripts/
├── src/
├── tests/
├── vendor/
├── CMakeLists.txt
└── README.md
```

## Travail actuel

Le dépôt indique que les travaux se concentrent principalement sur :

- l'expérience de navigation en conduite ;
- la lisibilité de l'interface ;
- la poursuite du rendu cartographique détaillé sans dégrader les performances mobiles.

## Dépôt

GitHub : `arthur-thensh/openride`

> [!note] Source de vérité
> Cette note est une synthèse. Pour l'état exact du code, le dépôt GitHub OpenRide reste la source de vérité.
