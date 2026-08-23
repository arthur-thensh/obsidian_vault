---
type: design
project: Idle Game
last_verified: 2026-08-23
---

# Gameplay Idle Game

## Boucle principale

Le jeu vise un compromis entre jeu actif et progression automatisée :

```text
Explorer
   ↓
Combattre / Récolter
   ↓
Loot / Ressources
   ↓
Équipement / Classes / Métiers
   ↓
Progression
   ↓
Débloquer de nouvelles activités
   ↺
```

## Jeu actif

Le joueur contrôle directement les déplacements et les décisions importantes. Le combat se déroule dans le monde, sans écran de combat séparé.

Les attaques de base peuvent être semi-automatiques afin de conserver une bonne lisibilité et une utilisation mobile confortable, tandis que l'esquive, les compétences et le positionnement gardent une part active.

## Idle visible

Lorsque le jeu reste ouvert sans interaction, la progression doit rester visible dans le monde : le personnage continue une activité compréhensible à l'écran plutôt que d'être remplacé par une simple barre de progression.

C'est un principe central du projet.

## Progression hors ligne

Lorsque l'application est fermée, la progression doit être calculée de manière agrégée à partir de l'état sauvegardé et du temps écoulé, plutôt que de simuler chaque frame manquée.

## Classes

Le personnage n'est pas définitivement enfermé dans une classe. Les classes sont prévues comme des voies équipables/déblocables liées aux maîtrises et à la progression.

## Métiers

Les métiers doivent participer à la boucle longue durée : récolte, transformation, crafting et progression spécialisée.

## Loot

Le système combine :

- objets procéduraux pour la variété et la progression longue ;
- objets uniques conçus manuellement pour créer des objectifs mémorables.

## Monde

Le monde principal doit être conçu manuellement afin de conserver identité et cohérence. Un endgame plus procédural peut ensuite prolonger la durée de vie du jeu.

## Références

- [[Architecture Idle Game]]
- [[Systèmes Idle Game]]
- [[Contrôles Idle Game]]
