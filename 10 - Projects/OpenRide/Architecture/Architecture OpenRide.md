---
type: architecture
project: OpenRide
last_verified: 2026-08-23
---

# Architecture OpenRide

## Principe général

OpenRide privilégie un cœur portable en **C17**. La carte, le routage, la navigation, la recherche, le GPX, la génération de boucles et la logique GPS vivent autant que possible dans le code commun. SDL3 fournit le rendu et la couche applicative multiplateforme.

Les couches spécifiques Android et, plus tard, iOS doivent rester limitées aux services réellement dépendants du système : GPS, cycle de vie, stockage et intégration native.

## Vue d'ensemble

```text
                   ┌─────────────────────┐
                   │   Données OSM PBF   │
                   └──────────┬──────────┘
                              │
            ┌─────────────────┼─────────────────┐
            │                 │                 │
            ▼                 ▼                 ▼
        .orgraph      .orplaces.sqlite     cartes OpenRide
                                               │
                                      ┌────────┴────────┐
                                      ▼                 ▼
                                  .ormap v8        .ormap11 v11

            ┌──────────────────────────────────────────┐
            │               Cœur C17                  │
            │ carte · routing · navigation · GPX      │
            │ recherche · boucles · GPS · état app    │
            └────────────────────┬─────────────────────┘
                                 │
                               SDL3
                    ┌────────────┴────────────┐
                    ▼                         ▼
                  macOS                    Android
            GPS simulé / dev         JNI + GPS système
```

## Répertoires structurants

```text
include/openride/   API publiques du cœur C
src/core/           logique applicative partagée
src/map/            carte, formats et rendu
src/osm/            import et transformation OSM
src/platform/       abstraction plateforme
src/tools/          outils de préparation/inspection
android/            couche Android native
scripts/            build, données, tests, benchmarks
tests/              tests CTest
```

## Données

La donnée source d'une région est un `.osm.pbf`. Elle peut produire quatre artefacts :

- `.orgraph` : graphe de routage et index spatiaux ;
- `.orplaces.sqlite` : recherche locale ;
- `.ormap` v8 : carte stable ;
- `.ormap11` v11 : carte détaillée TilePyramid.

Voir [[Pipeline de données OpenRide]].

## Cartographie

Le rendu cartographique repose sur SDL3 et cherche explicitement à limiter le coût GPU/CPU sur mobile. Les routes, casings, waterways, surfaces et masques sont regroupés en batches de géométrie.

Les bâtiments individuels ne sont pas la représentation finale du format stable : ils contribuent à générer des zones bâties simplifiées.

Voir [[Cartographie OpenRide]].

## Routage

Le moteur utilise un graphe dirigé, des index spatiaux pour les nœuds et segments, du snapping et un pathfinder A* interne. A* est un détail d'implémentation : le composant fonctionnel est le moteur de routage hors ligne.

Voir [[Routing OpenRide]].

## Navigation

La couche navigation ajoute au calcul d'itinéraire :

- instructions turn-by-turn ;
- progression ;
- gestion des ronds-points ;
- détection de sortie de route ;
- recalcul ;
- filtrage GPS ;
- statistiques de session ;
- Drive Mode orienté selon le cap.

Voir [[Drive Mode]].

## Portabilité

### macOS

Plateforme principale de développement. SDL3, CMake et clang sont utilisés directement. Le GPS peut être simulé pour tester la navigation.

### Android

Le cœur reste en C. La couche Android fournit notamment l'accès au GPS réel et au cycle de vie via JNI/Java.

### iOS

Prévu ultérieurement avec le même principe : conserver le maximum de logique dans le cœur C et limiter la couche native.
