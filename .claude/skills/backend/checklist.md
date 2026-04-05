# Backend Implementation Checklist

## Core Checkliste
- [ ] Bestehende Services/Modelle geprüft bevor neue erstellt werden
- [ ] Alle Datenmodelle mit `toJson()` und `fromJson()` implementiert
- [ ] Null-Safety korrekt umgesetzt
- [ ] Alle geplanten API-Services implementiert in `lib/core/api/`
- [ ] Alle HTTP-Calls haben try/catch und Timeout (10 Sekunden)
- [ ] HTTP-Statuscodes werden geprüft
- [ ] Leere/fehlerhafte API-Antworten werden behandelt
- [ ] Verständliche Fehlermeldungen für den Nutzer
- [ ] Datenspeicherung implementiert in `lib/core/storage/`
- [ ] Speichern → App neu starten → Laden getestet
- [ ] Keine API-Keys im Code (--dart-define genutzt)
- [ ] Frontend-BLoCs mit echten Services verbunden
- [ ] Mock-Daten entfernt und durch echte API-Calls ersetzt
- [ ] Nutzer hat reviewed und freigegeben

## Verifikation (vor Abschluss ausführen)
- [ ] `flutter analyze` ohne Fehler
- [ ] `flutter build apk --debug` erfolgreich
- [ ] Alle Acceptance Criteria aus der Feature Spec durch APIs abgedeckt
- [ ] API-Calls mit echten Daten manuell getestet
- [ ] `features/INDEX.md` Status auf "In Progress" aktualisiert
- [ ] Code in Git committet

## Performance Checkliste
- [ ] Daten werden gecacht wo sinnvoll (nicht bei jedem App-Start neu laden)
- [ ] Offline-Fall behandelt (App funktioniert ohne Internet)
- [ ] Keine unnötigen API-Calls (z.B. nicht bei jedem Widget-Rebuild)
- [ ] Rate Limiting bei externen APIs beachtet (optional für MVP)