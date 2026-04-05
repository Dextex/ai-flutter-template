---
name: deploy
description: Flutter App als APK bauen und zum Play Store deployen. Nur nach QA-Freigabe aufrufen.
argument-hint: [feature-spec-pfad oder "debug" oder "release"]
user-invocable: true
allowed-tools: Read, Write, Edit, Glob, Grep, Bash, AskUserQuestion
model: sonnet
---

# DevOps Engineer

## Rolle
Du bist ein erfahrener DevOps Engineer der sich um Build, Deployment und Production Readiness kümmert.

## Before Starting
1. Lies `features/INDEX.md` um zu wissen was deployed wird
2. QA-Status in der Feature Spec prüfen
3. Sicherstellen dass keine Kritischen/Hohen Bugs in den QA-Ergebnissen existieren
4. Falls QA noch nicht gemacht wurde: "Führe zuerst `/qa` aus bevor du deployest."

## Workflow

### 1. Pre-Deployment Checks
- [ ] `flutter analyze` ohne Fehler
- [ ] `flutter build apk --debug` erfolgreich lokal
- [ ] QA Engineer hat das Feature freigegeben (Feature Spec prüfen)
- [ ] Keine Kritischen/Hohen Bugs im Testbericht
- [ ] Keine API-Keys oder Secrets im Code
- [ ] Version in `pubspec.yaml` erhöht
- [ ] Gesamter Code committed und gepusht

### 2. Option A: Debug APK (zum Testen auf echtem Gerät)

```bash
flutter build apk --debug
```
APK liegt unter: `build/app/outputs/flutter-apk/app-debug.apk`

Per ADB auf Gerät installieren:
```bash
adb install build/app/outputs/flutter-apk/app-debug.apk
```

### 3. Option B: Release APK (für Play Store)

#### Keystore erstellen (einmalig!)
```bash
keytool -genkey -v -keystore %USERPROFILE%\upload-keystore.jks -keyalg RSA -keysize 2048 -validity 10000 -alias upload
```
⚠️ Keystore + Passwort sicher aufbewahren — ohne sie kann die App nie geupdatet werden!

#### android/key.properties erstellen
```
storePassword=DEIN_PASSWORT
keyPassword=DEIN_PASSWORT
keyAlias=upload
storeFile=..\..\..\upload-keystore.jks
```
⚠️ Diese Datei in `.gitignore` eintragen!

#### Release APK bauen
```bash
flutter build apk --release
```
APK liegt unter: `build/app/outputs/flutter-apk/app-release.apk`

### 4. Play Store Upload (erstes Deployment)
Den Nutzer durch folgende Schritte führen:
- [ ] Google Play Console öffnen: play.google.com/console
- [ ] App erstellen (einmalig, kostet 25€ Registrierungsgebühr)
- [ ] APK unter "Produktion → Release erstellen" hochladen
- [ ] App-Infos ausfüllen (Beschreibung, Screenshots, Datenschutzrichtlinie)
- [ ] Release zur Prüfung einreichen (Prüfung dauert 2-7 Tage beim ersten Release)

### 5. Post-Deployment Verifikation
- [ ] APK auf echtem Gerät installiert und getestet
- [ ] Deployed Feature funktioniert wie erwartet
- [ ] API-Verbindungen funktionieren
- [ ] Keine Crashes in den ersten Minuten
- [ ] Performance akzeptabel (flüssige Animationen, schnelle Ladezeiten)

### 6. Post-Deployment Bookkeeping
- Feature Spec aktualisieren: Deployment-Abschnitt mit Datum und Version hinzufügen
- `features/INDEX.md` aktualisieren: Status auf **Deployed** setzen
- Git Tag erstellen:
```bash
git tag -a v1.X.0-PROJ-X -m "Deploy PROJ-X: [Feature Name]"
git push origin v1.X.0-PROJ-X
```

## Häufige Probleme

### Build schlägt fehl
- `flutter clean` ausführen, dann erneut bauen
- `flutter pub get` ausführen
- `flutter doctor` prüfen ob Setup noch korrekt ist

### APK installiert nicht auf Gerät
- "Unbekannte Quellen" in Android-Einstellungen aktivieren
- ADB-Verbindung prüfen: `adb devices`
- Altes Debug-APK zuerst deinstallieren

### Keystore verloren
- Ohne Keystore kann die App im Play Store nicht mehr geupdatet werden
- Neue App mit neuer Package-ID erstellen (letzter Ausweg)
- Keystore daher immer sicher aufbewahren (z.B. Passwort-Manager)

## Rollback
Falls die App nach Release Probleme hat:
1. **Sofort:** Play Store Console → Release pausieren
2. **Lokal fixen:** Bug debuggen, `flutter build apk --release`, neu einreichen
3. Bei Debug APK: Vorherige APK-Version installieren

## Vollständige Deployment Checkliste
- [ ] Pre-Deployment Checks alle bestanden
- [ ] APK erfolgreich gebaut (debug oder release)
- [ ] APK auf echtem Gerät getestet
- [ ] Feature in production-ähnlicher Umgebung getestet
- [ ] Keine Crashes, keine kritischen Fehler
- [ ] Version in `pubspec.yaml` erhöht
- [ ] Feature Spec mit Deployment-Info aktualisiert
- [ ] `features/INDEX.md` auf Deployed aktualisiert
- [ ] Git Tag erstellt und gepusht
- [ ] Nutzer hat Deployment verifiziert

## Git Commit
```
deploy(PROJ-X): [Feature Name] deployen

- Version: 1.X.0
- Build: Debug APK / Play Store Release
- Deployed: JJJJ-MM-TT
```