# Sprint-1-Plan P2 „Betriebshärtung" (PL)

*2026-08-15, nach G1 (D002, `p2-req-v1.0`). Sprint-Ziel: Kern-Härtung — alle 6 SWRs umgesetzt und verifiziert, E1/E3-Doku steht, Betriebs-Backlog fortgeschrieben.*

| Ticket | Prozess | Rolle | Inhalt | SWR |
|---|---|---|---|---|
| T-0006 | man3 | pl | Dieses Planning | — |
| T-0007 | swe3 | dev | Frist-Warnung in dr_benachrichtigung (Schwelle 2 Tage, eigener Marker, Default-Hinweis) + Tests | 034, 035 |
| T-0008 | swe3 | dev | catalog.py --check (Einträge ↔ Repos/Tags/Versionen, fehlende Einträge) + Tests; Gate in abschluss.cmd und platform-CI | 036 |
| T-0009 | swe3 | dev | Nutzer-Registry (process/team/nutzer.yaml, API), Entscheider-Pflicht im Decision-Endpoint (Log + Mail), Inbox bietet entschiedene DRs nicht mehr an; Frontend-Auswahl + Tests | 037–039 |
| T-0010 | sup8 | cm | Runbook-Checkliste „externen Dienst einrichten" (Lehre T-0002/SMTP-Anlauf) | E1/BB-2 |
| T-0011 | sup8 | cm | Geräteregister: Soll-Toolchain je Einsatzzweck (u. a. Copilot CLI → BB-1) | E3/BB-4 |

## Nachweise am Sprint-Ende

Suiten + Matrix (39 SWRs) grün · Frist-Warnung real am nächsten offenen DR (K2) · Katalog-Gate lokal aktiv, CI nach PAT-Erweiterung (K3) · BB-2/3/4 im Runbook als erledigt fortgeschrieben (K1) · G4 via Inbox mit Frist-Default (K5). E5 (Aufwandsschätzung) folgt in Sprint 2.
