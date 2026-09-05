# 💰 Frauengesundheit — die Wirtschaftlichkeit, belastbar gerechnet

## 📌 Status

| | |
|---|---|
| **Status** | `DRAFT` — v1 |
| **Datum** | 2026-09-04 |
| **Ersetzt** | Im Vorgängerkonzept `DRAFT_frauengesundheit_selbstaendigkeit.de.md` (v7) die Abschnitte **„Die Rechnung, die die Entscheidung trägt"**, **„Die Break-even-Leiter"**, **„Die drei Schwellen"** und die Elternzeit-Rechnung |
| **Anlass** | Zwei Reviews haben festgestellt, dass die bisherige Rechnung auf einer **erfundenen Randbedingung** (gesperrter Dienstag, gesperrte Abende) und auf **geschätzten, nie aufgeschlüsselten Betriebskosten** stand |
| **Adversarial Review** | ✅ **nachgeholt** · `VERDICT: REVISE` · 14 Befunde, davon fünf ergebnisverändernd · **`reviewer_model: claude-opus-5`** — Modellidentität mit dem Autor nicht ausschließbar, also faktisch **same-model-fallback** |
| **Status der Zahlen** | **v2 nach Review.** Die Arithmetik wurde Zelle für Zelle fremdgeprüft und überwiegend bestätigt; korrigiert wurden **Bilanzierung** (Rentenanwartschaft als Ertrag verbucht), der Job-KV-Effekt, die Umsatzsteuer-Folgerung, der Break-even und **die Wachstumsempfehlung** |
| **Ergänzt** | `DRAFT_frauengesundheit_qualifikationsweg.de.md` (v4) — dort steht der Weg zur Erlaubnis, hier was er einbringt |

---

# 🎯 Was hier anders gemacht wird

| | bisher | jetzt |
|---|---|---|
| Zeitfenster | 4 Vormittage (Dienstag „gesperrt") | **5 Vormittage + gelegentlich Abend/Samstag** |
| Betriebskosten | 2.500 € / 6.000 € — „geschätzt, nicht aufgeschlüsselt" | **von unten aufgebaut, Position für Position** |
| Preis | 100 € gesetzt | **gegen regionale Marktpreise geprüft** |
| Vergleich | nur „ohne Erlaubnis" | **beide Spalten: ohne und mit Heilpraktikererlaubnis** |
| Ergebnisgröße | Jahresnetto | **zusätzlich Netto pro Arbeitsstunde** — gegen den Verlagsjob |
| Marktgröße | keine | **Branchenkennzahlen und Wettbewerbsdichte, mit Vorbehalt** |

> ⚠️ **Was diese Version nicht kann:** Sie prüft die **Angebotsseite** belastbar. Die **Nachfrageseite** bleibt unbelegt — es gibt weiterhin null Minuten Kundenkontakt. Am Ende steht deshalb keine Zahl, sondern eine Schwelle: *ab wie vielen Kundinnen trägt es, und ist das plausibel?*

---

# 📐 Die Parameter — jeder mit Status

| # | Parameter | Wert | Status |
|---|---|---|---|
| P1 | Vormittagsfenster | 5 × 5,5 h = **27,5 h/Woche** | **Annahme** — setzt Betreuung Mo–Fr ~8:00–13:30 voraus |
| P2 | Job inkl. Pendeln | **12–18 h**, je nach Zahl der Fahrten nach München | **Unbekannt** — offene Frage Nr. 1 des Vorgängerkonzepts |
| P3 | Haushalt, Erledigungen im kinderfreien Fenster | −2 h/Woche | Annahme |
| P4 | Unbezahlt je Termin (Vor-/Nachbereitung, Akquise, Buchhaltung) | ~1 h | aus v7 übernommen (dort 3 h bei 3 Terminen) |
| P5 | Abend / Samstag, **gelegentlich** | +1–3 h/Woche | **vom Nutzer bestätigt** („kann auch mal") |
| P6 | Arbeitswochen | **34–36**, gerechnet mit 35 | aus v7; ~14 Wochen bayerische Schulferien |
| P7 | Preis ohne Erlaubnis | 100 € / 90 Min | aus v7 |
| P8 | Preis mit HP-Erlaubnis | **120 € / 90 Min** | **marktgeprüft, konservativ** — siehe unten |
| P9 | Grenzsteuersatz | **40 %** | abgeleitet aus ~140 k Zusammenveranlagung; v7 rechnete 37 % · **Kirchensteuer offen (+~3 pp)** |
| P10 | Geringfügigkeitsgrenze (RV-Freiheit, § 5 Abs. 2 SGB VI) | **7.236 €/Jahr** | ✅ verifiziert (603 €/Monat, 2026) |
| P11 | KV/PV-Satz freiwillig Versicherte | **20,85 %** (14,6 + 2,9 Zusatz + 3,35 Pflege bei 2 Kindern) | ✅ verifiziert |
| P12 | Mindestbemessungsgrundlage GKV 2026 | **1.318,33 €/Monat** | ✅ verifiziert |
| P13 | Kleinunternehmergrenze § 19 UStG | 25.000 € Vorjahr / 100.000 € laufend | ✅ verifiziert |
| P14 | Job brutto / netto | 12.000 € / **~6.000 €** | aus v7 |

> **Zu P11:** Eine verbreitete Quelle rechnet die Pflegeversicherung bei zwei Kindern mit 3,1 % (0,25 pp × 2). Das ist falsch: Der Abschlag gilt **ab dem zweiten** Kind, bei zwei Kindern also einmal → **3,35 %**. ([BMG](https://www.bundesgesundheitsministerium.de/beitraege), [Rechengrößen 2026](https://www.krankenkassen.de/gesetzliche-krankenkassen/system-gesetzliche-krankenversicherung/sozialversicherung-rechengroessen-beitragsbemessungsgrenze-versicherungspflichtgrenze/rechengroessen-2026/))

---

# ⏱️ Kapazität — wie viele Termine passen wirklich?

Die Zahl hängt an **P2**, der Zahl der Fahrten nach München. Deshalb zwei Spalten statt eines Mittelwerts:

| | **2 Fahrten** (Job kompakt) | **4 Fahrten** (Job verteilt) |
|---|---|---|
| Fenster | 27,5 h | 27,5 h |
| − Job inkl. Pendeln | −12 bis −14 h | −16 bis −18 h |
| − Haushalt / Erledigungen | −2 h | −2 h |
| + Abend / Samstag, gelegentlich | +1 bis +3 h | +1 bis +3 h |
| **= verfügbar** | **12,5 – 16,5 h** | **8,5 – 12,5 h** |
| ÷ 2,5 h je Termin (90 Min + 1 h unbezahlt) | | |
| **= Termine/Woche** | **5,0 – 6,6** | **3,4 – 5,0** |

> **Ergebnis: 3,5 – 6,5 Termine pro Woche.** Der Vorgänger rechnete mit 3, die verworfene v3 dieses Dokuments mit 6–8. Beide Ränder waren falsch.
>
> ⚠️ **Ein einziges Telefonat mit dem Verlag halbiert diese Spanne.** Es ist die billigste Informationsbeschaffung im ganzen Vorhaben.

---

# 🏢 Betriebskosten — zum ersten Mal aufgeschlüsselt

Das Vorgängerkonzept nennt 2.500 € (3 Termine) und 6.000 € (8 Termine) und markiert sie selbst als „geschätzt, nicht aufgeschlüsselt". Von unten aufgebaut:

| Position | schlank | normal | Ausbau (5–6,5 Termine) |
|---|---|---|---|
| **Raum** — regelmäßige Anmietung, 1 Tag/Woche ab **195 €/Monat** in München; Dachau tendenziell darunter; stundenweise ab 18 €/h, Tagespauschale ~120 € | 1.200 € *(vergünstigt bei der Bekannten)* | **2.340 €** | 3.900 – 4.700 € *(2 Tage)* |
| Berufshaftpflicht Heilpraktiker | 100 € | 150 € | 250 € |
| Berufsverband (BDH/FDH o. ä.) | 0 € | 250 € | 250 € |
| Website, Domain, Mail, Terminbuchung | 150 € | 250 € | 350 € |
| Buchhaltung / Steuerberater (EÜR) | 0 € *(selbst)* | 400 € | 700 € |
| Material, Verbrauch, Fachliteratur | 200 € | 300 € | 500 € |
| Fortbildung (laufend) | 300 € | 600 € | 900 € |
| Fahrt, Telefon, Porto, Büro | 200 € | 300 € | 450 € |
| Marketing, Vortragsräume, Flyer | 150 € | 250 € | 500 € |
| **Summe** | **≈ 2.300 €** | **≈ 4.840 €** | **≈ 7.800 – 8.600 €** |

> Quellen zur Raummiete: [Praxis- und Seminarräume München, stunden-/tageweise](https://ganzheitliche-therapie-muenchen.de/praxisraeume/praxisraeume-seminarraeume-mieten/) (18 €/h · 120 €/Tag · **195 €/Monat bei 1 Tag/Woche**), [Praxisraum München](https://www.praxisraum-muenchen.de/)

> ⛔ **Erster wesentlicher Befund: Die bisherigen 2.500 € sind der *schlanke* Fall, nicht der Erwartungswert.**
> Sie setzen voraus, dass der Raum vergünstigt ist, die Buchhaltung selbst gemacht wird, kein Berufsverband und wenig Fortbildung. Realistisch sind **~4.800 €** — fast das Doppelte. Das verschiebt jede Folgezeile.

**Die Zwischenwerte in den Rechnungen unten, hergeleitet:**

| Auslastung | Betriebskosten | Herleitung |
|---|---|---|
| 3 Termine, ohne Erlaubnis | **4.840 €** | Spalte „normal" |
| 3 Termine, mit Erlaubnis | **5.200 €** | + höhere Berufshaftpflicht und Fachfortbildung |
| 5 Termine | **6.500 – 7.000 €** | zweiter Raumtag (+~1.560 €) plus anteilig höhere Sachkosten |
| 6,5 Termine | **8.000 €** | Spalte „Ausbau", mittlerer Wert |

> ⚠️ Diese Zwischenwerte sind **interpoliert, nicht erhoben.** Der Raum ist dabei der einzige Posten mit echtem Sprungcharakter — alles andere skaliert weich.

---

# 💵 Marktpreise — hält der angesetzte Preis?

| Leistung | Region München/Umland |
|---|---|
| Heilpraktiker Erstanamnese (60–90 Min) | **90 – 180 €** |
| Heilpraktiker Folgebehandlung (60 Min) | **90 – 130 €** |
| Typischer Stundensatz | ~120 € / 50 Min |
| GebüH (amtliches Verzeichnis) | von 1985, zuletzt 2002 an die Inflation angepasst — **die meisten liegen darüber** |

> Quellen: [Naturheilpraxis Wehner München](https://www.naturheilpraxis-wehner-muenchen.de/heilpraktiker-kosten-muenchen), [Praxis Grünerleben](https://www.praxis-gruenerleben.de/leistungen-und-honorar/honorar-preise/), [Naturheilpraxis Dietlmeier, Gröbenzell](https://www.naturheilpraxis-dietlmeier.de/preise/), [Praxis für Integrative Medizin](https://www.praxisim.de/preise)

**Bewertung:** **120 € für 90 Minuten liegt am unteren Rand des regionalen Marktes** — das entspricht 80 €/Stunde gegen typische 90–130 €/Stunde. Für eine neu startende Praxis in Dachau ist das angemessen konservativ. Die 100 € des Vorgängerkonzepts gelten für die Variante **ohne** Erlaubnis und sind dort ebenfalls plausibel, weil dort kein Heilberufsstatus den Preis stützt.

> ⚠️ Diese Preise stammen von etablierten Praxen in und um München. Eine neue Praxis startet typischerweise darunter und braucht Jahre bis zum Marktpreis. **120 € ist ein Zielwert, kein Startwert.**

---

# 🧮 Die Rechnung

Alle Zeilen: 35 Arbeitswochen, Grenzsteuersatz 40 %, Rentenversicherungsbeiträge als Sonderausgaben vor Steuer abgezogen, Krankenversicherung 0 € solange nebenberuflich.

## Spalte 1 — ohne Erlaubnis (Wissensvermittlung, 100 €)

| | 3 Termine | 3 Termine, schlanke Kosten | 5 Termine | 6,5 Termine |
|---|---|---|---|---|
| Umsatz | 10.500 € | 10.500 € | 17.500 € | 22.750 € |
| − Betriebskosten | −4.840 € | −2.300 € | −6.500 € | −8.000 € |
| **= Gewinn** | **5.660 €** | **8.200 €** | **11.000 €** | **14.750 €** |
| Rentenversicherung 18,6 % *(Lehrtätigkeit)* | **0 €** — unter 7.236 € | −1.525 € | −2.046 € | −2.744 € |
| Krankenversicherung | 0 € | 0 € | 0 € *(Gewinn < Gehalt)* | **−5.578 €** *(hauptberuflich)* |
| Einkommensteuer 40 % | −2.264 € | −2.670 € | −3.582 € | −2.571 € |
| = netto Selbständigkeit | 3.396 € | 4.005 € | 5.372 € | 3.857 € |
| + Wegfall eigener KV-Abzug im Job, **nach Steuer** *(nur bei hauptberuflich)* | — | — | — | **+~750 €** |
| **= netto effektiv** | **≈ 3.396 €** | **≈ 4.005 €** | **≈ 5.372 €** | **≈ 4.607 €** |

> ⚠️ **Selbstprüfung, Fehler 1:** Die letzte Zeile fehlte in der ersten Fassung. Wird die Selbständigkeit als hauptberuflich eingestuft, ist das Angestelltenverhältnis krankenversicherungsfrei (§ 5 Abs. 5 SGB V) — der eigene KV-Abzug vom Gehalt entfällt, das Job-Netto steigt um ~1.250 €. Das galt in Spalte 2 und wurde in Spalte 1 vergessen. **Folge: Der Vorteil der Erlaubnis bei 6,5 Terminen ist ~1.250 € kleiner als zunächst gerechnet.**

## Spalte 2 — mit Heilpraktikererlaubnis (120 €)

| | 3 Termine | 5 Termine · nebenberuflich | 5 Termine · hauptberuflich | 6,5 Termine |
|---|---|---|---|---|
| Umsatz | 12.600 € | 21.000 € | 21.000 € | 27.300 € |
| − Betriebskosten | −5.200 € | −7.000 € | −7.000 € | −8.000 € |
| **= Gewinn** | **7.400 €** | **14.000 €** | **14.000 €** | **19.300 €** |
| Rentenversicherung | **0 €** — Heilpraktiker fallen nicht unter § 2 SGB VI | 0 € | 0 € | 0 € |
| Umsatzsteuer | **0 €** — heilkundliche Umsätze zählen nicht in den Gesamtumsatz des § 19 UStG | 0 € | 0 € | **0 €** |
| Krankenversicherung | 0 € | 0 € | −5.421 € | −6.526 € |
| Einkommensteuer 40 % | −2.960 € | −5.600 € | −3.432 € | −5.110 € |
| = netto Selbständigkeit | 4.440 € | **8.400 €** | 5.147 € | 7.664 € |
| + Wegfall eigener KV-Abzug im Job, **nach Steuer** *(nur bei hauptberuflich)* | — | — | +~750 € | +~750 € |
| **= netto effektiv** | **≈ 4.440 €** | **≈ 8.400 €** | **≈ 5.897 €** | **≈ 8.414 €** |

> ⚠️ **Review-Korrektur:** Der Wegfall des eigenen KV-Abzugs vom Gehalt beträgt brutto ~1.236 €, ist aber **Sonderausgabe nach § 10 Abs. 1 Nr. 3 EStG** — fällt er weg, steigt das zu versteuernde Einkommen entsprechend. Nach 40 % Steuer bleiben **~750 €**. Die erste Fassung buchte den Bruttowert, obwohl sie die Sonderausgabenlogik bei der freiwilligen Krankenversicherung korrekt anwandte. Inkonsistenz, kein Rechtsirrtum.

## Spalte 3 — die Variante, die der Review sichtbar gemacht hat: **weniger Termine, höherer Preis**

| | **3 Termine · 150 €** |
|---|---|
| Umsatz (3 × 35 × 150 €) | 15.750 € |
| − Betriebskosten | −5.200 € |
| **= Gewinn** | **10.550 €** |
| vs. Gehalt 12.000 € | **darunter** ✅ |
| Zeitaufwand 7,5 h vs. 10 h Job | **darunter** ✅ |
| Rentenversicherung · Umsatzsteuer · Krankenversicherung | 0 € · 0 € · **0 €** |
| Einkommensteuer 40 % | −4.220 € |
| **= netto** | **≈ 6.330 €** |
| **Arbeitsstunden** | **263 h** |
| **= netto je Stunde** | **≈ 24,1 €** |
| benötigte Neukundinnen/Jahr | **18 – 35** |

> **Zur Umsatzsteuer:** Steuerfreie Umsätze nach § 4 Nr. 14 UStG sind bei der Ermittlung des Gesamtumsatzes nach § 19 Abs. 2 Satz 1 Nr. 1 UStG **nicht zu berücksichtigen** — die 25.000-€-Grenze zählt sie also gar nicht mit. ([BMF-Schreiben 18.03.2025 zur Neufassung § 19 UStG](https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Umsatzsteuer/Umsatzsteuer-Anwendungserlass/2025-03-18-sonderregelung-kleinunternehmer.pdf), [smartsteuer — Heilberufe](https://www.smartsteuer.de/online/lexikon/h/heilberufe/))
> ⚠️ **Aber nur für den heilkundlichen Anteil.** Vorträge, Prävention und Wellness bleiben steuerpflichtig und zählen mit. Bei einem gemischten Angebot muss der Steuerberater die Grenze ziehen.

---

# 🔍 Fünf Befunde, die aus dieser Rechnung folgen

## 1. Die Umsatzsteuer war nie das Problem — sie war ein Artefakt

Das Vorgängerkonzept ließ Szenario B an der Kleinunternehmergrenze scheitern (28.000 € Umsatz → ~4.470 € Margenverlust). **Mit korrigiertem Zeitfenster wird diese Grenze aber gar nicht erreicht:** 6,5 Termine × 35 × 100 € = 22.750 €, also unter 25.000 €. Die 28.000 € gehörten zu einem 8-Termine-Szenario, das nur ohne Job erreichbar war.

> ⚠️ **Review-Korrektur — die erste Fassung zog hier den falschen Schluss.** Sie schrieb, der Umsatzsteuervorteil sei „im relevanten Bereich wirkungslos" und greife erst jenseits von ~7,5 Terminen à 100 €. Zwei Fehler:
> 1. **Rechenfehler:** 25.000 € ÷ (35 × 100 €) = **7,14 Termine**, nicht 7,5.
> 2. **Falsche Spalte, und das ist der eigentliche Fehler.** Der Vorteil betrifft die Erlaubnis, also die **120-€-Welt**. Dort liegt die Grenze bei 25.000 ÷ (35 × 120) = **5,95 Termine**. Die Zelle „6,5 Termine mit Erlaubnis" weist **27.300 € Umsatz** aus — 2.300 € über der Grenze — und bucht dort 0 € Umsatzsteuer allein gestützt auf § 4 Nr. 14 a UStG.
>
> **Der Umsatzsteuervorteil ist also nicht wirkungslos, sondern tragend in genau der Zelle mit dem besten Ergebnis.** Richtig bleibt nur: Für die Variante *ohne* Erlaubnis war die Umsatzsteuerklippe des Vorgängerkonzepts ein Artefakt eines 8-Termine-Szenarios, das ohne Jobaufgabe nicht existiert.
>
> ⚠️ Und er ist wackeliger, als er aussieht: Vorträge und Prävention sind **nicht** befreit — und Vorträge sind der einzige benannte Akquisekanal.

## 2. Höhere Betriebskosten *senken* die Abgaben — die Kurve ist flach

Die auffälligste Zeile: **3 Termine mit schlanken Kosten bringen netto nur ~600 € mehr als mit normalen Kosten** (4.005 € vs. 3.396 €), obwohl der Gewinn um 2.540 € höher liegt.

Grund: Der schlanke Fall überschreitet die Geringfügigkeitsgrenze von 7.236 € und löst damit **18,6 % Rentenversicherung** aus. Zusammen mit 40 % Steuer bleiben von jedem zusätzlichen Euro nur ~49 Cent.

> **Praktische Folge:** Im Bereich um 7.000–8.000 € Gewinn ist Sparen an Betriebskosten fast wertlos. Umgekehrt sind Fortbildung, Berufsverband und ein ordentlicher Raum dort **fast zur Hälfte fremdfinanziert**. Das spricht dafür, nicht am falschen Ende zu sparen.

## 3. Die Rentenversicherungspflicht verschwindet mit realistischen Kosten von selbst

Der Vorgänger rechnete bei 3 Terminen mit 1.488 € Rentenversicherung. **Mit aufgeschlüsselten Betriebskosten liegt der Gewinn bei 5.660 € — unter der Geringfügigkeitsgrenze, also 0 €.**

Das relativiert den in v1 des Qualifikationsdokuments gefeierten „Vorteil" der Erlaubnis noch weiter: Er beträgt im Zustand A **null**, weil die Pflicht dort ohnehin nicht greift. Erst ab ~5 Terminen wird er zu einer echten Größe (2.046 €/Jahr).

> ⛔ **Und ein Hebel, den man vermuten könnte, existiert nicht:** Die Existenzgründer-Befreiung nach **§ 6 Abs. 1a SGB VI** gilt ausschließlich für arbeitnehmerähnliche Selbständige nach § 2 Satz 1 Nr. 9 SGB VI — **nicht für selbständige Lehrende nach Nr. 1**. Für die Wissensvermittlerin ist dieser Weg zu. ([DRV](https://www.deutsche-rentenversicherung.de/DRV/DE/Experten/Arbeitgeber-und-Steuerberater/summa-summarum/Lexikon/B/befreiung_von_der_rentenversicherungspflicht_auf_antrag), [§ 6 SGB VI](https://dejure.org/gesetze/SGB_VI/6.html))

## 3b. ⛔ Rund die Hälfte des „Erlaubnis-Vorteils" ist gar kein Einkommen

**Der schwerwiegendste Befund des Reviews — und einer, den eine Nachrechnung nicht findet, weil jede Zahl stimmt.**

Der Mehrertrag der Erlaubnis bei 5 Terminen beträgt 8.400 − 5.372 = **3.028 €**. Davon entstehen **1.228 €** allein dadurch, dass Heilpraktiker nicht rentenversicherungspflichtig sind — die Wissensvermittlerin zahlt dort 2.046 € Beitrag, was sie nach Steuer 1.228 € Bargeld kostet.

> **Diese 1.228 € sind kein Ertrag, sondern eine nicht erworbene Rentenanwartschaft — plus der Wegfall des Erwerbsminderungsschutzes.**
>
> Das Vorgängerkonzept sagt das an der spiegelbildlichen Stelle selbst: *„Das ist kein reiner Verlust: Die Beiträge fließen in eigene Rentenanwartschaften und erhalten den Erwerbsminderungsschutz — bei zwei kleinen Kindern die wertvollste Absicherung überhaupt."* Dort stand es als Warnung, den Beitrag nicht als reine Kosten zu lesen. Hier wurde derselbe Betrag als **Ertrag** verbucht, ohne den Gegenwert zu nennen.

**Bereinigt** — wenn man die Rentenbeiträge zum vollen Nennwert als erhaltene Gegenleistung ansetzt:

| Auslastung | Mehrertrag laut Tabelle | davon nicht gezahlte RV | **bereinigt** |
|---|---|---|---|
| 3 Termine | +1.044 € | 0 € *(Gewinn unter der Grenze)* | **+1.044 €** |
| 5 Termine, nebenberuflich | +3.028 € | 1.228 € | **+1.800 €** |
| 6,5 Termine | +3.807 € | 1.646 € | **+2.161 €** |

*(Der Review setzte hier 68–72 % an, weil er den Bruttobeitrag ansetzte. Nach Steuer sind es ~40–43 % — die Richtung stimmt, die Höhe war überzeichnet.)*

## 4. Die Kasseneinstufung ist der teuerste einzelne Parameter

Sensitivität, gerechnet am Fall „mit Erlaubnis, 5 Termine" (netto 8.400 €):

| Veränderung | Wirkung aufs Jahresnetto |
|---|---|
| ⛔ **Ehemann wechselt in die PKV — *und* Einstufung hauptberuflich** | **−4.360 €** — siehe unten |
| Termine 3,5 statt 5 | −2.970 € |
| **Kasse stuft hauptberuflich ein** | **−2.500 €** *(nach Gegenrechnung des Job-Effekts)* |
| Preis 100 € statt 120 € | −2.100 € |
| Arbeitswochen 30 statt 35 | −1.800 € |
| Betriebskosten 5.500 € statt 7.000 € | +900 € |

> ⛔ **Die teuerste Zeile fehlte in der ersten Fassung vollständig — der Review hat sie gefunden.**
>
> Die gesamte Hauptberuflichkeits-Rechnung setzt stillschweigend voraus, dass der **Ehemann gesetzlich versichert bleibt**. Nach § 2 Abs. 4 der Beitragsverfahrensgrundsätze Selbstzahler wird bei freiwilligen Mitgliedern, deren Ehegatte **nicht** Mitglied einer Krankenkasse ist, dessen Einkommen **zur Hälfte, gedeckelt auf die halbe Beitragsbemessungsgrenze**, hinzugerechnet. Bei ~140 k liegt er über der Versicherungspflichtgrenze (2026: 77.400 €) und **kann jederzeit in die PKV wechseln**.
>
> Dann: (26.000 € eigene Einnahmen + 34.875 € halbes Ehegatteneinkommen) → 5.072,92 €/Monat × 20,85 % = **12.692 €/Jahr** statt 5.421 €. Nach Steuerwirkung **~4.360 € Mehrbelastung** — mehr als der gesamte Nettoertrag mancher Zelle.
>
> **Das Risiko greift nur in Regime H.** Solange sie nebenberuflich bleibt, ist sie über den Job pflichtversichert und der Status des Ehemanns irrelevant. Ein weiteres Argument, unter der Klippe zu bleiben.

> **Die schriftliche BKK-Anfrage ist damit rund 2.000 € im Jahr wert** — und sie kostet einen Brief. Sie gehört an den Anfang, nicht ans Ende.
>
> Was die Kasse prüft, steht im Vorgängerkonzept korrekt: **wirtschaftliche Bedeutung *und* zeitlicher Aufwand müssen die übrige Erwerbstätigkeit „deutlich" übersteigen** — maßgeblich ist der Gewinn nach § 15 SGB IV, nicht der Umsatz, und in die Zeit zählen Akquise und Buchhaltung mit. Bei 5 Terminen (14.000 € Gewinn gegen 12.000 € Gehalt, ~12,5 h gegen 10 h) ist **beides knapp über der Schwelle, aber nicht „deutlich"** — eine Gesamtschau, keine Formel.

## 5. Der aussagekräftigste Vergleich ist der Stundenlohn — nicht das Jahresnetto

> ⚠️ **Selbstprüfung, Fehler 2:** Die erste Fassung verglich den Verlagsjob **ohne** Pendelzeit mit der Selbständigkeit **inklusive** unbezahlter Vor- und Nachbereitung. Das ist kein fairer Maßstab: Wenn Buchhaltung und Akquise als Arbeitszeit zählen, zählen zwei Stunden Fahrt nach München auch. Beide Lesarten stehen jetzt nebeneinander.

| | Stunden/Jahr | netto | **€/h** |
|---|---|---|---|
| **Verlagsjob** — ohne Pendeln (10 h × 46 Wo.) | 460 h | 6.000 € | **13,0 €** |
| **Verlagsjob** — mit Pendeln (14 h × 46 Wo.) | 644 h | 6.000 € | **9,3 €** |
| Ohne Erlaubnis, 3 Termine | 263 h | 3.396 € | **12,9 €** |
| Ohne Erlaubnis, 5 Termine | 438 h | 5.372 € | **12,3 €** |
| **Mit Erlaubnis, 3 Termine à 120 €** | 263 h | 4.440 € | **16,9 €** |
| ⭐ **Mit Erlaubnis, 3 Termine à 150 €** | 263 h | **6.330 €** | **24,1 €** |
| Mit Erlaubnis, 5 Termine à 120 € | 438 h *(→ 538 h, s. u.)* | 5.897 – 8.400 € | **11,0 – 19,2 €** |
| Mit Erlaubnis, 6,5 Termine | 569 h | 8.414 € | **14,8 €** |

> ⚠️ **Review-Korrektur: Die Akquise skaliert mit den Kundinnen, nicht mit den Terminen.** P4 setzt 1 h unbezahlt je Termin an — bei 5 Terminen also 175 h für Vor-/Nachbereitung, Buchhaltung **und** Akquise. Die Vor-/Nachbereitung von 175 Sitzungen frisst davon 60–90 h, Verwaltung ~30 h. Für 29–58 Neukundinnen bleiben 55–85 h — das reicht für den unteren Rand, am oberen fehlen ~100 h. **Realistisch liegt die 5-Termine-Zeile bei ~538 statt 438 Stunden**, also bei 11,0–15,6 €/h statt 14,6–19,2. Die 3-Termine-Zeilen sind davon kaum betroffen, weil sie nur 18–35 Neukundinnen brauchen.

> **Das Kernergebnis, korrigiert:**
>
> Die Selbständigkeit hat **keine Pendelzeit** — die Praxis ist in Dachau. Das ist ein struktureller Vorteil, den die erste Fassung verschenkt hat. Gemessen an der Zeit, die tatsächlich aus dem Familienalltag herausgeht, liegt schon die Variante **ohne** Erlaubnis rund **40 % über dem Verlagsjob** (12,9 € gegen 9,3 €).
>
> ⚠️ *„Wirtschaftlich ein Nullsummenspiel" — so stand es in der ersten Fassung. Das war zu hart und ist zurückgenommen.* Richtig ist: Ohne Erlaubnis ist der Zugewinn **klein und ungesichert**, und er wird mit dem Verlust von Krankengeld, Kinderkrankengeld, Arbeitslosenanwartschaft und bezahltem Urlaub erkauft, **falls** der Job dafür weichen müsste. Solange der Job bleibt, ist es echter Zusatz — nur wenig davon.
>
> **Mit Erlaubnis liegt der Stundenlohn 30–100 % über dem Job**, je nach Kasseneinstufung und Pendel-Lesart. Der beste Punkt liegt bei **5 Terminen**.

---

# ↩️ Amortisiert sich die Ausbildung?

Kosten des Wegs zur Erlaubnis (aus dem Qualifikationsdokument v4, netto nach Steuerersparnis):

| | |
|---|---|
| HP-Ausbildung selbstbestimmt + Prüfungsgebühren + Material | 2.960 – 4.030 € |
| Fachausbildung Frauenheilkunde (nötig, um 120 € zu rechtfertigen) | 1.660 – 1.810 € |
| **= Netto-Investition** | **4.620 – 5.840 €** |

| Auslastung | Mehrertrag Cashflow | davon nicht gezahlte RV | **bereinigter Mehrertrag** | **Amortisation** |
|---|---|---|---|---|
| 3 Termine à 120 € | +1.044 € | 0 € | **+1.044 €** | **4,4 – 5,6 Jahre** |
| ⭐ **3 Termine à 150 €** | **+2.934 €** | 0 € | **+2.934 €** | **1,6 – 2,0 Jahre** |
| 5 Termine, nebenberuflich | +3.028 € | 1.228 € | **+1.800 €** | **2,6 – 3,2 Jahre** |
| 5 Termine, hauptberuflich | +525 € | 1.228 € | **−703 €** | **nie** |
| 6,5 Termine | +3.807 € | 1.646 € | **+2.161 €** | **2,1 – 2,7 Jahre** |

> ⚠️ **Zwei Korrekturen gegenüber der ersten Fassung.** Erstens ist die Spalte „Cashflow" nicht dasselbe wie Ertrag — bei 5 und 6,5 Terminen besteht ein erheblicher Teil aus nicht mehr erworbener Rentenanwartschaft (Befund 3b). Zweitens setzte die erste Fassung bei 5 Terminen nur den günstigen Fall an.
>
> **Das Ergebnis:** Bereinigt liegt die Amortisation bei **1,6 bis 3,2 Jahren** — mit einer klaren Rangfolge, und der Sieger ist **nicht** das Szenario mit den meisten Terminen.

> ⚠️ **Was in dieser Tabelle *nicht* steht — und der Review zu Recht anmahnt:**
> - **Die Lernzeit.** 700–1.400 Stunden aus demselben Vormittagsfenster, aus dem die Termine kommen sollen. Bewertet mit dem Stundensatz ohne Erlaubnis (12,9 €) sind das **9.000–18.000 € entgangener Ertrag** — ein Vielfaches der Barinvestition. Teilweise vermeidbar, wenn die Praxis während der Ausbildung schon läuft, aber nicht ganz.
> - **Das Liebhaberei-Risiko.** Der Qualifikationsweg nennt es, dieses Dokument hat es beim Import der Nettokosten verloren: Erkennt das Finanzamt die Gewinnerzielungsabsicht nicht an, liegt die Investition bei **7.965–9.265 € brutto** und die Amortisation ~60 % höher.
> - **Anlaufjahre.** Die Tabelle unterstellt Vollauslastung ab dem ersten Tag nach der Prüfung.

Dazu der Kalender aus dem Qualifikationsdokument: Schritt 0/1 (5 Monate) + Lernzeit (2,5–4 Jahre) + Fristenversatz (bis 9 Monate) + zweiter Anlauf (0,5 Jahre) = **Erlaubnis realistisch 2030–2032**, danach ein Praxisanlaufjahr.

> **Zusammengefasst:** Bei 3 Terminen amortisiert sich die Erlaubnis frühestens **Mitte der 2030er**. Bei 5 Terminen etwa **2032–2034**. Der Unterschied zwischen diesen beiden Zeilen ist **nicht** die Ausbildung, sondern die Zahl der Kundinnen.

---

# 🚧 Die Nachfrage — die Schwelle statt einer Zahl

| Auslastung | Sitzungen/Jahr | bei 3–6 Sitzungen je Kundin | **neue Kundinnen pro Jahr** |
|---|---|---|---|
| 3 Termine | 105 | | **18 – 35** |
| **5 Termine** | **175** | | **29 – 58** |
| 6,5 Termine | 228 | | **38 – 76** |

> ⚠️ **Review-Korrektur zur Kadenz.** Die erste Fassung rechnete „alle 6 bis 12 Tage eine neue Kundin" — das sind Kalendertage. Der Betrieb läuft aber 35 Wochen = **175 Arbeitstage**. Richtig: **alle 3 bis 6 Arbeitstage** bei 5 Terminen, **alle 5 bis 10** bei 3 Terminen. Doppelt so anspruchsvoll wie dargestellt.

## Was der Markt dazu hergibt — mit ausdrücklichem Vorbehalt

| Kennzahl | Wert |
|---|---|
| Heilpraktiker in Deutschland | ~47.000 |
| Branchenumsatz | ~1,0 – 1,2 Mrd €/Jahr |
| **→ Umsatz je Heilpraktiker** | **≈ 21.000 – 26.000 €/Jahr** |
| Einwohner Landkreis Dachau | **152.363** (2023), Kaufkraftindex **118** |
| → rechnerische Dichte (1 HP je ~1.780 Einwohner) | **~85 Heilpraktiker im Landkreis** — zu verifizieren |

> Quellen: [heilpraktiker-fakten.de](https://www.heilpraktiker-fakten.de/heilpraktikerfakten/heilpraktiker-in-deutschland/), [Statista — Umsatz Heilpraktikerpraxen](https://de.statista.com/prognosen/314278/prognose-zum-umsatz-der-branche-heilpraktikerpraxen-in-deutschland), [Landkreis Dachau — Strukturdaten](https://www.landratsamt-dachau.de/bauen-wohnen-gewerbe/wirtschaftsstandort/standort-dachau/strukturdaten/)

> ⚠️ **Zwei viel zitierte Branchenzahlen widersprechen einander um den Faktor 3–4.** Neben den obigen kursiert „46 Millionen Patientenkontakte pro Jahr" — das wären ~980 Kontakte je Heilpraktiker, was bei 21.000–26.000 € Umsatz einen Preis von ~25 € je Kontakt bedeuten würde. Das ist unmöglich. **Beide Zahlen stammen von interessierten Parteien.** Verwendbar ist hier nur die Umsatzgröße, und auch die nur als Größenordnung.

**Was sich daraus ableiten lässt:**

> ⚠️ **Review-Korrektur — die Grundgesamtheit ist falsch.** Die 47.000 sind **Erlaubnisinhaber**, nicht praktizierende Vollzeitpraxen; Erhebungen weisen rund **zwei Drittel als nebenberuflich oder in Teilzeit** aus. Der Quotient mischt Vollzeitpraxen mit Teilzeit- und Karteileichen-Erlaubnissen.
>
> Modellhaft: ein Drittel Vollzeit à ~40.000 € plus zwei Drittel Teilzeit à ~12.000 € ergibt genau die ausgewiesenen ~22.000 €. Daraus folgt:
>
> **21.000 € sind nicht „etwa der Bundesdurchschnitt einer Praxis", sondern das obere Viertel bis Fünftel der *nebenberuflichen* Praxen.** Der Median einer Teilzeitpraxis — und nichts anderes wäre ihre — liegt eher bei **~12.000 €**, also praktisch **beim 3-Termine-Szenario (12.600 €)**.
>
> Das stützt die Empfehlung, die sich aus der Hebeltabelle ohnehin ergibt: **3 Termine sind die realistische Planungsgröße, 5 Termine ein Top-Quartil-Ergebnis aus dem Stand.** Und der Weg zu mehr Ertrag führt über den Preis, nicht über die Menge.
>
> ⚠️ Die abgeleiteten „~85 Heilpraktiker im Landkreis" unterstellen eine Gleichverteilung über Deutschland; die Dichte ist stark stadt- und kaufkraftkorreliert. Die Zahl wird in keiner Schlussfolgerung verwendet und ist als Größenordnung zu lesen.

---

# ⚖️ Die Antwort auf „lohnt sich das?"

| Frage | Antwort |
|---|---|
| **Trägt sich die Tätigkeit selbst?** | Ja, sehr früh. Break-even bei **~26 Terminen/Jahr ≈ 0,7 pro Woche** *(Review-Korrektur: die erste Fassung nannte 1,4/Woche, weil sie einen dauerhaft angemieteten Raumtag gegen eine Ein-Termin-Woche rechnete. Bei so wenigen Terminen mietet man stundenweise — 48 × 1,5 h × 18 € = 1.296 € statt 2.340 €.)* |
| **Lohnt sie sich ohne Erlaubnis?** | **Knapp.** ~12,9 €/Stunde — gleichauf mit dem Verlagsjob ohne Pendelzeit, ~40 % darüber mit. **~3.400 €/Jahr** zusätzlich zum Gehalt. Echter Zusatz, aber wenig |
| **Lohnt sie sich mit Erlaubnis?** | **Ja — aber über den Preis, nicht über die Menge.** Bester Punkt: **3 Termine à 150 € → 6.330 €/Jahr, 24 €/Stunde**, Amortisation 1,6–2,0 Jahre, kein Beitragsrisiko, nur 18–35 Neukundinnen |
| **Lohnt sich der Ausbau auf mehr Termine?** | **Kaum.** Der Grenzertrag von 5 auf 6,5 Termine beträgt ~500 € für 131 Stunden = **3,8 €/Stunde** — ein Viertel des Verlagsjobs inklusive Pendeln |
| ⚠️ **Ist der Preis-Pfad beitragsrechtlich riskanter?** | **Nein — genau umgekehrt.** Das stand so im Vorgängerkonzept und wurde ungeprüft übernommen. Dort galt es bei 2.500 € Betriebskosten (3 × 150 € → 13.250 € Gewinn > 12.000 € Gehalt). Mit den hier aufgeschlüsselten 5.200 € sind es **10.550 € — unter dem Gehalt**, und der Zeitaufwand (7,5 h) bleibt unter den 10 h des Jobs. **Kein Kriterium der Hauptberuflichkeit ist berührt.** Bei 5 Terminen à 120 € sind beide berührt |
| **Sollte der Job gekündigt werden?** | **Nein.** Er hält die Krankenversicherung bei 0 €, sichert Krankengeld und Kinderkrankengeld, und sein Stundenlohn ist nur unwesentlich niedriger als der der Selbständigkeit ohne Erlaubnis |
| **Ist Elternzeit ein Hebel?** | **Nein — und noch klarer als bisher.** Sie schafft Kapazität, die nach dieser Rechnung ohnehin nicht der Engpass ist. Der Engpass sind Kundinnen |
| **Woran hängt alles?** | Am empfohlenen Punkt an **18–35 neuen Kundinnen im Jahr** — alle 5 bis 10 Arbeitstage eine. Dazu gibt es null Daten. **Und: ob 150 € durchsetzbar sind.** Der regionale Markt gibt es her (Folgebehandlung 90–130 €/60 Min), aber es ist ein Zielwert, kein Startwert |

## Die Hebel, nach Wirkung sortiert

*(Die erste Fassung hatte hier eine dritte, mit den anderen Tabellen unvereinbare Rechnung — Statuswechsel als „gleicher Status" etikettiert, Preishebel auf falscher Basis. Korrigiert, alles gegen dieselbe Basis: **3 Termine à 120 € mit Erlaubnis = 4.440 €**.)*

| Hebel | Wirkung aufs Jahresnetto | Preis in Zeit und Risiko |
|---|---|---|
| ⭐ **Preis 120 → 150 €** | **+1.890 €** | **keiner** — gleiche Stundenzahl, gleiche Kundinnenzahl, kein Beitragsrisiko |
| **Von 3 auf 5 Termine** (à 120 €, nebenberuflich) | +3.960 € | +175 h Arbeit, +11–23 Neukundinnen, **Beitragsklippe berührt** |
| **Die Erlaubnis** (bei 3 Terminen) | +1.044 € | 2,5–4 Jahre Ausbildung, ~5.000 € bar |
| ⛔ **Einstufung als hauptberuflich** | **−2.500 €** | — |
| ⛔ **Ehemann in die PKV, bei Regime H** | **−4.360 €** | — |

> ## Der eine Satz
>
> **Der günstigste Hebel ist der Preis — er kostet keine zusätzliche Stunde, keine zusätzliche Kundin und kein Beitragsrisiko.** Der ökonomisch beste erreichbare Zustand ist deshalb **nicht** „so viele Termine wie möglich", sondern **drei Termine pro Woche zu einem Heilpraktiker-Satz von ~150 €: rund 6.300 € im Jahr, 24 € pro Arbeitsstunde, 18–35 neue Kundinnen.**
>
> **Und genau diese 18–35 Kundinnen sind die einzige Größe im ganzen Dokument, zu der es keine Daten gibt.**

---

# 🎯 Was jetzt zu tun ist, nach Wert sortiert

| Priorität | Handlung | Wert |
|---|---|---|
| **1** | **Verlag anrufen:** Wie liegen die 10 Arbeitsstunden — zwei Fahrten oder vier? | Halbiert die Kapazitätsspanne, entscheidet über 3,5 vs. 6,5 Termine |
| **2** | **20 Gespräche führen** (unverändert aus v7), mit der Frage nach **tatsächlichen Gesundheitsausgaben der letzten 12 Monate** | Die einzige Größe, an der alles hängt |
| **3** | **Zwei Heilpraktikerinnen mit Frauenschwerpunkt anrufen:** Wie viele Behandlungen pro Woche, welcher Nettoertrag, wie viele Neukundinnen pro Monat, über welchen Kanal? | Ersetzt die Marktschätzung durch Beobachtung |
| **4** | **BKK schriftlich anfragen:** Ab welchem Gewinn **und Zeitaufwand** hauptberuflich? **Und: Was passiert mit meinem Beitrag, wenn mein Mann in die PKV wechselt?** | ~2.500 €/Jahr — im PKV-Fall **~4.400 €** |
| **5** | **Raum bei der Bekannten klären** — vormittags frei? Zu welchem Preis? Und: Ist stundenweise günstiger als ein fester Tag? | Bis ~1.100 €/Jahr; im Anlaufjahr entscheidet es über den Break-even |
| **6** | **DRV anfragen** *(nur relevant ohne Erlaubnis)*: Wird der Beitrag nach dem tatsächlichen Gewinn bemessen, oder gilt im Gründungsjahr mangels Steuerbescheid der Regelbeitrag? | Bis **~2.400 €/Jahr** in den Anlaufjahren |
| 7 | Steuerberater: Welcher Umsatzanteil ist nach § 4 Nr. 14 a UStG befreit? Kirchensteuerpflicht? | Ab ~6 Terminen à 120 € relevant · Kirchensteuer ~3 pp |

---

# ⚠️ Grenzen dieser Rechnung

- **Die Nachfrageseite ist weiterhin unbelegt.** Diese Version macht die Angebotsseite belastbar und legt die Schwelle offen — sie beweist nicht, dass die Schwelle erreichbar ist.
- **Der hauptberufliche Fall ist vereinfacht.** Wenn die Kasse umstuft, ändert sich auch die Beitragslage des Angestelltenverhältnisses; die +1.250 € Gegenrechnung ist eine Näherung. **Vor jeder Entscheidung darüber: BKK und Steuerberater.**
- **Der Grenzsteuersatz (40 %) ist abgeleitet, nicht berechnet.** Sensitivität am Fall „mit Erlaubnis, 5 Termine": bei 37 % netto 8.820 €, bei 40 % 8.400 €, bei 43 % (mit Kirchensteuer) 7.980 €. **Spannweite ±420 € — der unkritischste Parameter im ganzen Modell.** Die Kirchensteuerpflicht bleibt trotzdem zu klären.
- **Die Betriebskosten sind mit echten Marktpreisen gebaut, aber nicht mit echten Angeboten.** Die Raummiete stammt aus Münchner Anzeigen; in Dachau kann sie deutlich niedriger liegen — oder das Studio der Bekannten hat vormittags gar keine freie Kapazität.
- **Der Preis von 120 € ist ein Zielwert, kein Startwert.** Eine neue Praxis liegt anfangs darunter. In den ersten ein bis zwei Praxisjahren ist jede Zeile dieser Tabellen zu optimistisch.
- **Die Marktkennzahlen stammen aus Quellen, die sich gegenseitig widersprechen.** Nur die Umsatzgröße wird verwendet, und nur als Größenordnung.
- **Diese Version rechnet an mehreren Stellen ungünstiger als v7** (Betriebskosten, Steuersatz) und an mehreren günstiger (Kapazität, Preis, Umsatzsteuer, Rentenversicherung). Das ist kein Ausgleich, sondern Zufall — **jede Zeile ist einzeln nachzurechnen.**

---

# 🔬 Prüfprotokoll

## Runde 1 — Selbstprüfung (der Review war am Session-Limit gescheitert)

| # | Fehler | Wirkung |
|---|---|---|
| 1 | Job-KV-Effekt stand in Spalte 2, fehlte in Spalte 1 | Vorteil der Erlaubnis bei 6,5 Terminen zu hoch |
| 2 | Verlagsjob **ohne** Pendelzeit gegen Selbständigkeit **mit** unbezahlter Nebenzeit | „Nullsummenspiel" war zu hart, zurückgenommen |
| 3 | Bei 5 Terminen nur der günstige Fall als Ergebnis | Ergebnis ist eine Spanne |
| 4 | Amortisation gegen die unkorrigierte Zahl gerechnet | 1,2–1,5 statt 0,9–1,2 Jahre |

## Runde 2 — unabhängiger Review · `VERDICT: REVISE` · 14 Befunde

**Ergebnisverändernd, eingearbeitet:**

| Befund | Wirkung |
|---|---|
| **Rentenanwartschaft als Ertrag verbucht** | ~40 % des „Erlaubnis-Vorteils" bei 5+ Terminen ist kein Einkommen. Amortisation neu berechnet |
| **Job-KV-Effekt brutto statt netto** | +750 € statt +1.250 €; BKK-Anfrage wertvoller (~2.500 € statt ~2.000 €) |
| **Umsatzsteuer-Folgerung falsch** | Der Vorteil ist nicht „wirkungslos", sondern **tragend** in der besten Zelle. Schwelle liegt bei 5,95 Terminen, nicht 7,5 |
| ⭐ **Preis-Pfad ist der *sicherere*, nicht der riskantere** | Aus v7 ungeprüft übernommen; galt dort bei 2.500 € Betriebskosten. Mit 5.200 € kehrt sich die Aussage um — **das ändert die Empfehlung** |
| **Break-even mit 3-Termine-Fixkosten für eine 1-Termin-Woche** | 0,7 statt 1,4 Termine/Woche |
| **Ehemann könnte in die PKV wechseln** | Fehlte vollständig; in Regime H **~4.360 €/Jahr** — die teuerste Zeile des Modells |
| **Rentenversicherung: Regelbeitrag vs. einkommensgerechter Beitrag** | Im Gründungsjahr fehlt der Steuerbescheid; bis ~2.400 €/Jahr Unterschied. Als DRV-Frage aufgenommen |
| **Marktableitung mischt Vollzeit- und Teilzeitpraxen** | 21.000 € sind nicht der Durchschnitt, sondern das obere Viertel der Teilzeitpraxen |
| **Akquise skaliert mit Kundinnen, nicht mit Terminen** | Stundenlohn bei 5 Terminen überschätzt |
| **Neukundinnen-Kadenz in Kalender- statt Arbeitstagen** | Doppelt so anspruchsvoll wie dargestellt |
| **„Die drei Hebel" auf inkonsistenter Basis** | Neu gerechnet, Rangfolge kippt zugunsten des Preises |
| **„Ausbau lohnt nicht" widersprach der eigenen Tabelle** | Ersetzt durch den Grenzertrag: 3,8 €/Stunde |
| **Zusatzbeitrag 2,9 % ist der Durchschnitt** | Der BMW-BKK-Wert ist eine Ein-Minuten-Recherche; ±375 €/Jahr. Weiterhin offen |
| **Liebhaberei-Vorbehalt beim Import verloren** | Wieder aufgenommen |

**Vom Review geprüft und bestätigt:** alle Betriebskostenspalten · die Kapazitätsrechnung · alle Ergebnisspalten beider Hauptrechnungen · sämtliche Krankenversicherungsberechnungen · die Stundenlohntabelle · § 226 SGB V · § 5 Abs. 5 SGB V · § 6 Abs. 1a SGB VI (Existenzgründerbefreiung nur für Nr. 9, nicht für Lehrende) · § 18 EStG · § 19 UStG n. F. · **die Pflegeversicherungs-Korrektur auf 3,35 % bei zwei Kindern** · der Grenzsteuersatz von 40 % inklusive fehlendem Solidaritätszuschlag · und dass der Pendel-Fix keinen neuen Fehler eingeführt hat.

---

## ⛔ Und jetzt: nicht weiterrechnen

Der Review schließt mit einem Einwand gegen sich selbst, und er hat recht damit:

> *„Der Erwartungswert der vier Telefonate ist um ein Vielfaches höher als der jeder weiteren Rechenrunde. Ein Review, der eine fünfte Überarbeitung auslöst, arbeitet gegen genau die Erkenntnis, die er bestätigt."*

Die tragende Aussage hat inzwischen zwei unabhängige Prüfungen überstanden und ist durch mehrere Korrekturen eher **stärker** geworden: **Der Engpass sind Kundinnen — nicht Kapazität, nicht Steuerrecht, nicht Beitragsrecht.** Alles Weitere ist Optimierung an einem Modell, dessen einzige unbekannte Größe außerhalb des Modells liegt.

**Nächster Schritt sind die Telefonate, nicht die nächste Version.**
