# Aufgaben → Bildschirmzeit & Taschengeld — die Idee auf einer Seite

> **Lesefassung.** Diese Datei fasst nur die Ergebnisse zusammen und lässt den Herleitungsweg weg.
> Verbindliche Grundlage für die weitere Arbeit bleibt `DRAFT_family_chore_screentime_economy.md`.

---

## Die Idee

Zwei tägliche Konflikte in Familien mit Kindern (ca. 6–16 Jahre):

- **Der Bildschirmzeit-Streit** — jeden Tag dieselbe Verhandlung über Handy, Tablet, Konsole, TV.
- **Der Aufgaben-Streit** — Haushaltsaufgaben werden erst sichtbar, wenn sie nicht gemacht sind.

Die App koppelt beides: Kind erledigt eine Aufgabe → Elternteil bestätigt per Tipp → Bildschirmzeit-Minuten und/oder Cent landen im virtuellen Sparschwein des Kindes. Später soll das angesparte Guthaben genutzt werden, um den Umgang mit Geld zu lernen.

**Kernfrage:** Wird daraus eine App, die Geld verdient? Die ehrliche Antwort steht weiter unten.

---

## Wie es funktioniert

- **Ein gemeinsames Konto pro Kind**, geführt in zwei Einheiten: Minuten und Cent.
- **Vertrauensbasiert, kein technisches Sperren.** Die App führt das vereinbarte Budget; durchgesetzt wird es mit den Bordmitteln, die Eltern ohnehin haben. Grund: Konsolen bieten keine Schnittstelle für Fremd-Apps, und Apples bzw. Googles Sperr-Wege bringen unkalkulierbare Freigabe- und Rauswurf-Risiken. Ein reiner „Kontostand" deckt Handy, Tablet, Konsole, TV und PC gleich ab.
- **Das Taschengeld ist ein Schuldschein der Eltern an das eigene Kind.** Das liegt bewusst außerhalb jeder Finanzaufsicht — kein echtes Geld, keine Karte, kein Zahlungsverkehr. Sobald echtes Geld oder eine Karte ins Spiel kommt, wird daraus ein Lizenzprojekt (so macht es der Wettbewerber Bling).
- **Elternteil ist alleiniger Kontoinhaber, das Kind ein Unterprofil.** Damit greift die Elternteil-Zustimmung statt der in Deutschland geltenden Altersgrenze 16.

---

## Der ehrliche Knackpunkt

**Die beiden Hälften des Produkts sind nie gleichzeitig wertvoll für dasselbe Kind.**

- „Aufgabe → Bildschirmzeit" funktioniert, solange die Eltern das Gerät kontrollieren — etwa **6–10 Jahre** (90 % der Eltern von 6–9-Jährigen nutzen solche Kontrollen).
- „Taschengeld → Sparen → Anlegen" wird erst mit **12–16** interessant — dann ist der Bildschirmzeit-Hebel praktisch weg und die Eltern verwalten das Gerät kaum noch.

Der „spätere Ausbau" ist also kein Ausbau, sondern ein anderes Produkt für ein anderes Alter — verkauft an einen Kunden, der schon abgewandert ist. **Das ist offen und muss vor der ersten Zeile Code entschieden werden:** entweder auf eine Altersgruppe festlegen, oder den Übergang zwischen beiden Modi als schwerstes Produktproblem behandeln.

---

## Was wir zuerst bauen würden (4–6 Wochen, 1–2 Personen)

Ein Konto pro Kind, eine Aufgabenliste mit Wert je Aufgabe, Ein-Tipp-Freigabe durch die Eltern, eine Nur-Lese-Ansicht fürs Kind. Ein Haushalt.

**Bewusst weggelassen:** Foto-Nachweis (größte Datenschutz-Last), pädagogisches Drei-Ebenen-Modell, Modus-Umschalter, Haushalts-übergreifende Synchronisation, Finanzbildung/Simuliertes Anlegen, kostenlose/bezahlte Tarife zum Start. Jeder Punkt ist eine Streichung, keine Abschwächung.

---

## Verdient das Geld?

**Auf heutiger Datenlage: eine reine Abo-App ohne Karte, nur für den DACH-Raum, trägt zwei Personen nicht.**

Die Zahlen dahinter, konsistent gerechnet:

| Größe | Wert |
|---|---|
| Preisanker deutsche Familien-Apps | ~30 €/Jahr |
| Anteil Installation → zahlend (Westeuropa) | ~2 % |
| Tatsächlicher Umsatz je Zahler, Jahr 1 | ~23–25 € |
| Kosten bezahlte Werbung je zahlendem Haushalt | 125–225 € |
| Break-even für zwei Personen | ~5.900–7.500 zahlende Haushalte |

- **Bezahlte Werbung ist tot** — sie kostet das ~5-Fache dessen, was ein Kunde je einbringt.
- **Der organische Weg** bräuchte für 5.000 zahlende Haushalte rund **250.000 Installationen** — und wegen hoher Kündigungsrate jedes Jahr aufs Neue. Das ist eine Top-Reichweiten-Marke im deutschen Eltern-Web, nicht ein Nebenprojekt.

### Die drei Wege nach vorne

| Weg | Was er braucht | Einschätzung |
|---|---|---|
| **1. Kosten unter den Umsatz** | Eine Person, Teilzeit, geringe Ausgaben. Break-even sinkt auf ~2.000–3.000 Haushalte. | Der einzige Weg, der ohne neues Kapital in der vorhandenen Zeit erreichbar ist. Kein Unternehmen — ein profitables Produkt. |
| **2. Umsatz je Kunde 3–5× anheben** | Eine echte Karte (Interchange-Einnahmen). Genau das, was die Schuldschein-Entscheidung ausschließt. | Wird zum Lizenz- und Kapitalprojekt statt einem Bau. |
| **3. Institutioneller Vertrieb** | Sparkassen-White-Label, Arbeitgeber-Benefits, Krankenkassen-Programme. | Löst das Kunden-Kosten-Problem komplett, aber die Vertriebszyklen im deutschen Gesundheitswesen sind länger als die verfügbare Zeit. Das verkauft man *nach* Consumer-Traktion. |

---

## Was das MVP beantworten soll (mit Abbruch-Bedingung)

1. **Übersteht der Mechanismus Woche 4?** Belohnungs-Müdigkeit ist die Standard-Krankheit der Kategorie. Abbruch, wenn die Aktivität in einer Testgruppe von 20–30 Familien bis Woche 4 zusammenbricht.
2. **Zahlt ein Elternteil, wenn es überall eine kostenlose Alternative gibt?** Abbruch, wenn eine Bezahlschranke unter ~2 % konvertiert.
3. **Bewegt sich organische Gewinnung überhaupt?** Zuerst die Suchnachfrage testen (Mediennutzungsvertrag, Bildschirmzeit Streit, Taschengeld Tabelle) — vor dem Aufbau der Inhalte.
4. **Zeigt sich das Altersproblem in echten Gruppen?** Jede Kennzahl von Tag 1 an nach Altersband trennen.

---

## Zu entscheiden

1. **Altersgruppe:** eine, oder expliziter Zwei-Modus-Übergang? Vor dem Code.
2. **Welcher der drei Geld-Wege?** Das ist eine Entscheidung, die das Konzept nicht abnehmen kann.
3. **Ist der schwache Schutz vor Nachbau akzeptabel?** Nichts hier ist technisch schwer zu kopieren; das einzige dauerhafte Gut ist die ausgehandelte Regel-Historie der Familie.
