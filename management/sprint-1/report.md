# Sprint-1-Report — P2 „Betriebshärtung" (PL)

*2026-08-15. Sprint-Motto: „Kern-Härtung". An: Mensch (G4 via Inbox-DR T-0012). 6/6 Tickets done.*

## Sprint-Ziel: erreicht — alle 6 SWRs umgesetzt und verifiziert

| Ticket | Ergebnis |
|---|---|
| T-0006 | Planning (SWR-Zuordnung, Nachweisliste) |
| T-0007 | **Frist-Warnung live** (SWR-034/035): 2-Tage-Schwelle, eigener Marker, Default-Hinweis, Retry; +5 Tests |
| T-0008 | **Katalog-Check** (SWR-036): Einträge ↔ Repos/Tags/Versionen beidseitig; Gate in abschluss.cmd [2/5] + platform-CI-Step; +3 Tests |
| T-0009 | **Registry + Entscheider-Pflicht + Inbox-Härtung** (SWR-037–039): nutzer.yaml, /api/nutzer, Entscheider in Log und Mail, Leser/Unbekannte 403, entschiedene DRs raus aus der Inbox (D001-Befund), Frontend-Auswahl; +4 Tests |
| T-0010 | Runbook Kap. 8: Checkliste „externen Dienst einrichten" (7 Schritte, alle Fallen aus dem realen SMTP-Anlauf) |
| T-0011 | Geräteregister: Soll-Toolchain je Einsatzzweck (Copilot-Zeile stützt BB-1) |

## KPIs

Tests **126 → 138** (platform) + 42 (produkt) grün · Matrix **39 SWRs / 0 Lücken** · Betriebs-Backlog: BB-2/3/4/6 erledigt, offen nur BB-1 (Copilot CLI) + BB-5 (PAT-Termine) · 0,00 € API · Statuswechsel 100 % Skript-Route.

## Kriterienbilanz

K1 (BB umgesetzt + nachvollziehbar) ✓ · K2 (Warnmail real): Mechanik verifiziert (Tests), **realer Zustellnachweis steht aus** — ergibt sich am nächsten DR nahe Frist · K3 (Katalog-CI): lokal aktiv; CI-Step wartet auf PAT-Erweiterung (Mensch) · K4 (Aufwandsschätzung): Sprint 2 · K5 (requirements-first, Gates Inbox/Default) ✓.

## QM-Abschnitt (ungefiltert)

1. G1 lief per Session-Dialog statt Inbox (zulässig, Präzedenz P0-D009) — der Inbox-Zähler wächst dafür mit diesem G4-DR. 2. CI-Katalog-Gate ist erst nach der PAT-Erweiterung grün — bis dahin bricht der neue CI-Lauf beim p2/process/produkt-Checkout ab (klare Meldung). 3. D001-Duplikat von heute ist durch SWR-039 künftig unmöglich — Wirksamkeit per API-Test belegt, realer Gegencheck empfohlen (Stichprobe).

## Entscheidungsbedarf: G4 Sprint 1 → Inbox-DR T-0012
