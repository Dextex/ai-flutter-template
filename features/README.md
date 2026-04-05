# Features — Dokumentation

Dieser Ordner enthält alle Feature-Spezifikationen des Meal-Planer Projekts.

## Struktur

```
features/
├── INDEX.md           ← Übersicht aller Features mit Status
├── README.md          ← Diese Datei
├── PROJ-1-*.md        ← Feature Spec (erstellt von /requirements)
├── PROJ-2-*.md
└── ...
```

## Feature-Lebenszyklus

Jedes Feature durchläuft diese Phasen:

```
🔵 Planned      → /requirements hat Spec erstellt
🟡 In Progress  → /frontend oder /backend arbeiten daran
✅ Deployed     → /deploy hat Feature veröffentlicht
```

## Feature Spec Aufbau

Jede `PROJ-X.md` Datei enthält:

| Abschnitt | Erstellt von |
|---|---|
| User Stories | /requirements |
| Acceptance Criteria | /requirements |
| Edge Cases | /requirements |
| Tech Design | /architecture |
| QA Testergebnisse | /qa |
| Deployment Status | /deploy |

## Neues Feature hinzufügen

In Claude Code (VS Code):
```
/requirements Ich möchte [Feature-Beschreibung] bauen.
```

Der Requirements-Skill übernimmt den Rest automatisch.

## Feature IDs

Format: `PROJ-X` wobei X fortlaufend nummeriert wird.
Beispiel: PROJ-1, PROJ-2, PROJ-3 ...

Die nächste verfügbare ID steht immer in `INDEX.md`.
