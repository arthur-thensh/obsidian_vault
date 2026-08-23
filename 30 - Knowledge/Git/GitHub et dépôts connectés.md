---
type: knowledge
parent: Git
---

# GitHub et dépôts connectés

## Répartition des responsabilités

GitHub est la source de vérité pour le code, les branches, les commits et l'état exact des fichiers. Obsidian conserve le contexte difficile à déduire du code : décisions, architecture, procédures, objectifs et explications.

## Règle pour la documentation technique

Avant de documenter une arborescence, un script ou un comportement lié à un projet, vérifier le dépôt réel. Ne pas créer une procédure basée sur un nom de fichier supposé.

## Branches de travail

Une note Obsidian doit préciser la branche lorsqu'une information n'est pas encore sur `main`. Exemple : la refonte visuelle de [[Idle Game]] peut être décrite à partir de `visual-rework-2d` sans faire croire qu'elle est déjà intégrée à la branche principale.

## Synchronisation du vault

```bash
cd ~/Documents/obsidian_vault
git pull --ff-only
```

Après des modifications locales :

```bash
git status
git add .
git commit -m "Update vault"
git push
```

## Liens

- [[Git]]
- [[Workflow Git quotidien]]
- [[OpenRide]]
- [[Idle Game]]
