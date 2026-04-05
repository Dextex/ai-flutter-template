# QA Testergebnisse Template

Diesen Abschnitt ans ENDE der Feature Spec `/features/PROJ-X.md` hinzufügen:

```markdown
---

## QA Testergebnisse

**Getestet am:** JJJJ-MM-TT
**Emulator/Gerät:** [z.B. sdk gphone16k x86 64 / Pixel 8 API 35]
**Tester:** QA Engineer (AI)

### Acceptance Criteria Status

#### AC-1: [Kriterium Name]
- [x] Teilkriterium bestanden
- [ ] BUG: Teilkriterium nicht bestanden (beschreiben was schiefgelaufen ist)

#### AC-2: [Kriterium Name]
- [x] Alle Teilkriterien bestanden

### Edge Cases Status

#### EC-1: [Edge Case Name]
- [x] Korrekt behandelt

#### EC-2: [Edge Case Name]
- [ ] BUG: Nicht behandelt (Erwartet vs. Tatsächlich beschreiben)

### Sicherheits-Audit Ergebnisse
- [x] Keine API-Keys im Code
- [x] Nur HTTPS-Verbindungen
- [x] Eingabe-Validierung funktioniert
- [x] Sensible Daten sicher gespeichert
- [ ] BUG: [Sicherheitsproblem beschreiben]

### Gefundene Bugs

#### BUG-1: [Bug Titel]
- **Schweregrad:** Kritisch | Hoch | Mittel | Niedrig
- **Reproduktionsschritte:**
  1. [Screen/Aktion]
  2. [Aktion]
  3. Erwartet: [Was sollte passieren]
  4. Tatsächlich: [Was passiert stattdessen]
- **Screenshot:** [falls visueller Bug]
- **Priorität:** Vor Deployment fixen | Im nächsten Sprint | Nice to have

### Zusammenfassung
- **Acceptance Criteria:** X/Y bestanden
- **Gefundene Bugs:** N gesamt (K kritisch, H hoch, M mittel, N niedrig)
- **Sicherheit:** [Bestanden / Probleme gefunden]
- **Production Ready:** JA / NEIN
- **Empfehlung:** [Deployen / Erst Bugs fixen]
```