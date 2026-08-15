# Retrospektive Sprint 1 — P2 (COACH)

*2026-08-15. Max. 3 Punkte.*

**Gut:** Der Sprint bestand fast nur aus Härtungen, die der Betrieb selbst bestellt hat (T-0002-Befund, D001-Doppelklick, P1-Retro) — kürzester Weg von Schmerz zu Anforderung zu Test, alle am selben Tag.

**Erkenntnisse → Maßnahmen (Sprint 2):** 1. **Windows-Blindflug beenden:** Zwei Befunde (Mail-Test, Pfadtrenner, cmd-Klammerfalle) entstanden, weil die Suite nur auf Linux lief — Sprint-2-Ticket: abschluss.cmd-Trockenlauf bzw. Suite-Lauf auf dem Team-Node als fester Gate-Schritt vor jedem G4. 2. **Hermetik als Regel:** Testklassen mit Außenwirkung (Netz, Mail, Env) bekommen die SMTP-Scrub-Technik als dokumentiertes Muster in die Wissensbasis (Gold-Beispiel aus T-0002). 3. **Session-Gates sparsam:** G1 im Dialog war pragmatisch richtig, aber der Regelkanal bleibt die Inbox — PL stellt Gate-DRs künftig VOR Sprint-Start-Aufrufen ein, damit die Antwort asynchron da ist.
