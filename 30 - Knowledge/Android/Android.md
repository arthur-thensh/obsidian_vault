---
type: knowledge
---

# Android

## Sujets suivis

- ADB ;
- SDK / NDK ;
- permissions ;
- stockage privé des applications ;
- débogage avec logcat ;
- émulateurs ;
- optimisation mobile.

## Notes

- [[ADB et diagnostic Android]]
- [[Android OpenRide]]

## Commandes de base

```bash
adb devices
adb shell
adb logcat
```

## Principe

Sur Android moderne, ne pas supposer qu'une application peut écrire librement dans le stockage partagé. Pour les données internes, raisonner d'abord en termes de stockage privé de l'application et de scoped storage.

## Projets liés

- [[OpenRide]]
- [[Idle Game]]
