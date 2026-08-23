---
type: knowledge
parent: Android
---

# ADB et diagnostic Android

## Vérifier la connexion

```bash
adb devices
```

Un appareil doit apparaître avec l'état `device`.

## Identifier une application

```bash
adb shell pidof com.exemple.app
```

## Observer la consommation

```bash
adb shell top -b -n 1 | grep com.exemple.app
```

## Lire les erreurs récentes

```bash
adb logcat -d -t 300 | grep -E "AndroidRuntime|FATAL|libc|lmkd"
```

Pour suivre les logs en direct :

```bash
adb logcat
```

## Stockage privé d'une application debug

Lorsque l'application est debuggable, `run-as` permet d'inspecter son stockage privé :

```bash
adb shell run-as com.exemple.app ls -lah files
```

C'est préférable à supposer qu'un chemin partagé est accessible, car Android applique le scoped storage.

## Diagnostic reproductible

Pour un bug mobile, conserver ensemble :

1. commit testé ;
2. modèle/appareil ou émulateur ;
3. version Android ;
4. action reproduisant le bug ;
5. extrait logcat ;
6. capture ou vidéo si le problème est visuel.

## Liens

- [[Android]]
- [[Android OpenRide]]
- [[Environnement Mac]]
