# General Project Rules

## Feature Tracking
- Alle Features werden in `features/INDEX.md` getrackt — vor jeder Arbeit lesen
- Feature Specs liegen in `features/PROJ-X-feature-name.md`
- Feature IDs sind fortlaufend: INDEX.md für nächste verfügbare Nummer prüfen
- Ein Feature pro Spec-Datei (Single Responsibility)
- Niemals mehrere unabhängige Funktionalitäten in einer Spec kombinieren

## Git Conventions
- Commit-Format: `type(PROJ-X): Beschreibung`
- Types: feat, fix, refactor, test, docs, deploy, chore
- Bestehende Features prüfen: `ls features/ | grep PROJ-`
- Bestehende Screens prüfen: `find lib/features -name "*screen*.dart"`
- Bestehende Services prüfen: `find lib/core/api -name "*.dart"`

## Human-in-the-Loop
- Immer Nutzer-Freigabe einholen bevor Ergebnisse finalisiert werden
- Optionen mit klaren Auswahlmöglichkeiten präsentieren statt offener Fragen
- Niemals zur nächsten Workflow-Phase übergehen ohne Nutzer-Bestätigung

## Status Updates
- `features/INDEX.md` aktualisieren wenn sich Feature-Status ändert
- Status-Feld im Feature Spec Header aktualisieren
- Gültige Status: Planned, In Progress, In Review, Deployed

## File Handling
- IMMER eine Datei lesen bevor sie bearbeitet wird — niemals Inhalt aus dem Gedächtnis annehmen
- Nach Context Compaction Dateien erneut lesen bevor weitergearbeitet wird
- Bei Unsicherheit über aktuellen Projektstatus zuerst `features/INDEX.md` lesen
- `git diff` ausführen um zu prüfen was in dieser Session bereits geändert wurde
- Niemals Import-Pfade, Widget-Namen oder Service-Methoden raten — durch Lesen verifizieren

## Handoffs zwischen Skills
- Nach Abschluss eines Skills den nächsten Skill dem Nutzer vorschlagen
- Format: "Nächster Schritt: `/skillname` ausführen um [Aktion]"
- Handoffs sind immer nutzer-initiiert, niemals automatisch