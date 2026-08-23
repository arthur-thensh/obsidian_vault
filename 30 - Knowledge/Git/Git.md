---
type: knowledge
---

# Git

## Rôle

Git sert à versionner les projets et le vault lui-même.

## Notes

- [[Workflow Git quotidien]]
- [[GitHub et dépôts connectés]]

## Workflow minimal

```bash
git status
git pull --ff-only
git add .
git commit -m "Description du changement"
git push
```

## Bonnes pratiques

- vérifier `git status` avant un pull ;
- ne pas écraser des modifications locales non commitées ;
- lire `git diff` avant de commiter ;
- préférer des commits ciblés ;
- isoler les gros chantiers dans des branches ;
- ne pas supposer l'état d'un dépôt : inspecter la branche et les fichiers réels.

## Liens

- [[OpenRide]]
- [[Idle Game]]
- [[Environnement Mac]]
