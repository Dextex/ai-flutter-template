# Frontend Checkliste

Vor jedem Review diese Liste abhaken:

# Frontend Implementation Checklist

Vor dem Abschließen des Frontends:

## Material Design Widgets
- [ ] Material Design Widgets für JEDES UI-Element geprüft
- [ ] Keine custom Duplikate von Standard-Material-Widgets erstellt
- [ ] Fehlende Funktionalität als Komposition von Material-Primitives gebaut

## Bestehender Code
- [ ] Bestehende Widgets geprüft via `find lib/shared/widgets -name "*.dart"`
- [ ] Bestehende Widgets wo möglich wiederverwendet

## Design
- [ ] Design-Präferenzen mit Nutzer geklärt (falls keine Mockups)
- [ ] Screen-Struktur aus dem Solution Architect Tech Design umgesetzt

## Implementierung
- [ ] Alle geplanten Screens und Widgets implementiert
- [ ] BLoC für alle State-Änderungen genutzt (kein setState für Business Logic)
- [ ] Lade-Zustände implementiert (CircularProgressIndicator / Skeleton)
- [ ] Fehler-Zustände implementiert (verständliche Fehlermeldungen für Nutzer)
- [ ] Leere Zustände implementiert ("Noch keine Daten" Meldungen)

## Qualität
- [ ] `const` Konstruktoren wo möglich genutzt (Performance)
- [ ] Verschiedene Bildschirmgrößen getestet (klein: 360px, groß: 412px)
- [ ] Keine hardcodierten Farben — Theme-Farben genutzt
- [ ] Dart: Keine Analyse-Fehler (`flutter analyze` fehlerfrei)

## Verifikation (vor Abschluss ausführen)
- [ ] `flutter build apk --debug` erfolgreich
- [ ] Alle Acceptance Criteria aus der Feature Spec in der UI umgesetzt
- [ ] `features/INDEX.md` Status auf "In Progress" aktualisiert

## Abschluss
- [ ] Nutzer hat UI im Emulator geprüft und freigegeben
- [ ] Code in Git committet