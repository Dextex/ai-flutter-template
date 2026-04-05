# AI Flutter Starter Template

> Ein Flutter-basiertes Template das einen strukturierten AI-Workflow bereitstellt um optimierter mit AI zu entwickeln. Dieses Template nutzt spezialisierte Skills für Requirements, Architecture, Frontend, Backend, QA und Deployment.

## Tech Stack
| Bereich | Tool |
|---|---|
| Framework | Flutter (Dart) |
| State Management | BLoC (flutter_bloc) |
| Lokaler Speicher | SharedPreferences (optional) |
| Backend | Firebase (Firestore + Auth) (optional) |
| Deployment | Google Play Store |
| Versionierung | GitHub |
| UI Framework | Material Design 3 (built-in) |
| Icons | Material Icons (built-in) |
| Schriften | Google Fonts (optional) |

## Projekt-Struktur
```
lib/
  features/         ← Feature-spezifischer Code (Screens, BLoCs, Widgets)
  core/             ← APIs, Datenmodelle, Storage-Logik
  shared/           ← Wiederverwendbare Widgets
features/           ← Feature Specs (PROJ-X-name.md)
  INDEX.md          ← Feature Status Übersicht
docs/
  PRD.md            ← Product Requirements Document
```

## Development Workflow
1. `/requirements` → Feature Spec aus Idee erstellen
2. `/architecture` → Technisches Design (Datenmodell, BLoC, Widgets)
3. `/frontend`     → Flutter UI + BLoC bauen
4. `/backend`      → API-Integration + Datenspeicherung
5. `/qa`           → Gegen Acceptance Criteria testen
6. `/deploy`       → APK bauen + Play Store

## Feature Tracking
Alle Features werden in `features/INDEX.md` getrackt. Jeder Skill liest die Datei beim Start und aktualisiert sie wenn er fertig ist. Feature Specs leben in `features/PROJ-X-name.md`.

## Wichtige Commands
```bash
flutter run           # App starten (Emulator muss laufen)
flutter pub get       # Dependencies installieren
flutter build apk     # Android APK bauen
flutter doctor        # Setup prüfen
```

## Projekt-Dokumente
- Produkt-Vision & Features → `docs/PRD.md`
- Feature-Tracking → `features/INDEX.md`

## Key Conventions
- **Feature IDs:** PROJ-1, PROJ-2, etc. (fortlaufend)
- **Commits:** `feat(PROJ-X): Beschreibung` / `fix(PROJ-X): Beschreibung`
- **Dateinamen:** `snake_case.dart`
- **Klassen:** `PascalCase`
- **Variablen & Methoden:** `camelCase`
- **Single Responsibility:** Eine Feature Spec pro Feature-File
- **Kein Business Logic in Widgets** — gehört in BLoC
- **Human-in-the-Loop:** Jeder Workflow hat User-Review Checkpoints

## Verfügbare Skills
- `/requirements` → Feature-Anforderungen definieren
- `/architecture` → Technisches Design erstellen
- `/frontend`     → Flutter UI bauen
- `/backend`      → API & Datenspeicher implementieren
- `/qa`           → Feature testen
- `/deploy`       → App veröffentlichen
- `/security`     → Sicherheits-Review
- `/help`         → Status & Orientierung