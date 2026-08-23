---
type: area-note
area: Informatique
---

# Environnement Mac

## Machine de référence

MacBook Air 13 pouces, puce Apple M4, 16 Go de RAM.

## Philosophie de travail

- VS Code pour l'édition ;
- Terminal pour compiler, tester et lancer ;
- Homebrew pour les dépendances ;
- clang comme compilateur C/C++ ;
- CMake pour les projets natifs ;
- Git + SSH pour les dépôts ;
- éviter l'IDE Xcode tant qu'il n'est pas requis pour iOS.

## Outils vérifiés

- CMake ;
- Ninja ;
- SQLite ;
- Java 17 ;
- Git ;
- accès SSH GitHub.

## Checklist nouveau poste

```bash
xcode-select --install
brew install cmake ninja sqlite git
clang --version
cmake --version
git --version
ssh -T git@github.com
```

Pour Android, compléter avec SDK/NDK et vérifier `adb`.

## Projets concernés

- [[OpenRide]]
- [[Idle Game]]
- [[Git]]
- [[Android]]
