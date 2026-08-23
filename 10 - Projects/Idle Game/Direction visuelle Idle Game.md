---
type: visual-direction
project: Idle Game
branch: visual-rework-2d
last_verified: 2026-08-23
---

# Direction visuelle Idle Game

## Branche de travail

La refonte visuelle 2D est portée par la branche :

```text
visual-rework-2d
```

Cette branche contient une arborescence d'assets plus structurée que `main` :

```text
assets/
├── Animals/
├── Enemies/
├── Outdoor decoration/
├── Player/
├── Tiles/
└── read_me.txt
```

## Principe de production

Le pack présent dans `assets/` sert de référence visuelle pour produire les nouveaux éléments du jeu.

Les nouveaux assets doivent être conçus pour être **directement intégrables dans Godot** et conserver une structure cohérente avec les ressources déjà présentes :

- dimensions de sprites compatibles ;
- grille/cellules cohérentes ;
- proportions constantes ;
- densité de pixels homogène ;
- conventions de nommage stables ;
- organisation par catégorie compatible avec l'arborescence du dépôt.

## Catégories actuelles

### `Player/`

Sprites du personnage jouable et variantes/animations associées.

### `Animals/`

Créatures animales et faune du monde.

### `Enemies/`

Ennemis et créatures hostiles.

### `Outdoor decoration/`

Décors, végétation et éléments d'environnement extérieur.

### `Tiles/`

Éléments composant le terrain et le monde top-down.

## Règle de cohérence

> [!important]
> Avant de produire un nouvel asset, inspecter le dossier `assets/` de la branche visuelle et prendre les fichiers existants comme référence technique et esthétique. Ne pas inventer arbitrairement une résolution, une structure de spritesheet ou un format d'animation.

## Intégration

Un asset validé ne doit pas rester une simple image de concept. Il doit être livré avec la même logique d'organisation que les assets existants afin de pouvoir remplacer ou compléter directement les ressources du jeu.

## Relation avec le gameplay

La direction visuelle doit servir [[Gameplay Idle Game]] :

- lecture immédiate en vue top-down ;
- personnage et ennemis reconnaissables sur petit écran ;
- décors suffisamment riches sans nuire à la lisibilité du combat ;
- animations lisibles même lorsque le jeu tourne en mode idle visible.
