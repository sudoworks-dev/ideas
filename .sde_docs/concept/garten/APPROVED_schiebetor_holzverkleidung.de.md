# Konstruktionskonzept: Fichte-Verkleidung auf freitragendem Stahl-Schiebetor (6,0 × 1,90 m)

📌 **Status:** APPROVED — **Version 3** (Final-Prüfung vor Bestellung; freigegeben durch Nutzer 2026-09-23, Einkauf Alu/Nietmuttern/Schrauben freigegeben)
📅 **Erstellt:** 2026-09-09
🎯 **Ziel:** Opferschicht-Prinzip — Holz ist Verschleißteil, die Alu-Ebene bleibt dauerhaft

> **Version 3 — Final-Prüfung vor der Bestellung von Alu, Nietmuttern und Schrauben.**
> Vier Befunde ändern die Bestellung. Alle nachrechenbar, keiner ist Geschmackssache:
>
> | v2 | Warum falsch | v3 |
> |---|---|---|
> | **Flachprofil 40 × 6**, 4 Löcher je 2-m-Segment | Nie nachgewiesen: Bei Windsog (Wind von der Hausseite) zieht das Holz die Leiste **vom Stahl weg** — sie spannt dann in ihrer schwachen Achse (W = 240 mm³) von Loch zu Loch. Mittlere Linie trägt als Mittelauflager eines Zweifeldträgers 1,25 × 0,95 = 1,19 m Einzugshöhe. Ergebnis: σ_d = **165 N/mm²** (Zone B) bzw. **271 N/mm²** (Zone A) gegen f_o/γ_M1 = 150/1,1 = **136 N/mm²**; Durchbiegung charakteristisch **8–13 mm** | **Flachprofil 40 × 8**, **5 Löcher je Segment** (Raster 450 mm): σ_d = 79 (B) / 130 (A) N/mm², w_k = 2–3 mm |
> | Senkkopf M6 an den **Gleitpunkten**, mit Feder-/Planscheibe darunter | Ein Senkkopf **zentriert sich im Kegel** — er kann im überweiten Loch nicht gleiten, egal wie weit das Loch ist. Eine Scheibe unter einem bündigen Senkkopf ist geometrisch unmöglich | Gleitpunkte: **Flachkopf ISO 7380 in Flachsenkung Ø 11**, Festpunkt: Senkkopf |
> | Festpunkt „mittig", Raster 200/750/1250/1800 | Das Raster hat **kein Loch in der Mitte** — der mittige Festpunkt war nicht setzbar | Raster **100/550/1000/1450/1900**, Festpunkt = Loch bei 1000 |
> | 3 × 2,00 m + 2 × 10 mm Fuge je Linie | = **6,02 m** auf einem 6,00-m-Rahmen | Segmentlänge **nach Aufmaß kürzen**, s. Bauteil A |
>
> Dazu: **M5 statt M6** (kleinere Bohrung im Stahl, A4-M5 von Hand sicher setzbar — A4-M6 schafft selbst
> das Gesipa FireFox 1F nicht), **geschlossene** Nietmutter (kein Wasserweg ins Rohr), Holzschrauben-Höhe
> so gelegt, dass sie die Metallschraubenköpfe nicht treffen kann. Die Einkaufsliste steht jetzt
> bestellfertig unter „📦 Einkaufsliste".
>
> **4 mm Dicke?** Nein — dreifach ausgeschlossen: W = 107 mm³ (Spannung 2,25× höher als bei 6 mm, das
> schon versagt), kein Platz für eine Senkung, und die Holzschraube braucht 4–5 mm Sackloch **ohne**
> den Stahl zu erreichen.

---

> **Version 2 (Stand 2026-09-09) — Historie:**

> **Version 2 ist eine Verkleinerung und eine Korrektur, keine Erweiterung.**
> Eine unabhängige Prüfung hat Version 1 mit `BLOCK` bewertet. Drei Kernentscheidungen waren falsch,
> zwei davon geometrisch — mit dem Zollstock nachprüfbar, nicht Auslegungssache:
>
> | v1 | Warum falsch | v2 |
> |---|---|---|
> | Alu-**Rechteckrohr 40 × 20 × 2** | Geschlossenes Rohr = 20,8 mm bis zum Holz. Die Schraube 4,5 × 16 endet **4,8 mm vor dem Brett**. Die M6 hätte × 30 sein müssen und stünde 6 mm in die Auflagefläche | Alu-**Flachprofil 40 × 6** |
> | **Rückseitenverschraubung** | Traglinien liegen auf den Stahlriegeln — **dahinter ist Stahl, es gibt keine Rückseite**. Nicht bei der Montage, nicht beim Brettwechsel | **Verdeckte Schrägverschraubung durch die Feder** |
> | **4 Traglinien** | Die Zusatzlinie war der einzige frei spannende Bauteil und fiel im Durchbiegungsnachweis durch (9,3 mm gegen 6,0 mm zulässig). Sie löste ein Problem, das rechnerisch nicht existiert: das Brett hat bei 950 mm **Faktor 10 Reserve** | **3 Traglinien** auf den vorhandenen Riegeln |
>
> Weitere korrigierte Rechenfehler aus v1: Lochspiel Ø 8 um M6 (v2-Stand; v3: M5) ist **1,00 mm**, nicht 1,25 mm ·
> Windlast-Interpolation ergibt **10,7 kN**, nicht die als Alternative genannten 13,0 kN ·
> Schraubennachweis war über die Windzonen gemittelt (Faktor 10 behauptet, real **2,3**) ·
> die 20-mm-Hinterlüftung nach DIN 18516-1 war auf einen Fall zitiert, für den die Norm nicht gilt.
>
> **Sprache:** Deutsch, abweichend von der SDE-Kernregel „Artefakte in Englisch" — Konvention des
> Ordners `concept/garten/`, Ausführung durch den Nutzer selbst. Bewusste, sichtbare Abweichung.

---

## 🎯 Problem Statement

Ein 6,0 m breites, 1,90 m hohes freitragendes Schiebetor aus pulverbeschichtetem Stahl-Vierkantrohr
**40 × 40 mm** soll außen mit vorhandenen Nut-Feder-Fichtenbrettern (**21 mm**, Deckbreiten gemischt
**ca. 100–150 mm**) auf **2,00 m** Höhe verplankt werden — 100 mm über Rahmenoberkante.

Die eigentliche Anforderung ist eine **Lebensdauer-Trennung**: Fichte ist Dauerhaftigkeitsklasse 4
nach DIN EN 350 („wenig dauerhaft") und hat keinen abgesetzten Kern, der Splintanteil (DK 5) ist hoch.
Das Holz **wird** getauscht werden müssen. Beim Tausch darf der Stahlrahmen nie wieder angebohrt werden
— jede neue Bohrung im Stahl ist eine neue Roststelle. Deshalb die Alu-Zwischenebene: **sie nimmt die
Löcher, nicht der Stahl.**

### Akzeptanzkriterien — mit ehrlichem Erfüllungsgrad

| # | Kriterium | v3 |
|---|---|---|
| A1 | Verbindung Alu ↔ Stahl übersteht Jahrzehnte ohne Kontaktkorrosion | ⚠️ **eingeschränkt** — siehe Bauteil B, die Bohrung im Stahl bleibt der Schwachpunkt |
| A2 | Holz kann quellen/schwinden ohne Zwang | ⚠️ **abhängig von der ungemessenen Holzfeuchte** — siehe O1 |
| A3 | Einzelne Bretter tauschbar, ohne die Alu-Ebene zu demontieren | ⚠️ **neu gefasst** — siehe unten |
| A4 | Von außen keine sichtbaren Befestigungsmittel | ✅ im Neuzustand; beim Ersatz eines Brettes in Feldmitte nicht mehr |
| A5 | Von einem versierten Heimwerker allein ausführbar | ✅ (in v1 nicht — dort war „von innen anzeichnen" hinter Stahl vorgesehen) |
| A6 | Innenansicht aufgeräumt | ✅ — 3 Alu-Profile deckungsgleich auf 3 Stahlriegeln, sonst nichts Neues |

#### A3 muss ehrlich neu gefasst werden

Version 1 versprach: *„jedes Einzelbrett von innen in fünf Minuten getauscht."* **Das ist falsch, und
zwar unabhängig von der Befestigungsart.** Ein senkrechtes Nut-Feder-Brett steckt beidseitig
formschlüssig. Um es zu befreien, bräuchte es eine seitliche Verschiebung über die **volle Federlänge
(7–9 mm)**. Vorhanden sind 2 mm Fugenluft.

**Was tatsächlich geht:**

| Fall | Aufwand |
|---|---|
| Bretter **vom Rand her** abbauen | Schrauben lösen, Brett für Brett seitlich ausfädeln — sauber, wiederverwendbar |
| **Einzelbrett in Feldmitte** | Brett längs aufsägen und in Stücken entfernen. Ersatzbrett an der Nutrückwange abtrennen, von vorn einlegen — dieses eine Brett muss dann **sichtbar** verschraubt oder verklebt werden |
| **Komplette Neuverkleidung** | Der Regelfall nach ~15–25 Jahren. Alles ab, alles neu — **die Alu-Ebene und der Stahl bleiben unberührt.** Das ist der eigentliche Zweck der Konstruktion |

Die Alu-Ebene erfüllt ihren Zweck also beim **Generationswechsel der Verkleidung**, nicht beim
Einzelbrett-Tausch. Das ist immer noch der Hauptnutzen — aber es ist ein anderer Anspruch.

### Randbedingungen

| Punkt | Status |
|---|---|
| Rahmenrohr 40 × 40 mm | **bestätigt** (Nutzer) |
| Innenseite bleibt unverkleidet, dauerhaft zugänglich | **bestätigt** (Nutzer) |
| Innenansicht soll aufgeräumt wirken (Hausseite) | **bestätigt** (Nutzer) |
| Flügelgewicht / Antrieb / Fahrbreite | **vom Nutzer vorab geprüft** |
| Bretter 21 mm N+F, 100–150 mm gemischt, bereits gekauft | **bestätigt** (Nutzer) — Holzartwechsel ist keine Option |
| 3 waagerechte Rahmenebenen, senkrechte Stäbe ~1,2 m | ⚠️ **Annahme aus Fotos — messen** |
| Rahmen eben (alle Stahl-Vorderflächen bündig) | ⚠️ **Annahme — messen** |
| Wandstärke Rahmenrohr ≥ 2 mm | ⚠️ **Annahme — messen** |

---

## ⚠️ Windlast — was dieses Konzept nicht bemisst

| | offener Rahmen (Ist) | vollflächig beplankt |
|---|---|---|
| Völligkeitsgrad φ | ~0,10 | 1,00 |
| Angeströmte Fläche | 1,2 m² | 11,4 m² |
| **Resultierende Windkraft** | **0,9 kN** | **10,7 kN** (≈ 1,09 t) |

q_p = 0,65 kN/m² (DIN EN 1991-1-4/NA Tab. NA.B.3, Windzone 2 Binnenland, h ≤ 10 m).
c_p,net nach Tab. 7.9, **korrekt interpoliert** für l/h = 3,16 (Anteil 0,079 zwischen den Zeilen
l/h ≤ 3 und l/h = 5): c_A = 2,35 · c_B = 1,43 · c_C = 1,22.
Zonen bei h = 1,90 m: A = 0–0,57 m · B = 0,57–3,80 m · C = 3,80–6,00 m.

**Faktor 12 gegenüber dem offenen Rahmen.** Die Last geht über Pfosten, Fundament, Laufwagen und
Endanschlag ab — Bauteile, die dieses Konzept **nicht** bemisst (offener Punkt O2).

**Korrektur zu v1:** Dort stand, die Last gehe „nicht in die Verkleidung". Das war falsch herum.
Die Last **entsteht an der Verkleidung** und läuft durch jede Holzschraube, jedes Alu-Profil und
jede Blindnietmutter, bevor sie den Pfosten erreicht. Die Verkleidungsbefestigung ist das **erste**
Glied im Lastpfad — sie wird deshalb in Bauteil C nachgewiesen, und zwar mit dem Randzonenwert,
nicht mit einem Mittelwert.

Zusätzlich: Vier gleichlautende Montageanleitungen für freitragende Schiebetor-Bausätze
(Bauer Systemtechnik) nennen **„Belag max. 10 kg/m²"** und **„mind. 40 % winddurchlässig"**.
Dieses Vorhaben liegt bei ~10,5 kg/m² und 0 %.

---

## 💡 Vorgeschlagene Lösung

### Leitidee

**Drei Alu-Flachprofile 40 × 8 mm, deckungsgleich auf die drei vorhandenen Stahlriegel geschraubt.
Die Bretter werden verdeckt schräg durch die Feder in das Alu geschraubt — der belegte Regelfall der
Nut-Feder-Fassadenmontage.**

### Querschnitt — Klarstellung Alu-Lage

**Das Alu-Profil sitzt bündig direkt auf der Stahlriegel-Vorderfläche, nicht davorstehend mit
Abstand.** Kein Luftspalt zwischen Stahl und Alu — die einzige Trennung ist die 0,8 mm dünne
EPDM-Lage aus Bauteil D. Gilt für alle drei Ebenen gleich (oben, Mitte, unten), jeweils auf dem
zugehörigen horizontalen Stahlriegel:

```
        Stahlrohr           Alu-Flach   EPDM    Holz 21 mm
     ┌──────────────┐      ┌────────┐ ┌────┐ ┌──────────┐
     │              │      │ 8 mm   │ │0,8 │ │          │
     │  40 × 40 mm  │──────│ direkt │─│ mm │─│  Fichte  │
     │   Stahlriegel│ bündig│aufge-  │ │    │ │  sichtbar│
     │              │ auf-  │schraubt│ │    │ │          │
     └──────────────┘ liegend└────────┘ └────┘ └──────────┘
        (Innenseite)                              (Außenseite)
     ◄── Rahmentiefe ──►◄─ 8 ─►◄0,8►◄──── 21 ────►
```

Gesamtaufbau in der Tiefe: Stahl-Vorderfläche → Alu 8 mm (flächig aufliegend, verschraubt) →
EPDM 0,8 mm → Holz 21 mm (sichtbare Außenfläche). Das Alu ist damit selbst Teil der Rahmenebene,
kein vorgesetztes, freistehendes Element — das war auch der Grund, ein Flachprofil statt eines
Rechteckrohrs zu wählen (s. u.).

Kein Bauteil spannt frei. Die Alu-Profile liegen über ihre gesamte Länge flächig auf Stahl auf und
tragen nichts ab — sie sind reine Anschraubebene und werden nur auf Windsog beansprucht.

### Warum drei Traglinien genügen — der Nachweis, der in v1 fehlte

Version 1 begründete die vierte Linie mit Auflagerabständen aus Fassaden-Montageanleitungen
(Fachregel 01: 40 × d = 840 mm; Krages/Osmo: 500–700 mm). **Das sind Verarbeitungs- und
Optikkriterien gegen Schüsseln und Welligkeit bei frontverschraubten Einzelbrettern an einer
Gebäudewand — keine Tragkriterien.** Der tragende Nachweis wurde nie geführt. Hier ist er:

Ungünstigstes Brett 150 × 21 mm, Feld 950 mm, Zone A (w = 0,65 × 2,35 = 1,53 kN/m²):

```
q = 1,495 × 0,150                       = 0,224 N/mm
W = 150 × 21²/6                         = 11 025 mm³
M = qL²/8 = 0,224 × 950²/8              = 25 306 Nmm      (Einfeldträger, konservativ)
σ = 25 306 / 11 025                     = 2,29 N/mm²   gegen f_m,k = 24 N/mm² (C24)
                                        → Faktor 10,5
I = 150 × 21³/12                        = 115 762 mm⁴
f = 5qL⁴/(384·E·I), E = 11 000 N/mm²    = 1,87 mm  =  L/509
```

Als Durchlaufträger über drei Riegel und mit gegenseitiger Stützung über die Feder ist es noch
günstiger. **950 mm sind unkritisch.** Die vierte Linie entfällt — und mit ihr das einzige Bauteil,
das einen eigenen Tragnachweis gebraucht hätte.

```
 2000 ┬────────────────────────────  Brettoberkante (+100 über Rahmen), Alu-Abdeckung
      │        Kragarm ~110
 1890 ┼════ Traglinie 3 ═══════════  auf oberem Stahlriegel
      │        ~950
  940 ┼════ Traglinie 2 ═══════════  auf mittlerem Stahlriegel
      │        ~950
    0 ┼════ Traglinie 1 ═══════════  auf unterem Stahlriegel
      └────────────────────────────  Brettunterkante, 15° Tropfkante
```
*(Maße nach Aufmaß anpassen — die Riegellagen sind Annahme aus den Fotos.)*

---

### Bauteil A — Alu-Traglinien

| Parameter | Festlegung | Begründung |
|---|---|---|
| Profil | **Flachstange 40 × 8 mm, EN AW-6060 T66** (AlMgSi0,5 F22), blank | 0,864 kg/m → 18 m = **15,6 kg** (v2: 11,7 kg). Handelsübliche Metallbau-Qualität, Rp0,2 ≥ 150 N/mm² ([Dold](https://www.dold-mechatronik.de/Flachstange-40x8mm-Aluminium-EN-AW-6060-T66-(AlMgSi0,5)-0,91kg-m,-Zuschnitt-20-6000mm), [IBL](https://shop.ibl-raimund.de/Alu/Flachstangen/Metallbau-AlMgSi0-5-6060-T66/Flachstange-AlMgSi0-5-6060-F22-BreitexStaerke-40x8-mm.html)) |
| Oberfläche | **blank genügt** (EN AW-6060 bildet selbst eine Oxidschutzschicht) | Vom Stahlriegel weitgehend verdeckt. Beschichtung auf der Anode bringt laut MB 829 nichts und schadet bei Beschädigung. Blanke Kanten von innen ggf. mit Ausbesserungslack übermalen |
| **Warum flach, nicht Rohr** | massiv | Die Schraube muss durch das Alu ins Holz bzw. in die Nietmutter — ein geschlossenes Rohr legt 20 mm Hohlraum dazwischen. **Das war der tödliche Fehler in v1** |
| **Warum 8 mm, nicht 6 — und schon gar nicht 4** | Windsog-Nachweis, s. u. | 40 × 6 ist mit dem v2-Raster überlastet (σ_d 165–271 N/mm² gegen 136) und bräuchte ~7 Löcher je Segment = **63 Bohrungen im Stahl** statt 45. Jede Stahlbohrung ist der erklärte Schwachpunkt (A1) — dickeres Alu ist die billigere Reserve als mehr Löcher. 8 mm gibt außerdem ≥ 4,5 mm Sicherheitsabstand zwischen Holzschraubenspitze und Stahl (Bauteil C) und Platz für eine Flachsenkung mit 5 mm Restwand |
| **Warum flach, nicht Winkel** | — | Ein Winkel hätte einen nach oben offenen Schenkel = 6 m Wasserbrett. Ein Flachprofil hat gar keinen Schenkel. **Antwort auf „Winkel oder Profile?": Flachprofil, weder noch** |
| Segmentierung | **3 Segmente je Linie, 9 gesamt.** Länge L_seg = (Rahmenbreite − 2 × 5 mm Randrücksprung − 2 × 10 mm Stoßfuge) / 3. **Bei 6000 mm Rahmen: 1990 mm** | 2,0-m-Stangen passen — sie werden um ~10 mm gekürzt, nicht verlängert. **Rahmenbreite vor der Bestellung messen** und entweder 9 × 2000 mm kaufen und selbst kürzen oder direkt 9 × L_seg zuschneiden lassen |

#### Windsog-Nachweis der Leiste — fehlte in v2

Wind von der Hausseite drückt die Verkleidung nach außen. Die Holzschrauben ziehen die Leiste dann
**vom Stahl weg**, gehalten nur an den Nietmuttern. Zwischen zwei Löchern spannt das Flachprofil in
seiner **schwachen Achse** (40 breit, t hoch). Die Aussage aus v2 „die Profile tragen nichts ab" gilt
nur für Winddruck von außen.

```
Mittlere Linie = Mittelauflager des Brettes (Zweifeldträger): Einzug 1,25 × 0,95 m = 1,19 m
q_d Zone A = 0,65 × 2,35 × 1,19 × 1,5 = 2,73 N/mm     Zone B: 0,65 × 1,43 × 1,19 × 1,5 = 1,66 N/mm
Widerstand EN AW-6060 T66: f_o / γ_M1 = 150 / 1,1 = 136 N/mm²
```
Stabwerksrechnung je Segment (Löcher als gelenkige Auflager, Segmente an den Stoßfugen getrennt):

| Variante | σ_d Zone A | σ_d Zone B | w_k Zone B | Nietmutter-Last R_d |
|---|---|---|---|---|
| 40 × 6, 4 Löcher 200/750/1250/1800 (v2) | **271** ❌ | **165** ❌ | 8,0 mm | 0,9–1,5 kN |
| 40 × 6, 5 Löcher, 450er Raster | **231** ❌ | 140 ❌ | 4,8 mm | 0,8–1,4 kN |
| 40 × 8, 4 Löcher (v2-Raster) | **152** ❌ | 93 ✅ | 3,4 mm | 0,9–1,5 kN |
| **40 × 8, 5 Löcher, 450er Raster (v3)** | **130** ✅ | **79** ✅ | **2,0 mm** | **0,8–1,4 kN** |

Zone A (Windrandzone, ≤ 0,57 m ab Torende) ist hier konservativ auf ein ganzes Segment angesetzt.
Obere und untere Linie tragen nur ~0,4–0,5 m Einzugshöhe und sind mit demselben Raster unkritisch —
gleiches Raster überall, damit es nur ein Bohrbild gibt. *(Rechnung: `scratchpad/beam.py`,
Balken-FE je Segment; Werte gerundet.)*

#### Bohrbild je Segment

| | Festlegung |
|---|---|
| **Lage längs** | **Festpunkt in der Segmentmitte**, je 2 Gleitpunkte links/rechts im Abstand **450 mm**; äußere Löcher ~95–100 mm vom Segmentende. Bei L_seg = 1990: **95 / 545 / 995 / 1445 / 1895 mm** |
| **Lage in der Höhe** | Nietmutter-Reihe **14 mm über der Unterkante** der Leiste. Die Holzschrauben sitzen **8 mm unter der Oberkante** (Bauteil C) → mind. 7 mm Abstand zwischen Holzschraube und Metallschraubenkopf/Senkung. *(v2 hatte beide auf Mitte — bei ~48 Federn auf 45 Köpfen wären rechnerisch 5–7 Holzschrauben auf einen M-Kopf getroffen)* |
| **Festpunkt (1 je Segment)** | Ø **5,5 mm** + Kegelsenkung 90° für Senkkopf M5 (Kopf Ø 10, Tiefe ~2,8 mm, bündig) |
| **Gleitpunkte (4 je Segment)** | Ø **6,6 mm** + **Flachsenkung Ø 11 × 3,0 mm** (Zapfensenker DIN 373 „M6 mittel", Führungszapfen 6,6) für Flachrundkopf ISO 7380 M5 (Kopf Ø 9,5 × 2,75) |
| Summe | 9 Segmente × 5 = **45 Nietmuttern** (9 Fest-, 36 Gleitpunkte) |

**Wärmedehnung:**
```
ΔL_Alu   = 6000 × 23,1·10⁻⁶ × 100 K = 13,86 mm
ΔL_Stahl = 6000 × 12,0·10⁻⁶ × 100 K =  7,20 mm
Differenz über 6,0 m                =  6,66 mm
```

Starr gefesselt würde die Differenz eine Zwangskraft von σ = E·Δα·ΔT ≈ 35 N/mm² (±45 K) × 320 mm²
≈ **11 kN je Segment** erzeugen — unabhängig von der Segmentlänge, und sie ginge als Querkraft in die
äußeren Nietmuttern einer 2-mm-Rohrwand. Ausknicken kann die Leiste dagegen nicht: sie liegt zwischen
Stahl und verschraubtem Holz. *(Das v2-Argument „beult bei 6 N/mm² aus" übersah diese Sandwich-Lage;
die Schlussfolgerung — Gleitpunkte nötig — bleibt richtig, nur aus dem anderen Grund.)*

**Gleiten muss tatsächlich möglich sein — und ein Senkkopf kann das nicht.** Der Kegel zentriert
die Schraube in der Senkung; das überweite Loch darunter ist wirkungslos. Deshalb:

- **Festpunkt:** Senkkopf M5 in engem Loch Ø 5,5 — hält das Segment in Position.
- **Gleitpunkte:** Flachrundkopf M5 auf **ebenem** Grund einer Flachsenkung Ø 11. Radiales Spiel:
  Schaft 5 in Ø 6,6 = **±0,8 mm**, Kopf 9,5 in Ø 11 = **±0,75 mm**.
- **Bedarf** am äußersten Gleitpunkt (900 mm vom Festpunkt), Einbau ~15 °C, Bereich −20…+80 °C:
  `900 × 11,1·10⁻⁶ × 65 K = +0,65 mm` / `× 35 K = −0,35 mm` → **gedeckt**.
- **Kein Langloch, keine Federscheibe, keine Planscheibe.** Gleitpunkte **handfest + ~¼ Umdrehung**
  (≈ 2–3 Nm), Gewinde mit **mittelfester Schraubensicherung** (z. B. Loctite 243) — hält das moderate
  Anzugsmoment über die Temperaturzyklen und verhindert zugleich Fressen A4 in A4.

**Beim Anzeichnen vor Ort:**
- **Senkrechte Stäbe meiden.** Wo ein senkrechter Rahmenstab den Riegel kreuzt (~alle 1,2 m,
  geschweißt), darf kein Loch sitzen. Gleitpunkt dann um bis zu ±50 mm verschieben (Nachweis hält
  bis ~500 mm Lochabstand). **Der Festpunkt bleibt in der Mitte**; liegt dort ein Stab, das
  ganze Bohrbild um ≤ 50 mm verschieben.
- **Schweißnähte / Überstände** an den Kreuzungen prüfen (O7) — die Leiste muss plan aufliegen.
- Stoßfugen über einem senkrechten Stahlstab sind ein Komfortmerkmal, kein Muss.

---

### Bauteil B — Verbindung Alu ↔ Stahl

**Die Korrosionsfrage hat zwei Stellen, und v1 hat die falsche analysiert.**

**Stelle 1 — Alu gegen A4-Schraube: unkritisch, belegt.** Merkblatt 829 der Informationsstelle
Edelstahl Rostfrei (Autoren u. a. BAM), Abschn. 3.4:

> *„Typische Praxisbeispiele sind hier Befestigungselemente aus rostfreiem Stahl für Aluminiumbauteile
> […] Auch unter korrosiven Umgebungsbedingungen tritt bei diesen Anordnungen praktisch keine
> Bimetallkorrosion auf."*

Große Alu-Anode, kleine Edelstahl-Kathode — Tab. 7 bewertet das mit „+". Hier ist nichts zu tun.

**Stelle 2 — die tatsächlich kritische, in v1 übersehen: die Bohrung im Stahlrohr.** Dort sitzt die
A4-Blindnietmutter formschlüssig gegen die **blanke, frisch gebohrte Wandung des Baustahlrohrs**,
im Hohlraum eines geschlossenen Profils, in dem Kondensat steht und schlecht abtrocknet.
Flächenverhältnis: ~44 mm² blanker Stahl (Bohrung Ø 7 × 2 mm Wand; bei M6/Ø 9 wären es ~57 mm²) als Anode gegen die deutlich größere A4-Fläche (Kathode) —
**kleine Anode an großer Kathode, das ungünstige Verhältnis.** Genau der Mechanismus, den MB 829 §6
beschreibt:

> *„Die Beschädigungen in der Beschichtung führen zu kleinflächigen Anoden, die dann mit hoher
> Abtragungsrate korrodieren können."*

v1 sah als Abhilfe eine EPDM-Dichtscheibe unter dem Schraubenkopf vor. **Die sitzt auf der
Alu-Vorderseite und deckt am Stahl nichts ab** — sie war wirkungslos.

| Parameter | Festlegung | Begründung |
|---|---|---|
| Nietmutter | **Blindnietmutter M5, A4, kleiner Senkkopf (reduzierter Flachkopf), geschlossen, Rundschaft — gerändelt, wo lieferbar. Klemmbereich muss die gemessene Wandstärke enthalten (typ. 0,3–3,5 oder 0,5–3,0 mm). Bohrloch Ø 7,0** | Details und Begründung M5/geschlossen/Kopf s. unten |
| Schraube Festpunkt | **Senkschraube ISO 10642 M5 × 16, A4-70**, Innensechskant | 8 mm Alu + ~0,5 mm Nietmutterkopf + ~7 mm Gewinde |
| Schraube Gleitpunkte | **Flachkopfschraube ISO 7380-1 M5 × 12, A4-70**, Innensechskant | 5 mm Restwand unter der Flachsenkung + 0,5 + ~6,5 mm Gewinde |
| **A4 statt A2** | 1.4401/1.4571 statt 1.4301 | Zufahrt = Streusalz. abZ Z-30.3-6: A2 = KWK II „ohne nennenswerte Chloridbelastung", A4 = KWK III „bei Tausalz" |
| **Abdichtung am Stahl** | **Nietmutter-Kopf beim Setzen in MS-Polymer einbetten, Überstand abwischen, ≥ 24 h aushärten lassen, dann erst Alu montieren** | Verschließt den Wassereintritt **dort, wo er entsteht**. Aushärten *vor* der Alu-Montage ist Pflicht: MS-Polymer ist ein Kleber — nass unter der Leiste würde es die Gleitpunkte festkleben |
| Unter dem Schraubenkopf | **nichts** | Senkkopf: bündig im Kegel. Flachkopf: direkt auf dem ebenen Senkungsgrund |
| Raster | s. Bauteil A — 5 je Segment, **45 gesamt** | Bemessung R_d = 0,8–1,4 kN je Nietmutter (v2 schätzte ~300 N/720 N — ohne Zweifeldträger-Faktor) |

#### Warum genau diese Nietmutter

| Merkmal | Wahl | Warum |
|---|---|---|
| **Größe M5 statt M6** | M5 | (1) **Bohrung im Stahl Ø 7 statt Ø 9** — 22 % weniger blanke Bohrungswand, d. h. weniger Anodenfläche am erklärten Schwachpunkt. (2) **A4 in M6 ist von Hand kaum setzbar**: selbst das druckluft-hydraulische Gesipa FireFox 1F nennt „M3–M6 alle Werkstoffe **außer M6 Edelstahl**" ([profishop](https://www.profishop.de/p/gesipa-blindnietmuttern-setzgeraet-firefox-1f-m-6-1458198)); Handzangen gehen bei Stahl/Edelstahl oft nur bis M5, für A4-M6 braucht es eine Zweihandzange ([Übersicht](https://www.vergleich.org/nietmutternzange/)). (3) Last 1,4 kN liegt weit unter der Tragfähigkeit einer M5-A4-Verbindung (Zugfestigkeit einer A4-70 M5 ≈ 10 kN) |
| **geschlossen** | geschlossenes Ende | Eine offene Nietmutter ist ein **Wasserweg** vom Schraubengewinde direkt ins Rohrinnere — genau dorthin, wo Kondensat die Bohrungswand angreift. Geschlossen hält Wasser draußen ([Gesipa: „verhindert das Eindringen von Schmutz und Flüssigkeiten“](https://www.schraubenhimmel.de/nieten/blindnietmuttern/kleiner-senkkopf/72342/gesipa-blindnietmuttern-edelstahl-a4-kleiner-senkkopf-m-5x7x12-5-klemmbereich-0-3-3-5-mm)) |
| **kleiner Senkkopf** | reduzierter Kopf ~0,5 mm | Liegt ohne Senkung im Stahl auf (keine zusätzliche Stahl-Bearbeitung) und hebt die Leiste nur ~0,5 mm an — der Spalt ist mit dem ausgehärteten MS-Polymer gefüllt. Der „Senkkopf 90°“ bräuchte eine Kegelsenkung **im Stahl** = mehr verletzte Beschichtung; der normale Flachkopf (~1,0–1,5 mm) hebt die Leiste zu weit an |
| **gerändelt** (wenn lieferbar) | Rändelschaft | Verdrehsicherung beim Anziehen im runden Loch. Nicht lieferbar in A4-geschlossen-M5? Dann Rundschaft — das MS-Polymer im Loch sichert zusätzlich |

**Pflicht-Probe vor der Montage** (mit einer Nietmutter aus der Packung, an einem Stahlrohr-Rest oder
einer unauffälligen Stelle): setzen, Schraube eindrehen — die M5 × 16 bzw. × 12 darf **nicht am
geschlossenen Boden aufstehen** (Schraube dreht fest, bevor der Kopf anliegt). Tut sie das: 2 mm
kürzere Schrauben (× 14 / × 10) nachkaufen. Die Gewindetiefe der geschlossenen Ausführung steht nicht
auf jedem Datenblatt.

**Ehrliche Bewertung von A1:** Die Bohrung im Stahl ist der Schwachpunkt der ganzen Konstruktion und
lässt sich **nicht vollständig schützen** — Bohrungswandung und Innenrand im Hohlraum sind nicht
erreichbar. Die Maßnahmen reduzieren das Risiko, sie beseitigen es nicht. Prüfen, ob der Rahmen
unten Entwässerungsöffnungen hat; falls nicht, welche setzen.

**Zwei Ausführungsregeln:**

1. **Bohrspäne sofort und vollständig entfernen.** Stahlspäne, die nass auf dem Alu liegen bleiben,
   erzeugen Flugrost direkt auf der Beschichtung.
2. **Kein Zinkspray ins Bohrloch.** Der intuitive Griff ist hier **falsch**: Zink ist unedler als
   Aluminium und macht die Bohrstelle zur Anode gegenüber der großen Alu-Fläche (MB 829 Tab. 7: „o",
   unsicher). Stattdessen deckender Lack in RAL des Rahmens auf den erreichbaren Rand.

**Verworfen: Bimetall-Bohrschrauben.** Die gehärtete Kohlenstoffstahl-Bohrspitze verbleibt im
Hohlraum und rostet.

#### Verworfen: Direktverschraubung (gewindefurchend) statt Blindnietmutter

Bis v2 als Alternative bei Wandstärke ≥ 2,5 mm geführt (DIN 7500 Form M, A4). Mit O6 zugunsten der
Nietmutter entschieden: Die Direktschraube hängt an einer ungemessenen Wandstärke, formt ihr Gewinde
in 2–3 mm Baustahl, der danach blank im Hohlraum liegt, und ist nicht nachbesserbar. Außerdem wäre
sie offen zum Rohrinneren. [Kopfmaße DIN 7500](https://www.schrauben-lexikon.de/download/t_7500mtx-a2.pdf)

---

### Bauteil C — Verbindung Holz ↔ Alu

**Antwort auf „unsichtbar, oder von hinten durchs Alu?": verdeckt von vorn — schräg durch die Feder.
Von hinten geht nicht.**

Der Grund ist Geometrie, nicht Vorliebe: Die Traglinien liegen deckungsgleich auf den Stahlriegeln.
**Dahinter ist über die volle Länge 40 × 40-Stahlrohr.** Es gibt keine Rückseite, in die man schrauben
könnte — weder bei der Montage noch je wieder. Version 1 hatte das übersehen; es war der Fehler, der
das ganze Konzept trug.

Die verdeckte Schrägverschraubung ist zugleich der **belegte Regelfall** der N+F-Fassadenmontage —
im Unterschied zur Rückseitenverschraubung, die in keinem Regelwerk vorkommt.

| Parameter | Festlegung | Begründung |
|---|---|---|
| Schraube | **A4 Senkkopf, Vollgewinde — Länge nach Messung, s. u.** | schräg ~45° durch den Federgrund |
| **Typ/Produktname** | **"Fassadenschraube A4" / "Universalschraube A4"**, ~3,5–4,0 mm, TX-Antrieb, **scharfe Spitze — ausdrücklich OHNE „Bohrspitze"/„für Alu-Unterkonstruktion"-Zusatz** | s. Korrekturbox unten |
| Vorbohren Holz | Ø 3,0 mm | Fichte spaltet an der Feder sonst |
| Vorbohren Alu | Ø 3,2 mm | gewindefurchender Sitz im Aluminium |
| Anzahl | **1 Schraube je Brett und Traglinie** = 3 pro Brett | s. u. |
| Abstand zum Brettende | ≥ 30 mm | Krages / Osmo |

**Korrektur zur Spitze — Bohrspitze ist hier falsch:** Eine "Bohrspitze" (Terrassenschraube
für Alu-Unterkonstruktion) hat einen eigenen, ungewindeten Bohrabschnitt vorn — gedacht, um sich
durch eine dünne Alu-Wand (typ. 2–3 mm) komplett durchzubohren, bevor das Gewinde greift. Bei uns
ist das Loch aber ein **Sackloch mit nur 3–4 mm nutzbarer Tiefe** (absichtlich nicht durchbohrt,
sonst zu nah am Stahl). Ist die Bohrspitze länger als dieses Sackloch — durchaus üblich, da sie
fürs Durchbohren dimensioniert ist — sitzt am Ende genau der ungewindete Teil: **kein Halt**, und
weiter eindrehen heißt entweder Steckenbleiben/Abreißen oder zu nah an den Stahl.

**Da beide Löcher ohnehin vorgebohrt werden (Holz Ø 3,0, Alu Ø 3,2), wird keine Bohrfähigkeit
gebraucht.** Gesucht ist eine Schraube mit **scharfer, ungebohrter Spitze** — Gewinde läuft fast
bis zur Spitze durch, kein separater toter Bohrabschnitt. Formt im vorgebohrten Alu-Loch über die
volle nutzbare Tiefe Gewinde. Produktkategorie: gewöhnliche A4-Fassaden-/Universalschraube, **ohne**
"Bohrspitze"/"für Alu-UK"-Kennzeichnung.

#### Konkretes Bezugsprodukt — geprüft

**"Spanplattenschraube A4, Vollgewinde, Senkkopf, TX20, Ø 4 mm"** — Standard-Handelsware, kein
Spezialprodukt. Zwei verifizierte Quellen mit passenden Eckdaten:

| Quelle | Bestätigt | Längen im Programm |
|---|---|---|
| [schraubenhandel24.de — Spanplattenschrauben A4 Vollgewinde TX](https://www.schraubenhandel24.de/schrauben/spanplattenschrauben/art-9047/art-9047-spanplattenschrauben-tx-edelstahl-a4-vollgewinde-4/) | A4, Senkkopf 90°, TX20, Vollgewinde, durchgehendes Holzgewinde (kein Bohrabschnitt), ETA 11/0283 | 10–80 mm in 5-mm-Schritten, u. a. **16 / 20 / 25 mm** |
| [schraubenhimmel.de — Spanplattenschrauben A4 TX20 Vollgewinde](https://www.schraubenhimmel.de/schrauben/senkkopf/spanplattenschrauben-tx/) | gleiches Programm, bestätigt zusätzlich: A4 ist weicher als verzinkter Stahl → Vorbohren nötig (deckt sich mit Ø 3,0/Ø 3,2 hier) | u. a. **16 mm**, 25 mm, 45 mm+ |

**Wichtig — bei diesem Produkt bewusst in Kauf genommen:** Das Gewinde ist fürs Holzfaser-Fassen
optimiert, nicht als eigens fürs Metall-Gewindeformen ausgelegtes Profil. Bei der hier anfallenden
Last (224 N Bemessungswert je Schraube, s. u.) reicht das im vorgebohrten Ø-3,2-Loch aus — Standard-
praxis bei so geringer Last, nicht das theoretische Optimum fürs Alu.

**Vor der Bestellung der vollen Charge (~150 Stk.):**
1. Spitze am Produktfoto/an der Verpackung ansehen — durchgehend gewindet, **kein** glatter
   Abschnitt vorn. Sonst gilt die Korrektur oben (Bohrspitze) und das Produkt ist ungeeignet.
2. Bei der konkret gewählten Länge (16/20/25 mm) die Angaben Material/Kopf/Antrieb auf der
   jeweiligen Produktseite gegenprüfen — bei sehr kurzen Varianten weichen manche Hersteller in
   Kleinigkeiten ab.
3. Erst eine kleine Menge/Packung zum Probebohren (s. u.), dann erst die volle Charge.

#### Schraubenlänge — Formel statt fixer Zahl, weil sie von der Federlage abhängt

**Korrektur:** Eine frühere Fassung nannte hier pauschal 40 mm. Das ist zu lang und stößt bei einem
45°-Winkel mit hoher Wahrscheinlichkeit **durch das 6-mm-Alu hindurch in den Stahl** — genau die
Bohrung im Stahl, die diese Konstruktion für immer vermeiden soll.

Aufbau in der Tiefe, ab der sichtbaren Holzfläche:
```
0 ── 21,0 mm  Holz
21,0 ── 21,8 mm  EPDM
21,8 ── 29,8 mm  Alu (8 mm)
29,8 mm  ──────  Stahl — darf nicht erreicht werden
```
Bei 45° legt die Schraube pro 1 mm Länge nur `sin 45° ≈ 0,71 mm` Tiefe zurück. Die richtige Länge
hängt davon ab, **wo die Feder im 21-mm-Querschnitt tatsächlich sitzt** — das variiert je nach
Profil und ist ohne Messung nicht seriös anzugeben:

```
L = (Zieltiefe im Alu − Tiefe des Ansatzpunkts an der Feder) / sin(45°)
```

Zieltiefe = 21,8 mm (Alu-Anfang) + 4–5 mm Einbindung = **25,8–26,8 mm** — bleibt ≥ 3 mm vor dem Stahl (29,8 mm).

| Federlage (Ansatzpunkt a) | rechnerisch | **Kauflänge (5-mm-Raster)** | Spitze liegt bei | Einbindung Alu / Rest bis Stahl |
|---|---|---|---|---|
| eher vorn (~7 mm) | 27,3 mm | **25 mm** | 24,7 mm | 2,9 mm / 5,1 mm |
| mittig (~10,5 mm) — typisch | 22,3 mm | **20 mm** | 24,6 mm | 2,8 mm / 5,2 mm |
| eher hinten (~14 mm) | 17,4 mm | **16 mm** | 25,3 mm | 3,5 mm / 4,5 mm |

Mit 8 mm Alu ist in jeder Federlage **≥ 4,5 mm Abstand zum Stahl** — die Stufe darüber (30/25/20 mm)
käme auf 1,6 mm heran und ist deshalb **nicht** zu wählen.

**Höhenlage:** Holzschraube **8 mm unter der Oberkante der Leiste** ansetzen (Bohrer waagerecht
seitlich gekippt, s. Montage). Die Metallschrauben sitzen 14 mm über der Unterkante (Bauteil A) —
die Holzschraube kann keinen Kopf und keine Senkung treffen.

**Vorgehen:** Federlage an einem Reststück mit dem Messschieber messen (O5, 1 Minute) → Zeile der
Tabelle wählen → **200 Stück dieser Länge bestellen**. Ist die Messung vor der Bestellung nicht
möglich: je 100 Stück 20 und 25 mm (Mehrkosten ~10 €). Vor dem Verlegen einmal an einem Brettrest
auf einem Leistenrest probeschrauben: Ø 3,2 mit Tiefenanschlag, Schraube muss fest ziehen, Leiste
rückseitig unverletzt.

**Nachweis mit dem Randzonenwert — nicht mit einem Mittelwert:**

```
Ungünstigstes Brett: 150 mm × 2,0 m, Zone A, 3 Befestigungspunkte
Einzugsfläche je Schraube = 0,150 × 2,0 / 3   = 0,100 m²
F_k = 1,495 kN/m² × 0,100 m²                  =  150 N
F_d = 1,5 × 150                               =  224 N
Mittlere Linie (Zweifeldträger-Faktor 1,25):
F_d = 0,150 × 1,19 × 1,495 × 1,5              ≈  400 N
```
Ausziehwiderstand einer Ø-4-Schraube mit ~3 mm geformtem Gewinde in EN AW-6060 T66 grob
π · 3,4 · 2,8 · 0,6 · 0,6 · 215 ≈ 2 kN → Faktor ~5. *(Abschätzung, kein Herstellerwert — die Probe
oben ist der eigentliche Nachweis.)*
Das liegt im normalen Bereich einer Fassaden-Federverschraubung. *(v1 rechnete mit 55 N je Schraube,
weil es über alle Windzonen gemittelt hatte, und behauptete „Reserve > Faktor 10". Beides war falsch.)*

#### Zur 2-Befestiger-Regel: sie ist hier nicht erfüllbar — bewusst

Fachregel 01 verlangt ab 80 mm Brettbreite (N+F-Montageanleitungen: ab 120 mm) **zwei** Befestiger je
Auflager, gegen Verdrehen und Schüsseln. **Eine verdeckte Federverschraubung kann konstruktiv nur
einen liefern** — das gilt für jede N+F-Fassade weltweit, nicht nur hier.

Kompensation: Das Brett ist über die Feder **beidseitig formschlüssig** in seinen Nachbarn gefasst.
Das ist die Schüsselsicherung. Version 1 wollte das mit einer zweiten Schraube in einem Langloch
lösen — der Aufwand entfällt ersatzlos.

> **Deine ursprüngliche Überlegung — „eine Schraube in horizontaler Richtung, drei übereinander" —
> ist damit genau die umgesetzte Lösung.** Nur sitzt die Schraube jetzt in der Feder statt hinten,
> und es sind drei statt vier.

#### Fugenluft — der Wert, der noch fehlt

Bewegung **je Fuge** (= volles Δb eines Brettes, weil jedes Brett um seinen eigenen Fixpunkt arbeitet):

| Brett | Einbau 16 % → 22 % | Einbau **10 %** → 22 % |
|---|---|---|
| 100 mm | 1,5 – 2,3 mm | 3,0 – 4,7 mm |
| 150 mm | 2,3 – 3,5 mm | **4,5 – 7,0 mm** |

*(Spanne = Praxis-Rechenwert 0,25 %/% bis tangential 0,39 %/% nach LWF Bayern.)*

**Der maßgebende Anschlag ist nicht der Nutgrund, sondern die sichtbare Fuge zwischen den
Brettkanten.** Die schließt bei 2 mm Bewegung — lange bevor die Feder den Nutgrund erreicht.
Danach steht Holz gegen Holz und das Brett weicht aus der Ebene aus. *(v1 hatte sich auf „3,5 mm
Luft im Nutgrund" berufen; das ist der falsche Freiheitsgrad.)*

**Deshalb ist O1 der wichtigste offene Punkt:** Die Beschreibung „Nut-Feder-Fichte, 21 mm, gemischte
Breiten 100–150 mm" passt auf **Profilholz nach DIN 68122/68126 — Innenausbau-Ware, typisch als
Restposten**. Innenprofilholz wird mit **8–12 %** Holzfeuchte geliefert, nicht mit den 14–18 % von
Fassadenprofilen. Bei 10 % Einbaufeuchte bräuchten die 150er bis zu **7 mm Fuge** — mit N+F nicht
darstellbar.

**Wenn die Messung < 13 % ergibt:** Bretter vor der Montage im Freien akklimatisieren — gestapelt
mit Stapelleisten, überdacht, allseitig belüftet, mehrere Wochen, bis sie 14–16 % erreichen. Das ist
kein optionaler Komfortschritt, davon hängt die Fugenbemessung ab.

**Festlegung nach Messung:** Fugenluft = errechnete Quellbewegung des breitesten Brettes, mindestens
2 mm. Mit Distanzplättchen gleichmäßig einhalten.

---

### Bauteil D — Trennlage

**Eine Lage, nicht zwei.** Version 1 sah EPDM sowohl zwischen Alu und Stahl als auch zwischen Alu und
Holz vor. Die Lage zwischen Alu und Stahl ist gestrichen: MB 829 Tab. 7 bewertet die Paarung als
unkritisch, und die Abdichtung des Bohrlochs erfolgt jetzt wirksamer am Stahl selbst (Bauteil B).

**EPDM zwischen Alu und Holz: bleibt.** Zwei Mechanismen:
- **Kapillarwasser** im Kontaktspalt zwischen Brettrückseite und Metall — 40 mm breit, dreimal pro Brett
- **Materialpaarung**: Fichte hat pH 4,0–5,3, 11,2 % Abietinsäure und kondensierte Gerbstoffe
  (Fraunhofer WKI, Tab. 4.2). Deutlich harmloser als Eiche (pH 3,9) oder Douglasie, aber nicht
  neutral — und Aluminium ist amphoter

> **Korrektur zu v1:** Dort war die Begründung „Alu strahlt nachts gegen den Himmel ab und wird
> kälter als die Luft". Das gilt für **waagerechte** Flächen. Ein senkrechtes Profil hinter einer
> Holzschale hat einen Himmelssichtfaktor nahe null. Die Kondensat-Begründung war falsch; die
> Kapillar- und Materialbegründung trägt.

- **EPDM-Fassadenband 0,8 mm, Breite 50 mm** (Profilbreite 40 + 5 mm Überstand je Seite)
- selbstklebend, über die volle Segmentlänge, Stöße ≥ 100 mm überlappen

---

### Bauteil E — Ränder und Abschlüsse

**Oben** — der 100-mm-Überstand stellt Hirnholz in den Regen:
- Abgekantetes **Alu-Abdeckprofil 2 mm**, RAL des Rahmens
- **3° Gefälle nach außen**, **5 mm Überstand mit Tropfkante**, **hinten offen** (kein geschlossenes
  U-Profil, das Wasser einsperrt)
- Hirnholz zusätzlich versiegeln, auch unter der Abdeckung
- ⚠️ liegt in der Höhe der Führungsrollen — siehe O3

**Unten** — Fachregel 01 und DIN 68800-2 fordern ≥ 300 mm Bodenabstand. Auf einem Schiebetor
unerfüllbar. **Bewusste, dokumentierte Abweichung:**
- Bodenabstand maximieren, was die Tormechanik hergibt
- **15° Hinterschneidung als Tropfkante** an jedem Brettende (Krages Abb. 4/5)
- **Hirnholzversiegelung** an jedem unteren Brettende, vor Montage
- Akzeptiert: die unteren ~200 mm sind die Verschleißzone, und ein Einzelbrett-Tausch dort ist ein
  Sägejob, kein Schraubjob (A3)

**Seitlich** — Randbretter symmetrisch aufteilen (von der Mitte nach außen einteilen); ≥ 10 mm Fuge
zu anschließenden Bauteilen; Rücksprung an der Schließkante nach Aufmaß Endanschlag / Fangkopf.

**Verlegerichtung senkrecht:** Bretter sind 2 m lang und passen in einem Stück — waagerecht bräuchte
es ~40 Stöße als Wassereintritte über 6 m. Wasser läuft längs zur Faser ab, und es passt zur
senkrechten Fassade des Hauses. Gegenargument aus dem Regelwerk (senkrechte Profile faulen von unten
und der Sockel ist nicht als Verschleißreihe tauschbar) ist bekannt und wird in Kauf genommen.

---

## 📦 Einkaufsliste (bestellfertig, Stand v3)

### Vor dem Klick auf „Bestellen" — drei Messungen, zusammen ~10 Minuten

| # | Messen | Wofür | Womit |
|---|---|---|---|
| M1 | **Rahmenbreite** an allen drei Riegeln | Segmentlänge L_seg = (Breite − 30 mm) / 3 → bei 6000 mm: **1990 mm** | Maßband |
| M2 | **Wandstärke Rahmenrohr** — an einem offenen Rohrende, einer Bohrung oder der Endkappe | muss im Klemmbereich der Nietmutter liegen (typ. 0,3–3,5 mm). Bei 40 × 40 sind 2–3 mm üblich; liegt sie > 3,5 mm, andere Klemmbereich-Variante wählen | Messschieber |
| M3 | **Federlage** im 21-mm-Querschnitt (Abstand Brettvorderseite → Federmitte) | Holzschraubenlänge, Tabelle Bauteil C | Messschieber an einem Brettende |

### A — Jetzt bestellen: Metallbau

| Pos | Artikel — so in den Shop eingeben | Menge | Bemerkung |
|---|---|---|---|
| 1 | **Aluminium Flachstange 40 × 8 mm, EN AW-6060 T66 (AlMgSi0,5), blank** | **9 Stück à L_seg** (bei 6000 mm Rahmen: 9 × 1990 mm) — oder 9 × 2000 mm und selbst kürzen | ~15,6 kg. Zuschnitt auf Maß z. B. bei [Dold Mechatronik](https://www.dold-mechatronik.de/Flachstange-40x8mm-Aluminium-EN-AW-6060-T66-(AlMgSi0,5)-0,91kg-m,-Zuschnitt-20-6000mm) / [aluprofile-express](https://www.aluprofile-express.de/Flachstange-40x8mm-Aluminium-EN-AW-6060-T66-AlMgSi05-091kg-m-Zuschnitt-20-6000mm), [Metallstore](https://www.metallstore.de/aluminium/stange-flach/almgsi0-5-aw-6060/40x8-mm-aluminium-flach-almgsi0-5). **Nicht 40 × 6, nicht 40 × 4** (Bauteil A) |
| 2 | **Blindnietmutter M5, Edelstahl A4, kleiner Senkkopf, geschlossen**, gerändelt wenn lieferbar, sonst Rundschaft; Klemmbereich enthält M2; Bohrloch Ø 7,0 | **45 + Reserve/Probe → 1 Packung ≥ 60** (Packungen meist 50/100/250) | z. B. [Seimatec 154-1022-519 „M5 × 19, kleiner Senkkopf, A4, Rundschaft geschl."](https://www.schrauben-seimatec.de/blindnietmutter-kleiner-senkkopf-edelstahl-a4-rundschaft-geschl.) oder [kauf-schrauben „kleiner Senkkopf geschlossen gerändelt A4"](https://www.kauf-schrauben.de/blindnietmuttern-kleiner-senkkopf-geschlossen-geraendelt-edelstahl-a4/). **Im Datenblatt prüfen:** A4 (nicht A2/V2A), *geschlossen*, Klemmbereich, Bohrloch |
| 3 | **Senkschraube ISO 10642 M5 × 16, A4-70, Innensechskant** | 9 + Reserve → **15–20** | Festpunkte |
| 4 | **Linsen-/Flachkopfschraube ISO 7380-1 M5 × 12, A4-70, Innensechskant** | 36 + Reserve → **50** | Gleitpunkte. Nicht ISO 7380-**2** (mit Bund — Kopf Ø 10,5 passt nicht in die Ø-11-Senkung mit Spiel) |
| 5 | **Spanplattenschraube 4,0 × L, Edelstahl A4, Senkkopf, TX20, Vollgewinde, ohne Bohrspitze** | **200** der Länge aus M3 (16 / 20 / 25 mm) — ohne M3: je 100 × 20 und × 25 | [schraubenhandel24 Art. 9047](https://www.schraubenhandel24.de/schrauben/spanplattenschrauben/art-9047/art-9047-spanplattenschrauben-tx-edelstahl-a4-vollgewinde-4/). ~48 Bretter × 3 = ~145 + Probe/Verlust |

### B — Jetzt bestellen: Werkzeug und Hilfsstoffe

| Pos | Artikel | Menge | Bemerkung |
|---|---|---|---|
| 6 | **Blindnietmuttern-Zange, Zweihand-Hebel**, Herstellerangabe **„Edelstahl bis M5" oder besser „bis M6"**, mit M5-Dorn | 1 | Einhandzangen schaffen A4 oft nur bis M4/M5 knapp. Das ersetzt die v2-Position „Setzgerät ~50 €" |
| 7 | **Zapfensenker DIN 373 „M6 mittel" — Ø 11 mm, Führungszapfen Ø 6,6** (HSS) | 1 | Flachsenkung der 36 Gleitpunkte. Tiefenanschlag / Bohrständer, Tiefe 3,0 mm |
| 8 | **Kegelsenker 90°, HSS, Ø ≥ 12** | 1 | Senkung der 9 Festpunkte, Tiefe bis Kopf bündig |
| 9 | **HSS-Bohrer Ø 5,5 / 6,6** (Alu) · **HSS-Co Ø 7,0** + Ø 4 zum Vorbohren (Stahl) · **Ø 3,0 lang** (Holz) · **Ø 3,2** (Alu, Sackloch) · **Bohrer-Tiefenstopp** für Ø 3,2 | je 1–2 | Ø 3,2 bricht bei 150 Löchern — 2–3 Stück |
| 10 | **Schraubensicherung mittelfest** (z. B. Loctite 243) | 1 kleine Flasche | nur Gleitpunkte |
| 11 | **MS-Polymer**, überstreichbar | 1 Kartusche | Nietmutter-Köpfe; ≥ 24 h aushärten vor Alu-Montage |
| 12 | **EPDM-Fassadenband 0,8 × 50 mm, selbstklebend** | 20 m | Stöße ≥ 100 mm überlappen |
| 13 | Ausbesserungslack RAL Rahmen | 1 Stift | Bohrlochränder am Stahl. **Kein Zinkspray** |

### C — Später, nicht Teil dieser Bestellung

| Pos | Artikel | Wann |
|---|---|---|
| 14 | Alu-Abdeckprofil 2 mm, abgekantet, RAL Rahmen, 6,1 m | nach Klärung O3 (Führungsrollen) |
| 15 | Hirnholzversiegelung, Grund-/Zwischen-/Endanstrich (kupferfrei, O9) | nach Holzfeuchtemessung O1 |
| 16 | Holzfeuchte-Messgerät (~20 €) | **sofort sinnvoll** — O1 entscheidet die Fugenluft |

**Zuwachs Flügelmasse:** ~127 kg Holz + 15,6 kg Alu + ~4 kg Abdeckung/Befestiger ≈ **147 kg**
(v2: ~143 kg).

---

## 🔧 Montagereihenfolge

1. **Holzfeuchte messen** (O1). Alles Weitere hängt davon ab. Bei < 13 % zuerst akklimatisieren.
2. **Aufmaß** — alle ⚠️-Annahmen prüfen: Riegellagen, Lage der senkrechten Stäbe, Rahmenebenheit mit
   Richtlatte, Schweißnaht-Überstände, Federlänge und Nuttiefe an einem Brettpaar.
3. **Probe Nietmutter** (Bauteil B): eine M5 setzen, beide Schraubenlängen eindrehen — kein Aufstehen
   am geschlossenen Boden.
4. **Alu-Segmente vorbereiten, liegend auf der Werkbank:** auf L_seg kürzen, Bohrbild nach Bauteil A
   anreißen (Reihe 14 mm über Unterkante; 95 / 545 / 995 / 1445 / 1895 mm, Stäbe vorher auf dem Rahmen
   geprüft). Mitte: Ø 5,5 + Kegelsenkung. Übrige: Ø 6,6 + Flachsenkung Ø 11 × 3,0. Entgraten.
   **Unten/oben markieren** — das Bohrbild ist nicht symmetrisch.
5. **Segment am Riegel anlegen, fixieren (Zwingen), durch die Alu-Löcher ankörnen**, Segment abnehmen.
6. **Stahl bohren** Ø 4 vor, Ø 7,0 fertig. Späne sofort entfernen. Erreichbaren Bohrlochrand lackieren.
7. **Blindnietmuttern setzen**, Kopf vorher in MS-Polymer. Überstand abwischen. **≥ 24 h aushärten.**
8. **EPDM-Band auf die Alu-Vorderflächen** kleben (Löcher mit Cutter freischneiden).
9. **Alu-Segmente montieren**, Festpunkt (Senkkopf) zuerst — voll angezogen. Gleitpunkte (Flachkopf,
   Loctite 243): **handfest + ~¼ Umdrehung**. Probe: Segment längs mit leichtem Schlag (Gummihammer)
   bewegbar, ohne dass die Schraube lose ist. 10 mm Stoßfugen einhalten.
   Fluchtung prüfen (Toleranz ± 5 mm auf 2 m, Fachregel 01).
10. **Bretter vorbereiten:** Grund- und Zwischenanstrich **allseitig vor Montage**. Untere Stirnenden
    15° anschrägen, Hirnholz versiegeln. Kanten ≥ 2 mm runden.
11. **Von einer Seite her verlegen** — Feder voraus. Je Brett: einlegen, Fugenluft mit Distanzplättchen
    einstellen, ausrichten, an jeder der 3 Traglinien **8 mm unter der Leisten-Oberkante** Ø 3,0 durch
    den Federgrund vorbohren, Ø 3,2 ins Alu mit Tiefenstopp nachbohren, 4,0 × L (Tabelle Bauteil C)
    schräg eindrehen. Nächstes Brett deckt die Schraube ab.
    **Von vorn, im Stehen, von einer Person machbar.**

   > **Praxis-Tipp Zielgenauigkeit:** Die drei Alu-Profile sind nur ~40 mm hoch, der Rest der
   > 2 m Bretthöhe ist dahinter leer — die Präzision entscheidet sich beim **Anreißen, nicht
   > beim Bohren**. Vor der Montage die drei Riegelhöhen auf jedes Brett (Federkante) übertragen,
   > z. B. mit einer Schablone oder durch Anhalten am Rahmen. Der 45°-Winkel selbst läuft **in der
   > Waagerechten** — Bohrer seitlich kippen (Feder-Außenkante → Tiefe), **nicht nach oben/unten**.
   > So bleibt die einmal angerissene Höhe über den ganzen Bohrvorgang exakt erhalten.
12. **Randbretter** symmetrisch auftrennen; letztes Brett muss von vorn befestigt werden — dort einen
    unauffälligen Punkt wählen (Nutgrund des Nachbarn oder oberste/unterste Zone).
13. **Abdeckprofil oben** montieren, Gefälle prüfen.
14. **Endanstrich** vorderseitig.
15. **Funktionsprobe:** Tor mehrfach komplett verfahren, Führungsrollen und Endanschlag beobachten.

---

## ⚖️ Trade-offs & verworfene Alternativen

| Verworfen | Warum |
|---|---|
| **Rückseitenverschraubung** (v1-Hauptlösung) | Hinter den Traglinien ist Stahl — es gibt keine Rückseite. Zudem in keinem Regelwerk belegt |
| **Alu-Rechteckrohr 40 × 20 × 2** (v1) | 20 mm Hohlraum zwischen Schraubenkopf und Holz; M6-Kopf stünde 6 mm in die Auflagefläche |
| **Vierte Traglinie** (v1) | Einziges frei spannendes Bauteil, fiel im Durchbiegungsnachweis durch. Das Brett hat bei 950 mm Faktor 10,5 Reserve |
| **Zweite EPDM-Lage Alu/Stahl** (v1) | MB 829 Tab. 7 bewertet die Paarung mit „+"; Abdichtung wirkt am Stahl besser |
| **Zweite Schraube im Langloch bei > 120 mm** (v1) | Mit Federverschraubung konstruktiv unmöglich; N+F-Formschluss übernimmt die Schüsselsicherung |
| **Alu-Winkel** | Nach oben offener Schenkel = 6 m Wasserbrett hinter dem Holz |
| **Senkrechte Alu-Rippen + waagerechte Bretter** | ~40 Stöße über 6 m als Wassereintritte; Nut als Wasserfalle |
| **Alu-Kassetten je Feld** | Zerlegt das Brettbild; umlaufender Rahmen ist unten eine Wasserfalle |
| **Bimetall-Bohrschrauben** | Kohlenstoffstahl-Bohrspitze verbleibt im Hohlraum und rostet |
| **Zinkspray im Bohrloch** | Zink unedler als Alu → macht die Bohrstelle zur Anode |
| **A2 statt A4** | Streusalz in der Zufahrt |
| **Profilholzkrallen** | Von Krages und Osmo ausdrücklich ausgeschlossen |
| **Sichtbare Frontverschraubung** | ~150 Wassereintritte in DK-4-Fichte auf der Wetterseite |
| **Verklebung Alu/Stahl** | Nicht lösbar, nicht prüfbar, ~147 kg an einem bewegten Bauteil |
| **Flachprofil 40 × 6** (v2) | Windsog: σ_d 165–271 N/mm² gegen 136; bräuchte ~63 statt 45 Stahlbohrungen (v3) |
| **Flachprofil 40 × 4** (Nutzerfrage v3) | W = 107 mm³ — noch schwächer; kein Platz für Senkung und Holzschrauben-Sackloch |
| **40 × 8 mit 4 Löchern** (v3) | Zone A σ_d 152 > 136 — das 5. Loch ist die billigste Reserve und liefert zugleich den mittigen Festpunkt |
| **Senkkopf an Gleitpunkten** (v2) | Kegel zentriert → gleitet nicht; Scheibe unter Senkkopf unmöglich |
| **Blindnietmutter M6 A4** (v2) | Ø-9-Bohrung im Stahl, von Hand kaum setzbar; M5 trägt die 1,4 kN mit großer Reserve |
| **Offene Nietmutter** | Wasserweg vom Gewinde ins Rohrinnere |
| **Flachkopf-Nietmutter / Senkkopf 90°** | Flachkopf hebt die Leiste 1–1,5 mm an; 90°-Senkkopf braucht Senkung im Stahl = mehr verletzte Beschichtung |
| **Holzschrauben auf Leistenmitte** (v2) | Kollision mit Metallschraubenköpfen; v3: 8 mm unter Oberkante |

---

## 📋 Offene Punkte

| # | Punkt | Warum es zählt |
|---|---|---|
| **O1** | **Holzfeuchte messen** — 20-€-Gerät, 30 Sekunden | Die gemischten Breiten 100–150 mm deuten auf Innenprofilholz (DIN 68122/68126, 8–12 %) statt Fassadenware (14–18 %). Bei 10 % bräuchten die 150er bis 7 mm Fuge. **Ohne diese Zahl ist die Fugenluft nicht bemessbar** |
| **O2** | **Windlast 10,7 kN** gegen Pfosten, Fundament, Laufwagen, Endanschlag | Faktor 12 gegenüber dem offenen Rahmen. Gewicht und Fahrbreite sind geprüft — das hier ist ein davon getrennter Nachweis |
| **O3** | **Läuft die äußere Führungsrolle künftig auf Holz statt Stahl?** Gesamtaufbau ab Stahl-Vorderfläche: 8 + 0,8 + 21 = **29,8 mm ≈ 30 mm** (v3: +2 mm durch 40 × 8) (v1 lag mit dem Rechteckrohr noch bei 41 mm — das Flachprofil hat das Problem bereits verkleinert, aber nicht beseitigt) | Führungsrollen spannen den Rahmen beidseitig spielfrei ein (EP0596362A2). Quellende Fichte mit N+F-Fuge ist keine Rollenbahn. Achtung: die naheliegende Abhilfe „Verkleidung im Riegelbereich aussparen" bricht A4, weil die Aussparung über 6 m von außen sichtbar ist |
| **O4** | **Kippmoment aus der einseitigen Masse: ~50 Nm, dauerhaft** | ~147 kg mit Schwerpunkt ~39 mm vor der Rahmenmittelebene. Die Laufwagenrollen nehmen das als Rollenpaar auf, in jeder Fahrposition plus dynamisch beim Anschlagen. Das ist eine andere Frage als „trägt der Antrieb das Gewicht" |
| **O5** | Federlänge, Nuttiefe **und Federlage im 21-mm-Querschnitt** messen | geht in die Fugenbemessung UND in die Schraubenlänge (Bauteil C) ein — ohne diese Messung ist keine sichere Schraubenlänge bestimmbar |
| **O6** | ~~Wandstärke Rahmenrohr prüfen~~ — **erledigt durch Entscheidung: Blindnietmutter (v3: M5 A4 geschlossen), Klemmbereich breit wählen (typ. 0,3–3,5 mm); wenn an einem offenen Rohrende messbar, vor der Bestellung kurz prüfen (Einkaufsliste M2).** Löst die Unsicherheit auf, statt sie zu messen — bei unbekannter Wandstärke ist die Nietmutter die robustere Wahl, die Direktverschraubung (Bauteil B, Alternative) hängt direkt an einer Zahl, die nicht ermittelbar war, für eine Verbindung, die nie wieder geöffnet wird. Nur falls später doch Interesse an der genauen Wandstärke besteht: zerstörungsfrei per Ultraschall-Wanddickenmessgerät möglich, nicht nötig für diese Entscheidung | Asymmetrisches Risiko: falsch gewählte Direktschraube bei dünnerer Wand als angenommen ist eine dauerhaft schwächere, nicht nachbesserbare Verbindung; ein breiter Klemmbereich bei der Nietmutter deckt jede realistische Wandstärke ab |
| **O7** | Rahmenebenheit mit Richtlatte prüfen | Foto 3 deutet einen Versatz an |
| **O8** | Entwässerungsöffnungen im Rahmen prüfen | Kondensat im Hohlprofil ist der Angriffspunkt an der Nietmutter-Bohrung |
| **O9** | Holzschutzmittel **kupferfrei** wählen | Kupferhaltige Mittel wirken „stark korrosiv" gegenüber unedlen Metallen (Fraunhofer WKI). Für Zink belegt, für Alu Analogieschluss |

---

## 📚 Quellen

- Merkblatt 829 „Edelstahl Rostfrei in Kontakt mit anderen Werkstoffen", Informationsstelle Edelstahl Rostfrei (Autoren u. a. BAM) — https://www.edelstahl-rostfrei.de/fileadmin/user_upload/ISER/downloads/MB_829.pdf
- Merkblatt 875 „Edelstahl Rostfrei im Bauwesen" (KWK nach abZ Z-30.3-6) — https://www.edelstahl-rostfrei.de/fileadmin/user_upload/ISER/downloads/MB_875_Bauwesen_2015.pdf
- „Praxiswissen Fassade" (Sekundärzitate Fachregel 01 BDZ) — https://www.holzstrupp.de/wp-content/uploads/2021/04/pw_strupp_fassade_web.pdf
- Krages Verlegehinweise Fassade — https://www.krages-hh.de/publish/binarydata/service/verlegehinweise/1-fassade_montagetipp.pdf
- Osmo Montageanleitung Fassade — https://www.osmo.de/fileadmin/media/downloads/montageanleitungen/fassade/montageanleitung-fassade.pdf
- FVHF / fassadentechnik 1-2022, Fest-/Gleitpunkte — https://www.fassadentechnik.de/downloads/wissen-vhf/Auslegungsfragen_2022_01.pdf
- Fraunhofer WKI, „Korrosion metallischer Verbindungsmittel in Holz" (2013) — https://www.wki.fraunhofer.de/content/dam/wki/press-media/fachpublikationen/informationsdienst-holz/spezial_Korrosion_2013-02.pdf
- LWF Bayern, „Holz der Fichte" — https://www.lwf.bayern.de/forsttechnik-holz/holzverwendung/172486/index.php
- Bauer Systemtechnik, Montageanleitung Schiebetor freitragend — https://www.torautomatik-shop.de/mediafiles/PDF/Montageanleitung_Bausatz_Schiebetor_freitragend.pdf
- Windbeiwerte c_p,net, Rechenbeispiel φ = 1,0 — https://www.dlubal.com/en/support-and-learning/support/knowledge-base/001542
- q_p Windzone 2 Binnenland — https://www.mauerwerksbau-lehre.de/vorlesungen/3-sicherheitskonzept-und-einwirkungen/32-einwirkungen/323-wind
- Führungsrollen, beidseitige Einspannung — https://patents.google.com/patent/EP0596362A2/de
- proHolz Austria, Zuschnitt 23 (Gegenposition zur Fichte-Skepsis) — https://www.proholz.at/zuschnitt/23/es-kommt-drauf-an
- Bezugsprodukt Holz-Alu-Schraube (Spanplattenschraube A4 Vollgewinde TX) — https://www.schraubenhandel24.de/schrauben/spanplattenschrauben/art-9047/art-9047-spanplattenschrauben-tx-edelstahl-a4-vollgewinde-4/ · https://www.schraubenhimmel.de/schrauben/senkkopf/spanplattenschrauben-tx/
- DIN 7500 Kopfmaße (M4/M5, Alu-Stahl-Verbindung) — https://www.schrauben-lexikon.de/download/t_7500mtx-a2.pdf
- Vorbohrwerte gewindefurchende Schrauben — https://www.lederer-online.com/technik/montagehilfe/vorbohrwerte/
- Blindnietmutter Setzen (5-Schritte, Bohrlochdurchmesser) — https://www.gesipa.de/service/gesipa-erklaert/blindnietmutter-setzen-einfacher-leitfaden/

### Belegstatus — was nicht abgesichert ist

| Aussage | Status |
|---|---|
| Fachregel 01 BDZ im Volltext | Nur Sekundärzitate (Ausgabe 2018); Original kostenpflichtig |
| DIN EN 1999-1-1 Tab. D.2 (Alu/Edelstahl-Kontakt) | Existenz belegt, Inhalt nicht zugänglich — wichtigste offene Normlücke |
| Standzeit Fichte in Jahren | **Existiert nicht seriös.** proHolz verweigert Zahlen mit Begründung |
| Trennlagenpflicht Holz/Alu-UK | Nur für Holz-UK und offene Fugen belegt |
| Kupfer-Holzschutzmittel vs. **Aluminium** | Für Zink belegt, für Alu Analogieschluss |
| Differentielles Schwindmaß Fichte | 0,39 (LWF) vs. 0,33 (holzvomfach) vs. 0,25 (Praxiswert) — 18 % Streuung, nicht auflösbar ohne EC5 Tab. A.2 |

---

## 🔍 Prüfvermerk

**Unabhängige Widerlegung (Phase 2F):** durchgeführt, Verdikt auf Version 1: **`BLOCK`**.
Alle Befunde wurden nachgerechnet und bestätigt; die drei Kernentscheidungen sind ersetzt, die
gestrichenen Bauteile sind **entfernt, nicht mit einer Schutzmaßnahme umbaut**.

⚠️ **`reviewer_model: same-model-fallback`** — es war kein abweichendes Prüfmodell konfiguriert.
Die Prüfung lief auf demselben Modell wie die Erstellung. **Das ist eine reale Einschränkung der
Unabhängigkeit**, keine Formalie: gemeinsame blinde Flecken bleiben in erheblichem Maß bestehen.
Version 2 ist ungeprüft.

### Version 3 — Final-Prüfung vor Bestellung (2026-09-23)

**Modus:** Selbstkritik des Autors (Nachrechnung aller bestellrelevanten Maße), **keine unabhängige
Prüfung** dieser Version. Befunde und Disposition:

| Befund | Schwere | Disposition |
|---|---|---|
| Windsog-Biegung der Leiste nie nachgewiesen; 40 × 6 / 4 Löcher überlastet | hoch | **40 × 8, 5 Löcher**, Nachweis in Bauteil A |
| Senkkopf kann nicht gleiten; Scheiben unter Senkkopf unmöglich | hoch | Festpunkt Senkkopf, Gleitpunkte ISO 7380 in Flachsenkung |
| Kein Loch in Segmentmitte für den „mittigen" Festpunkt | mittel | Raster 95/545/995/1445/1895 |
| 3 × 2,00 m + Fugen > 6,00 m | mittel | L_seg nach Aufmaß (1990 mm) |
| Holzschrauben und Metallköpfe auf gleicher Höhe | mittel | Höhenzonen 14 mm / 8 mm |
| A4-M6-Nietmutter von Hand kaum setzbar, offene Ausführung = Wasserweg | mittel | M5 A4 geschlossen, kleiner Senkkopf, Zweihandzange |
| MS-Polymer nass unter Gleitpunkt klebt fest | mittel | 24 h Aushärten vor Alu-Montage |
| Veraltete Angaben (Langloch-Reste, „4,0 × 40", Stückzahlen ~30 statt 36) | niedrig | bereinigt |

**Grenzen:** Nachweise sind Ingenieur-Abschätzungen (Balken-FE je Segment, Lastannahmen wie v2), kein
Statiknachweis; Gewindetiefe der geschlossenen Nietmutter und Ausziehwert der Holzschraube im Alu
werden durch die Pflicht-Proben (Bauteil B/C) abgesichert, nicht durch Herstellerwerte. O2–O4
(Windlast auf Pfosten/Laufwagen, Führungsrollen, Kippmoment) bleiben unverändert offen — sie betreffen
nicht die jetzige Bestellung, wohl aber die Frage, ob das Tor vollflächig beplankt werden sollte.


**Freigabe:** 2026-09-23 durch den Nutzer, auf Basis der Autoren-Selbstprüfung (keine unabhängige Prüfung von v3 — bewusst in Kauf genommen).
