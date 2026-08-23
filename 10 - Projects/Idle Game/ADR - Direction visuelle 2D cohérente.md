---
type: decision
project: Idle Game
status: accepted
branch: visual-rework-2d
---

# ADR - Direction visuelle 2D cohérente

## Contexte

Le prototype fonctionnel a progressivement accumulé une UI et des éléments visuels de styles différents. Pour éviter une refonte fragmentée, la branche `visual-rework-2d` sert de chantier dédié.

## Décision

Construire la direction visuelle autour d'un langage 2D cohérent et d'assets structurés par catégories (`Player`, `Enemies`, `Animals`, `Tiles`, `Outdoor decoration`). Les nouveaux assets doivent être conçus pour être intégrables directement dans Godot avec une structure compatible avec les assets déjà retenus.

## Principes

- cohérence de résolution et de densité de pixels ;
- proportions homogènes entre personnages, ennemis et décor ;
- animations et spritesheets structurées de façon reproductible ;
- lisibilité mobile prioritaire ;
- éviter les assets isolés qui paraissent réussis seuls mais incompatibles avec le reste du jeu.

## Conséquences

Toute proposition visuelle doit être comparée aux assets de la branche avant intégration. La branche principale ne doit pas être utilisée comme référence si la refonte existe uniquement dans `visual-rework-2d`.

## Liens

- [[Idle Game]]
- [[Direction visuelle Idle Game]]
- [[Organisation projet Godot]]
