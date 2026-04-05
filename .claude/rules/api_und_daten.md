# API & Datenspeicher Rules

## API-Calls
- IMMER try/catch um alle HTTP-Calls
- Timeout setzen: `.timeout(const Duration(seconds: 10))`
- HTTP-Statuscode prüfen bevor Antwort verarbeitet wird
- Leere/fehlerhafte Antworten behandeln (null-Check)
- Kein Internet → verständliche Fehlermeldung für den Nutzer
- Services in `lib/core/api/` — ein Service pro externer API

## Datenspeicherung (SharedPreferences)
- JSON-Encoding für komplexe Objekte
- Alle Datenklassen haben `toJson()` und `fromJson()` Methoden
- Null-Safety beim Laden beachten
- Speichern → App neu starten → Laden testen

## Daten cachen
- Daten cachen wo sinnvoll — nicht bei jedem App-Start neu laden
- Cache invalidieren wenn Daten veraltet sein könnten
- Offline-Fall bedenken: App muss grundlegend ohne Internet funktionieren

## Sicherheit
- NIEMALS API-Keys im Code hardcoden
- `--dart-define` für alle Credentials:
  `flutter run --dart-define=API_KEY=dein-key`
- Alle sensiblen Dateien in `.gitignore`:
  `key.properties`, `*.jks`, `*.env`
- Keine sensiblen Daten in `print()` Statements

## Input Validierung
- Alle Nutzereingaben validieren bevor sie verarbeitet werden
- Niemals externe API-Daten blind vertrauen
- Fehlerhafte Daten graceful behandeln

## Secrets Management
- Niemals Secrets, API-Keys oder Credentials in Git committen
- Alle benötigten Umgebungsvariablen in `README.md` dokumentieren
- Für sensible Daten (Auth-Tokens): `flutter_secure_storage` nutzen

## Code Review Trigger
- Änderungen an Auth-Logik erfordern explizite Nutzer-Freigabe
- Neue externe APIs erfordern Dokumentation in CLAUDE.md
- Neue sensible Datenspeicherung erfordert Security-Review