---
type: knowledge
parent: Godot
---

# Organisation projet Godot

## Principe

Séparer clairement les scènes, la logique métier et les données évite qu'un prototype devienne rapidement difficile à maintenir.

## Structure recommandée

```text
scenes/
  main/
  player/
  enemies/
  world/
  ui/
scripts/
  core/
  player/
  enemies/
  inventory/
  loot/
  save/
  ui/
data/
assets/
```

Cette logique correspond bien à l'architecture actuelle de [[Idle Game]].

## Règles utiles

- une scène doit représenter une responsabilité claire ;
- éviter de concentrer toute la logique dans la scène principale ;
- garder la simulation séparée de l'UI lorsque possible ;
- préférer des données configurables à des valeurs dispersées dans les scripts ;
- utiliser les signaux pour découpler les systèmes ;
- centraliser sauvegarde et chargement ;
- tester les systèmes indépendamment avant de multiplier les écrans UI.

## Debug GDScript

Lorsqu'une erreur de parse entraîne plusieurs messages, corriger d'abord **la toute première erreur** : les suivantes sont souvent des conséquences du parseur désynchronisé.

Pour les erreurs d'accès de propriété, vérifier le type réel du nœud ou de la ressource avant de supposer qu'une propriété existe.

## Liens

- [[Godot]]
- [[Architecture Idle Game]]
- [[Systèmes Idle Game]]
