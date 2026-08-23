---
type: workflow
project: OpenRide
last_verified: 2026-08-23
---

# Workflow de développement OpenRide

## Environnement principal

Le développement quotidien se fait sur macOS avec :

- VS Code pour l'édition ;
- Terminal pour construire, tester et lancer ;
- CMake ;
- clang ;
- C17 ;
- SDL3 ;
- Git ;
- Android SDK/NDK pour la cible Android.

## Installation initiale

```sh
xcode-select --install
brew install cmake sqlite3
```

Puis :

```sh
mkdir -p ~/Projects
cd ~/Projects
git clone git@github.com:arthur-thensh/openride.git
cd openride
./scripts/bootstrap_sdl.sh
```

## Build macOS recommandé

```sh
./scripts/build_macos.sh
```

Ce script regroupe configuration CMake, compilation et tests.

Les étapes restent accessibles séparément :

```sh
./scripts/configure.sh
./scripts/build.sh
./scripts/test.sh
```

Lancement :

```sh
./scripts/run.sh
```

## Données de développement

Pour préparer la région de référence :

```sh
./scripts/download_routing_data.sh
./scripts/prepare_region.sh
```

Voir [[Pipeline de données OpenRide]].

## Benchmarks disponibles

```sh
./scripts/benchmark_spatial_index.sh
./scripts/benchmark_segment_index.sh
./scripts/benchmark_loop_generator.sh
```

## Règles pratiques

- Ne pas commiter `vendor/SDL` ou `vendor/sqlite`.
- Ne pas commiter les grosses données cartographiques locales.
- Vérifier le dépôt avant de supposer un nom de script ou un emplacement de fichier.
- Maintenir le cœur C indépendant de la plateforme autant que possible.
- Valider les changements avec les tests avant de les considérer terminés.

## Références

- [[Architecture OpenRide]]
- [[Tests OpenRide]]
- [[Android OpenRide]]
