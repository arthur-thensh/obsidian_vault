---
type: project
status: active
repository: arthur-thensh/idle_game
engine: Godot 4.7
language: GDScript
orientation: portrait
last_verified: 2026-08-23
---

# Idle Game

## Objectif

Créer un RPG/idle mobile 2D top-down jouable hors ligne, avec exploration active, combat semi-automatique, progression idle visible, loot, classes, métiers et progression longue durée.

## État réel du dépôt

Le projet n'est plus seulement au stade du Game Design : le dépôt contient maintenant un **prototype Godot 4.7 structuré**.

La scène principale est :

```text
res://scenes/main/main.tscn
```

La configuration actuelle vise un viewport mobile portrait de **720 × 1280** avec rendu `gl_compatibility`.

## Systèmes présents dans l'arborescence

Les scripts sont déjà séparés par domaines :

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

Les scènes suivent une séparation similaire :

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

## Contrôles actuellement déclarés

Le projet définit notamment :

- déplacement gauche/droite/haut/bas ;
- esquive ;
- attaque spéciale ;
- compétence de classe ;
- interaction ;
- ouverture de l'inventaire ;
- ouverture des classes ;
- activation de l'automatisation.

## Direction de gameplay

- personnage unique ;
- classes équipables plutôt que choix définitif ;
- progression par maîtrises et métiers ;
- combat directement dans le monde ;
- attaques de base automatisables ;
- déplacement et décisions importantes contrôlés par le joueur ;
- idle visible lorsque le jeu reste ouvert ;
- progression hors ligne prévue lorsque l'application est fermée ;
- loot procédural complété par des objets uniques.

## Assets

Le dépôt contient actuellement :

- `assets/ValleeDesPins_AssetPack_V0_1.zip` ;
- `assets/_incoming/` ;
- `assets/generated/`.

La direction visuelle et la structure des assets doivent rester documentées séparément afin de conserver une cohérence de production.

## Sections

- [[Architecture Idle Game]]
- [[Gameplay Idle Game]]
- [[Direction visuelle Idle Game]]
- [[Systèmes Idle Game]]
- [[Contrôles Idle Game]]

## Point de vigilance

Le `README.md` du dépôt décrit encore le projet comme étant en préproduction, alors que l'arborescence contient désormais un prototype jouable et de nombreux systèmes. Pour suivre l'avancement, il faut donc privilégier l'état réel du dépôt plutôt que ce statut historique.

## Dépôt

GitHub : `arthur-thensh/idle_game`
