---
type: architecture
project: Idle Game
engine: Godot 4.7
last_verified: 2026-08-23
---

# Architecture Idle Game

## Base technique

Le projet utilise Godot **4.7** et GDScript. La scène principale déclarée dans `project.godot` est :

```text
res://scenes/main/main.tscn
```

Le projet cible une interface mobile portrait avec viewport logique de 720 × 1280 et rendu `gl_compatibility`, y compris sur mobile.

## Séparation des responsabilités

L'arborescence montre déjà une architecture orientée domaines plutôt qu'un unique script central.

### Scripts

```text
scripts/
├── classes/
├── core/
├── crafting/
├── enemies/
├── idle/
├── inventory/
├── items/
├── loot/
├── main/
├── player/
├── professions/
├── save/
├── ui/
└── world/
```

### Scènes

```text
scenes/
├── crafting/
├── enemies/
├── main/
├── player/
├── professions/
├── ui/
└── world/
```

Cette séparation est une bonne base : logique métier et représentation visuelle peuvent évoluer sans concentrer tout le jeu dans la scène principale.

## Principes à conserver

- garder les données de contenu séparées de la logique lorsque possible ;
- éviter que l'UI devienne propriétaire de l'état du jeu ;
- conserver une simulation exploitable aussi bien en actif qu'en idle ;
- centraliser la sauvegarde et son versionnement ;
- faire communiquer les systèmes par interfaces/signaux clairs plutôt que par dépendances circulaires ;
- conserver les scènes spécialisées petites et composables.

## Systèmes actuellement représentés

L'arborescence contient déjà des domaines dédiés pour :

- classes ;
- crafting ;
- ennemis ;
- idle ;
- inventaire ;
- items ;
- loot ;
- joueur ;
- professions ;
- sauvegarde ;
- UI ;
- monde.

Voir [[Systèmes Idle Game]].

## Assets

Le dossier `assets/` contient actuellement un pack Vallée des Pins, un espace `_incoming` et un dossier `generated`. La production d'assets doit conserver une structure compatible avec leur intégration directe dans Godot.

Voir [[Direction visuelle Idle Game]].
