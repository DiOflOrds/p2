# Software Requirements — P2 "Betriebshärtung" (extension of platform baseline)

*Extends SWR-001–033 (p0 genesis-v1.0, p1 p1-v1.0); numbering continues. Components: BCK/FRT (backend/frontend), TOOL (scripts). Language: English (D011). Status `reviewed` = feasibility (ARCH/DEV context) + verifiability (QM/TEST context) per DoD checklist. v0.1 Sprint 0, T-0004 — G1 pending (Inbox-DR T-0005).*

## Deadline warning (P2-E2, BB-3/R2)

| ID | Requirement | Trace | Verification | Prio | Status |
|---|---|---|---|---|---|
| SWR-034 | The DR notification run shall send one deadline warning e-mail per open decision request whose deadline is within 2 days or exceeded, marked separately on the ticket so each DR receives at most one warning in addition to the initial notification; warning failures are retried on the next run without blocking anything. | STK-014 | Unit tests (threshold, separate marker, no duplicate, retry on failure) | high | reviewed |
| SWR-035 | The deadline warning shall state project, ticket ID, title, and deadline, and — if the DR defines a default option — name it and state that it takes effect once the deadline passes. | STK-014 | Unit tests (mail body content with/without default) | medium | reviewed |

## Catalog check (P2-E4, B7)

| ID | Requirement | Trace | Verification | Prio | Status |
|---|---|---|---|---|---|
| SWR-036 | The catalog tool shall provide a check mode that verifies every catalog entry against its product repository (version consistent with the release tag, referenced files present) and that every product repository under the root with a release tag has a catalog entry; any mismatch is reported per product and exits non-zero. | STK-014 | Unit tests (consistent, version mismatch, missing entry) | high | reviewed |

## Users and inbox hardening (P2-E6, F9 + D001 finding)

| ID | Requirement | Trace | Verification | Prio | Status |
|---|---|---|---|---|---|
| SWR-037 | The backend shall load a user registry (name, role: reader or decider) from the process repository and expose it read-only via API; if no registry exists, a single default decider (the Auftraggeber) applies. | STK-014 | Unit tests (registry parsing, API, default fallback) | medium | reviewed |
| SWR-038 | The decision endpoint shall record the decider on every decision (name in the decision log entry and in the confirmation e-mail) and reject deciders not present with role decider in the user registry; the frontend shall let the human pick the decider identity. | STK-014 | API tests (known decider accepted and logged, unknown/reader rejected) | high | reviewed |
| SWR-039 | The decision inbox shall not offer decision requests that already carry a recorded decision, independent of ticket status, so no decision request can be answered twice. | STK-014 | API tests (decided-but-open DR absent from inbox, second POST rejected) | high | reviewed |

## Traceability

STK-014 ← SWR-034–039, SWR-084 (complete; no orphans). DoD checklist applied per SWR (2026-08-15 RM — feasibility ARCH/DEV context, verifiability QM/TEST context). Catalog-CI wiring (workflow) is an implementation task verified by a real CI run, not a separate SWR. G1 pending. v1.1: +SWR-084 (Betriebs-CR pm/T-0018 aus Auftraggeber via Session, PM-Beschluss B026).

## Nachtrag v1.1 (Auftraggeber via Session, PM-Beschluss B026)

*Betriebs-CR nach dem P2-Abschluss: Entscheidungen tragen Datum **und** Uhrzeit. Keine neue Projekt-Baseline — `p2-v1.0` bleibt Abnahmereferenz. Ergänzt SWR-038 (was der Endpunkt festhält) um den Zeitpunkt; Frist- und Ticketfelder (`frist`, `erstellt`, `geändert`) bleiben reine Datumsfelder, weil Fristen tagesgenau gelten.*

| ID | Requirement | Trace | Verification | Prio | Status |
|---|---|---|---|---|---|
| SWR-084 | The decision endpoint shall record the point in time of every decision as date **and** time of day (`YYYY-MM-DD HH:MM`, server local time) in both the decision log entry and the decision note written into the ticket, so that several decisions taken on the same day remain distinguishable and orderable; the same value shall be used for both writes, and existing date-only entries shall remain valid and readable. | STK-014 | Unit tests (log entry and ticket note carry an identical `YYYY-MM-DD HH:MM` stamp; injected clock verifies the exact value; history endpoint still parses the note) | medium | reviewed |
