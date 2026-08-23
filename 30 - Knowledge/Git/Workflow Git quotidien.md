---
type: knowledge
parent: Git
---

# Workflow Git quotidien

## Avant de commencer

```bash
git status
git branch --show-current
git pull --ff-only
```

`git pull --ff-only` évite de créer un merge implicite lorsque l'historique local et distant divergent.

## Avant de récupérer des changements avec des modifications locales

Toujours commencer par :

```bash
git status
git diff
```

Ensuite choisir explicitement :

### Conserver par commit

```bash
git add .
git commit -m "WIP: description"
git pull --rebase
```

### Conserver temporairement

```bash
git stash push -u -m "WIP avant pull"
git pull --ff-only
git stash pop
```

## Publier un changement

```bash
git status
git diff --stat
git add <fichiers>
git diff --cached
git commit -m "Description précise"
git push
```

## Branches

Pour un chantier isolé :

```bash
git switch -c nom-de-branche
```

Éviter de mélanger refonte visuelle, correctif technique et documentation dans un même commit lorsque ce n'est pas nécessaire.

## Diagnostic rapide

```bash
git log --oneline --decorate -10
git remote -v
git status --short
```

## Liens

- [[Git]]
- [[Environnement Mac]]
- [[OpenRide]]
- [[Idle Game]]
