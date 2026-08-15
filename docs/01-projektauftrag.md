# Projektauftrag P2 — „Betriebshärtung" (v0.1, zur G0-Freigabe)

*2026-08-15, PL. Eingang per Intake (`process/process/intake.md`), Projektwahl durch den Auftraggeber (Session-Dialog): Betriebshärtung. G0-Freigabe: Inbox-DR T-0001.*

## Was und Warum

P0 hat das Team gebaut, P1 den Leitstand — P2 macht den **Regelbetrieb robust**. Quellen sind ausschließlich bekannte, dokumentierte Lücken: das Betriebs-Backlog aus der P1-Schluss-Retro (Runbook Kap. 7) und der P0-Überhang. Kein Neuland, dafür messbare Härtung an Stellen, die im Erstbetrieb real geschmerzt haben (SMTP-Anlauf, abgelaufene DR-Fristen, fehlende Copilot-CLI).

**Zielprodukt-Typ:** Plattform-/Prozessverbesserung (SW, F6) · **Nutzerkreis:** Auftraggeber, perspektivisch weitere Personen (F9) · **Vertraulichkeit:** privat (F10) · **Budget:** D012-Mechanik unverändert, Ziel weiterhin 0 € API.

## Epics

| Epic | Inhalt | Quelle |
|---|---|---|
| P2-E1 | Runbook-Checkliste „externen Dienst einrichten" (2FA → Secret/Env → Testlauf → Empfänger prüfen) | BB-2 (R1) |
| P2-E2 | Frist-Warnung im DR-Benachrichtigungslauf (DRs nahe/über Frist erneut mailen) — requirements-first | BB-3 (R2) |
| P2-E3 | Geräteregister um Soll-Toolchain je PoC ergänzen (u. a. Copilot CLI, stützt BB-1) | BB-4 (R3) |
| P2-E4 | Katalog-CI: Produktkatalog-Eintrag automatisch prüfen (dokumentierte Abweichung aus P0/T-0056 einlösen) | B7 |
| P2-E5 | Aufwandsschätzung light: Schätzfeld im Ticket, Plan/Ist im Sprint-Report | B3 |
| P2-E6 | Rechte-/Nutzerverwaltung light: Nutzer-Registry + Lese-/Entscheidungsrechte in Mission Control (vorbereitend für F9) | F9 |

## Abnahmekriterien

1. BB-2/3/4 umgesetzt, im Runbook bzw. Geräteregister nachvollziehbar; Betriebs-Backlog entsprechend fortgeschrieben.
2. **Frist-Warnung real nachgewiesen:** mindestens eine Warnmail an die D008-Adresse (erledigt zugleich BB-6).
3. Katalog-CI als grünes Gate in mindestens einem Repo.
4. Aufwandsschätzung in mindestens einem Sprint gelebt (Schätzung vs. Ist im Report).
5. Requirements-first für alle SW-Änderungen (SWR + Matrix ohne Lücken), alle Gates als Inbox-DRs mit Frist-Default.

## Rahmen

2–3 Sprints. Playbook, Ticket-Board, Gates G0/G1/G4 (G2 nur falls Architektur-Delta nötig — erwartet: nein, E6 entscheidet), Baselines als Tags + Manifest. Rollen teamweit (Registry), Sandbox pusht nie (D007/p0).
