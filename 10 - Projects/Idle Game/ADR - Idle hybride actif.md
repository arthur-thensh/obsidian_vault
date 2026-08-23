---
type: decision
project: Idle Game
status: accepted
---

# ADR - Idle hybride actif

## Contexte

Le jeu doit fonctionner comme un RPG jouable activement tout en restant intéressant lorsqu'il tourne sans interaction. Un idle purement abstrait ferait perdre la présence du personnage dans le monde ; un RPG uniquement actif ne remplirait pas l'objectif de progression idle longue durée.

## Décision

Adopter un modèle hybride :

- déplacement et décisions importantes disponibles en jeu actif ;
- attaques de base et certaines activités automatisables ;
- progression idle visible lorsque l'application reste ouverte ;
- simulation agrégée lorsque l'application est fermée ;
- le monde et le personnage restent la représentation principale de la progression.

## Conséquences

La simulation de gameplay doit être suffisamment séparée de l'UI pour pouvoir fonctionner à plusieurs niveaux de détail. Les systèmes de loot, métiers, combat et sauvegarde doivent être compatibles avec l'automatisation.

## Liens

- [[Idle Game]]
- [[Gameplay Idle Game]]
- [[Architecture Idle Game]]
- [[Systèmes Idle Game]]
