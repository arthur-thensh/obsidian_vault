---
type: reference
project: Idle Game
source: project.godot
last_verified: 2026-08-23
---

# Contrôles Idle Game

## Actions déclarées dans Godot

Le fichier `project.godot` définit actuellement les actions suivantes :

| Action | Rôle |
|---|---|
| `move_left` | déplacement gauche |
| `move_right` | déplacement droite |
| `move_up` | déplacement haut |
| `move_down` | déplacement bas |
| `dodge` | esquive |
| `special_attack` | attaque spéciale |
| `class_skill` | compétence de classe |
| `interact` | interaction |
| `toggle_inventory` | ouvrir/fermer l'inventaire |
| `toggle_classes` | ouvrir/fermer l'interface de classes |
| `toggle_automation` | activer/désactiver l'automatisation |

## Clavier de développement

Les bindings actuels permettent notamment les dispositions QWERTY et AZERTY pour le déplacement :

- gauche : `A` ou `Q` ;
- droite : `D` ;
- haut : `W` ou `Z` ;
- bas : `S` ;
- esquive : `Espace` ;
- attaque spéciale : `E` ;
- compétence de classe : `R` ;
- interaction : `F` ;
- inventaire : `I` ;
- classes : `C` ;
- automation : `O`.

## Mobile

Ces actions constituent l'abstraction d'entrée. Les contrôles tactiles mobiles doivent déclencher ces mêmes actions ou les mêmes fonctions métier afin d'éviter de maintenir deux logiques de gameplay différentes.

## Résolution cible

Le viewport logique configuré est :

```text
720 × 1280
```

Orientation : portrait.

Voir [[Architecture Idle Game]].
