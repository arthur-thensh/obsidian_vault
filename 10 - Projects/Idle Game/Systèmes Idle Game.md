---
type: technical-note
project: Idle Game
last_verified: 2026-08-23
---

# Systèmes Idle Game

## Vue d'ensemble

Le dépôt comporte déjà des modules distincts pour les principaux systèmes de jeu. Cette note sert d'index fonctionnel et devra être affinée au fur et à mesure que chaque sous-système se stabilise.

## `classes/`

Responsable de la logique liée aux classes du personnage : choix équipable, progression associée et compétences de classe.

## `crafting/`

Logique de fabrication et interaction avec les ressources/métiers.

## `enemies/`

Comportement et données des ennemis, combat et interactions avec le joueur.

## `idle/`

Cœur de la progression automatisée. Ce domaine est stratégique car il doit servir deux situations différentes :

- activité visible lorsque l'application reste ouverte ;
- calcul agrégé de progression lorsque l'application a été fermée.

## `inventory/`

Gestion de l'inventaire et des équipements. L'interface doit éviter de devenir envahissante, surtout sur écran mobile portrait.

## `items/`

Définition des objets et de leurs propriétés. Ce domaine doit rester compatible avec une approche data-driven pour faciliter l'ajout de contenu.

## `loot/`

Génération et attribution du butin. Le design prévoit du loot procédural complété par des objets uniques.

## `player/`

Contrôle du personnage, états liés au joueur et interactions avec les autres systèmes.

## `professions/`

Progression des métiers, récolte et activités de production.

## `save/`

Sauvegarde locale et reprise de progression. La sauvegarde doit être versionnée afin de supporter l'évolution du format sans casser les parties existantes.

## `ui/`

Présentation des systèmes. L'UI ne doit pas devenir la source de vérité de l'état métier : elle doit refléter les données détenues par les systèmes de jeu.

## `world/`

Organisation du monde, zones, contenu spatial et interactions environnementales.

## Règle d'architecture

> [!important]
> Le mode idle ne doit pas devenir un second jeu séparé. Le même modèle de progression doit alimenter le jeu actif, l'automatisation visible et le calcul hors ligne.
