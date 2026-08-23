---
type: area-note
area: Informatique
---

# Principes de travail technique

## Source de vérité

Pour un projet versionné, le dépôt Git est la référence pour l'arborescence, les fichiers et l'état du code. Une note Obsidian ne doit pas inventer un script, un chemin ou une architecture lorsqu'ils sont vérifiables dans le dépôt.

## Avant une modification

1. vérifier la branche active ;
2. inspecter les fichiers concernés ;
3. lire la documentation existante ;
4. identifier les tests disponibles ;
5. seulement ensuite proposer ou appliquer le changement.

## Après une modification

1. compiler ou lancer le projet ;
2. exécuter les tests pertinents ;
3. vérifier `git diff` ;
4. documenter une décision si elle change l'architecture ;
5. commiter avec un message précis.

## Diagnostic

Lorsqu'un test échoue, conserver :

- la commande exacte ;
- la première erreur utile ;
- le commit ou la branche ;
- l'environnement ;
- les logs pertinents.

Éviter de corriger une série d'erreurs secondaires avant la première erreur racine.

## Documentation dans Obsidian

Documenter surtout :

- décisions et raisons ;
- procédures reproductibles ;
- architecture ;
- contraintes ;
- résultats de benchmarks ;
- leçons apprises.

Éviter de dupliquer intégralement le README ou le code.

## Liens

- [[GitHub et dépôts connectés]]
- [[Workflow Git quotidien]]
- [[ADB et diagnostic Android]]
- [[Organisation projet Godot]]
