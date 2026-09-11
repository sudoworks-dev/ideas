# Konstruktionskonzept: Fichte-Verkleidung auf freitragendem Stahl-Schiebetor (6,0 × 1,90 m)

📌 **Status:** DRAFT — **Version 2** (nach unabhängiger Widerlegung grundlegend überarbeitet)
📅 **Erstellt:** 2026-09-09
🎯 **Ziel:** Opferschicht-Prinzip — Holz ist Verschleißteil, die Alu-Ebene bleibt dauerhaft

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
> Weitere korrigierte Rechenfehler aus v1: Lochspiel Ø 8 um M6 ist **1,00 mm**, nicht 1,25 mm ·
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

| # | Kriterium | v2 |
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

**Drei Alu-Flachprofile 40 × 6 mm, deckungsgleich auf die drei vorhandenen Stahlriegel geschraubt.
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
     │              │      │ 6 mm   │ │0,8 │ │          │
     │  40 × 40 mm  │──────│ direkt │─│ mm │─│  Fichte  │
     │   Stahlriegel│ bündig│aufge-  │ │    │ │  sichtbar│
     │              │ auf-  │schraubt│ │    │ │          │
     └──────────────┘ liegend└────────┘ └────┘ └──────────┘
        (Innenseite)                              (Außenseite)
     ◄── Rahmentiefe ──►◄─ 6 ─►◄0,8►◄──── 21 ────►
```

Gesamtaufbau in der Tiefe: Stahl-Vorderfläche → Alu 6 mm (flächig aufliegend, verschraubt) →
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
| Profil | **Flachprofil 40 × 6 mm**, EN AW-6060 | 0,648 kg/m → 3 × 6 m = **11,7 kg** |
| Oberfläche | **blank genügt** (EN AW-6060 bildet selbst eine Oxidschutzschicht) | Vom Stahlriegel weitgehend verdeckt. Beschichtung auf der Anode bringt laut MB 829 nichts und schadet bei Beschädigung. Blanke Kanten von innen ggf. mit Ausbesserungslack übermalen |
| **Warum flach, nicht Rohr** | 6 mm massiv | Die Schraube muss durch das Alu ins Holz bzw. in die Nietmutter — ein geschlossenes Rohr legt 20 mm Hohlraum dazwischen. **Das war der tödliche Fehler in v1** |
| **Warum 6 mm, nicht 5** | Senkkopf M6 braucht ~3,3 mm Senktiefe | Restwand 2,7 mm. Der M6-Kopf liegt **bündig** — die Brettrückseite liegt plan auf, keine 45 Beulen unter der Verkleidung |
| **Warum flach, nicht Winkel** | — | Ein Winkel hätte einen nach oben offenen Schenkel = 6 m Wasserbrett. Ein Flachprofil hat gar keinen Schenkel. **Antwort auf „Winkel oder Profile?": Flachprofil, weder noch** |
| Segmentierung | **bis 2,0 m, an die Lagerlänge angepasst** (Handelsware kommt als 2,0-m-Stangen -> 0 % Verschnitt), 10 mm Stoßfuge | s. u. |

**Wärmedehnung:**
```
ΔL_Alu   = 6000 × 23,1·10⁻⁶ × 100 K = 13,86 mm
ΔL_Stahl = 6000 × 12,0·10⁻⁶ × 100 K =  7,20 mm
Differenz über 6,0 m                =  6,66 mm
```

**Wichtig — und in v1 falsch behandelt:** Die Zwangsspannung bei starrer Fesselung ist
σ = E·Δα·ΔT ≈ **78 N/mm² und hängt nicht von der Segmentlänge ab**. Kurze Segmente allein helfen
nicht. Ein 40 × 6-Flachprofil beult bei 600 mm Befestigungsabstand schon bei σ ≈ 6 N/mm² aus.
**Die Verschiebung muss also tatsächlich stattfinden können — Langlöcher sind nicht optional.**

- **Ein Festpunkt je Segment, MITTIG im Segment** (enges Rundloch: Ø 5,5 bei M5 / Ø 6,5 bei M6)
- **Alle übrigen Punkte: leicht überweites Rundloch** — Ø 7 bei M5, Ø 8 bei M6. **Kein Langloch nötig** — s. u.
- Bedarf am freien Ende bei 2,0 m Segment (Festpunkt am Ende): `2000 × 11,1·10⁻⁶ × 100 K = 2,22 mm`. Langloch 6,5 × 14 um M5 gibt ±4,5 mm Spielweg → massig Reserve.
- Stoßfugen über einem senkrechten Stahlstab sind ein Komfortmerkmal, kein Muss: die Fuge trägt nichts, ist 10 mm breit, hinter dem Holz, nur von innen sichtbar. Deshalb Lagerlänge vor Pfostenraster.

**Warum kein Langloch:** Mit dem Festpunkt mittig im 2,0-m-Segment ist der äußerste Befestigungspunkt
nur 1,0 m entfernt. Bei realistischem Einbau (~15 °C, Bereich −20…+80 °C) bewegt sich dieser Punkt
+0,72 mm im Sommer / −0,39 mm im Winter. Ein Ø-7-Rundloch um eine M5 (bzw. Ø 8 um M6) gibt ±1,0 mm
radiales Spiel — deckt das mit Reserve. Das spart das Ausfeilen/Fräsen von ~24 Schlitzen: nur zwei
Bohrerdurchmesser, sonst nichts. Voraussetzung ist wirklich der **mittige** Festpunkt; sitzt er am
Ende, wächst der Abstand auf 2,0 m und das Rundloch wird zu knapp.

**Beim Anzeichnen vor Ort:**
- **Senkrechte Stäbe meiden.** Wo ein senkrechter Rahmenstab den Riegel kreuzt (~alle 1,2 m,
  geschweißt), darf kein Loch sitzen. Landet eine der vier Positionen dort: Loch um ±50 mm
  verschieben (der 550-mm-Abstand hat den Spielraum). Festpunkt wahlweise bei 750 **oder** 1250 mm.
- **Löcher der drei Riegel gegeneinander versetzen** — den mittleren Riegel ~100 mm versetzt
  anreißen, verteilt die Löcher besser über den Rahmenquerschnitt.
- **Gleitpunkte nur mäßig anziehen, mit planer A4-Scheibe (kein Gummi unter dem Kopf).** Ein
  festgezogener Gleitpunkt ist reibschlüssig geklemmt und gleitet nicht — die Abdichtung des
  Bohrlochs erfolgt deshalb **am Stahl**, nicht unter dem Schraubenkopf (Bauteil B)
- Stoßfugen möglichst über einem senkrechten Stahlstab

*(v1 rechnete hier mit „Ø 8 um M6 = ± 1,25 mm Spiel". Richtig sind **1,00 mm** — und damit weniger
als der Bedarf. Der Fehler ist mit dem Langloch erledigt.)*

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
Flächenverhältnis: ~38 mm² blanker Stahl (Anode) gegen die deutlich größere A4-Fläche (Kathode) —
**kleine Anode an großer Kathode, das ungünstige Verhältnis.** Genau der Mechanismus, den MB 829 §6
beschreibt:

> *„Die Beschädigungen in der Beschichtung führen zu kleinflächigen Anoden, die dann mit hoher
> Abtragungsrate korrodieren können."*

v1 sah als Abhilfe eine EPDM-Dichtscheibe unter dem Schraubenkopf vor. **Die sitzt auf der
Alu-Vorderseite und deckt am Stahl nichts ab** — sie war wirkungslos.

| Parameter | Festlegung | Begründung |
|---|---|---|
| Verbindungsmittel | **Blindnietmutter M6 A4** + **Senkkopfschraube M6 × 16 A4** | 6 mm Alu + ~10 mm Gewinde. Lösbar, kein Fremdmaterial verbleibt |
| **A4 statt A2** | 1.4401 statt 1.4301 | Zufahrt = Streusalz. abZ Z-30.3-6: A2 = KWK II „ohne nennenswerte Chloridbelastung", A4 = KWK III „bei Tausalz" |
| **Abdichtung am Stahl** | **Nietmutter-Flansch in MS-Polymer / Butyl einbetten, vor dem Setzen** | Verschließt den Wassereintritt **dort, wo er entsteht** — nicht 6 mm weiter außen |
| Unter dem Schraubenkopf, Festpunkt | plane A4-Scheibe, voll angezogen | starr, trägt die Konstruktionslast |
| Unter dem Schraubenkopf, Gleitpunkte | **A4-Federscheibe/Tellerfeder statt planer Scheibe** | gibt unabhängig vom Anzugsmoment eine definierte, moderate Anpresskraft — voll angezogen würde die Reibung den Gleitpunkt trotz überweitem Loch faktisch festklemmen |
| Raster | **4 Löcher je 2,0-m-Segment: 200 / 750 / 1250 / 1800 mm ab Segmentanfang** (Randabstand 200, Lochabstand 550 mm). Höhe: mittig, 20 mm von jeder Kante. 36 Punkte gesamt | reine Sogbeanspruchung; ~300 N je Punkt (Rand/Bemessung ~720 N) gegen mehrere kN Ausziehwiderstand |

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

#### Alternative bei O6 ≥ 2,5 mm: Direktverschraubung statt Blindnietmutter

Spart das Setzgerät. Zwei Bohrdurchmesser, deshalb in dieser Reihenfolge:

1. **Alu-Durchgangsloch zuerst, auf der Werkbank** (vor der Montage): ~4,5 mm (M4) bzw. ~5,5 mm (M5),
   Klemmung, kein Gewinde. Senkung fräsen, Tiefe 2,7 mm (M4/M5, siehe Kopfmaße unten).
2. **Alu-Profil am Rahmen positionieren, fixieren.**
3. **Durchs vorhandene Alu-Loch ankörnen** — dient als Bohrbuchse, verhindert Verlaufen.
4. **Stahl-Kernloch bohren**, durch das Alu-Loch hindurch: Richtwert ~3,3 mm (M4) / ~4,2 mm (M5) —
   **verbindlich ist die Angabe auf der jeweiligen Schraubenpackung**, DIN 7500 nennt diese Werte
   ausdrücklich nur als Richtwerte. Nur bis zur Wandstärke, nicht durch die Rückwand.
5. **Bohrspäne sofort entfernen.**
6. **Dichtmasse (MS-Polymer/Butyl) auf die Stahloberfläche um das Kernloch auftragen** — vor dem
   Verschrauben, nicht danach. Sitzt genau an der Stelle, wo die Beschichtung verletzt wird.
7. **Schraube eindrehen**, mäßiges Drehmoment — gewindefurchende Schrauben brauchen anfangs mehr
   Kraft, werden leichter, sobald das Gewinde geformt ist. Nicht überdrehen (dünne Wand).
8. **Kontrolle:** Dichtmasse quillt sichtbar minimal am Rand aus — Zeichen für vollen Anpressdruck.

| Parameter | Festlegung |
|---|---|
| Norm/Typ | **DIN 7500, Form M** (Senkkopf, Innensechsrund/TX) |
| Material | **A4** (1.4401/1.4571) — wegen Streusalz; schlechter gelagert als A2, Lieferzeit einplanen |
| Durchmesser | **M4** (< 2,5 mm Wand nicht empfohlen) oder **M5** (≥ 2,5 mm) |
| Kopf-Ø max / Senktiefe | M4: 8,4 / 2,7 mm · M5: 9,3 / 2,7 mm |
| Antrieb | TX 20 (M4) / TX 25 (M5) |
| Länge | 6 mm (Alu) + Wandstärke + ~1 mm Reserve → meist 10–12 mm |
| Alu-Durchgangsloch | ~4,5 mm (M4) / ~5,5 mm (M5) |
| Stahl-Kernloch | Richtwert ~3,3 mm (M4) / ~4,2 mm (M5) — **Packungsangabe verbindlich** |

Quelle Kopfmaße: [Wegertseder DIN 7500 Datenblatt](https://www.schrauben-lexikon.de/download/t_7500mtx-a2.pdf).

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
| Vorbohren Holz | Ø 3,0 mm | Fichte spaltet an der Feder sonst |
| Vorbohren Alu | Ø 3,2 mm | gewindefurchender Sitz im Aluminium |
| Anzahl | **1 Schraube je Brett und Traglinie** = 3 pro Brett | s. u. |
| Abstand zum Brettende | ≥ 30 mm | Krages / Osmo |

#### Schraubenlänge — Formel statt fixer Zahl, weil sie von der Federlage abhängt

**Korrektur:** Eine frühere Fassung nannte hier pauschal 40 mm. Das ist zu lang und stößt bei einem
45°-Winkel mit hoher Wahrscheinlichkeit **durch das 6-mm-Alu hindurch in den Stahl** — genau die
Bohrung im Stahl, die diese Konstruktion für immer vermeiden soll.

Aufbau in der Tiefe, ab der sichtbaren Holzfläche:
```
0 ── 21,0 mm  Holz
21,0 ── 21,8 mm  EPDM
21,8 ── 27,8 mm  Alu (6 mm)
27,8 mm  ──────  Stahl — darf nicht erreicht werden
```
Bei 45° legt die Schraube pro 1 mm Länge nur `sin 45° ≈ 0,71 mm` Tiefe zurück. Die richtige Länge
hängt davon ab, **wo die Feder im 21-mm-Querschnitt tatsächlich sitzt** — das variiert je nach
Profil und ist ohne Messung nicht seriös anzugeben:

```
L = (Zieltiefe im Alu − Tiefe des Ansatzpunkts an der Feder) / sin(45°)
```

Zieltiefe = 21,8 mm (Alu-Anfang) + 3–4 mm Einbindung — **nicht mehr**, sonst zu nah am Stahl.

| Federlage (Ansatzpunkt) | Schraubenlänge für 3–4 mm Alu-Einbindung |
|---|---|
| eher vorn (~7 mm Tiefe) | ~25–27 mm |
| mittig (~10,5 mm Tiefe) — typischer Richtwert | ~20–22 mm |
| eher hinten (~14 mm Tiefe) | ~15–17 mm |

**Vorgehen:** Federlage an einem Reststück messen (s. O5), dann mit obiger Formel die Länge
bestimmen, an einem Probestück mit tiefenmarkiertem Bohrer testen (kein Durchstoß spürbar), **erst
danach** die Schrauben für das ganze Tor beschaffen.

**Nachweis mit dem Randzonenwert — nicht mit einem Mittelwert:**

```
Ungünstigstes Brett: 150 mm × 2,0 m, Zone A, 3 Befestigungspunkte
Einzugsfläche je Schraube = 0,150 × 2,0 / 3   = 0,100 m²
F_k = 1,495 kN/m² × 0,100 m²                  =  150 N
F_d = 1,5 × 150                               =  224 N
```
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

## 📦 Materialliste

| Pos | Artikel | Menge |
|---|---|---|
| 1 | Alu-Flachprofil 40 × 6, EN AW-6060, **blank** | 18 m — z. B. 3 Gebinde "3 × 200 cm" (9 Segmente à 2,0 m, 0 % Verschnitt, ~134 €) |
| 2 | Alu-Blech 2 mm abgekantet, Abdeckprofil | 6,1 m |
| 3 | Blindnietmutter M6, A4 | ~30 St. |
| 4 | Senkkopfschraube M6 × 16, A4 | ~30 St. |
| 5 | Scheibe M6 A4, plan | ~30 St. |
| 6 | **Senkkopfschraube 4,0 × [Länge nach Messung, s. Bauteil C], A4, Vollgewinde** | ~150 St. |
| 7 | EPDM-Fassadenband 0,8 × 50 mm | 20 m |
| 8 | MS-Polymer / Butyl-Dichtmasse | 1 Kartusche |
| 9 | Hirnholzversiegelung | 1 Gebinde |
| 10 | Ausbesserungslack RAL Rahmen | 1 Stift |
| — | Blindnietmuttern-Setzgerät | einmalig ~50 € |

**Zuwachs Flügelmasse:** ~127 kg Holz + 11,7 kg Alu + ~4 kg Abdeckung/Befestiger ≈ **143 kg**
(v1 lag bei ~150 kg).

---

## 🔧 Montagereihenfolge

1. **Holzfeuchte messen** (O1). Alles Weitere hängt davon ab. Bei < 13 % zuerst akklimatisieren.
2. **Aufmaß** — alle ⚠️-Annahmen prüfen: Riegellagen, Rahmenebenheit mit Richtlatte, Wandstärke,
   Federlänge und Nuttiefe an einem Brettpaar.
3. **Alu-Segmente ablängen** (bis 2,0 m, Lagerlänge nutzen), Bohrbilder **liegend am Boden** anreißen und bohren:
   je Segment **mittig** ein enges Loch (Festpunkt), alle übrigen als überweites Rundloch (Ø 7 bei M5 / Ø 8 bei M6). Senkungen fräsen.
4. **Stahl bohren.** Späne sofort entfernen. Erreichbaren Bohrlochrand lackieren.
5. **Blindnietmuttern setzen**, Flansch vorher in MS-Polymer einbetten.
6. **EPDM-Band auf die Alu-Vorderflächen** kleben.
7. **Alu-Segmente montieren**, mittigen Festpunkt zuerst — voll angezogen. Übrige Schrauben (Gleitpunkte,
   mit Federscheibe): **handfest plus ~1/4–1/2 Umdrehung**, nicht mehr. Probe: Profil an der Stelle
   von Hand längs schieben — Widerstand ist ok, völlige Starrheit heißt zu fest nachgezogen. 10 mm
   Stoßfugen einhalten.
   Fluchtung prüfen (Toleranz ± 5 mm auf 2 m, Fachregel 01).
8. **Bretter vorbereiten:** Grund- und Zwischenanstrich **allseitig vor Montage**. Untere Stirnenden
   15° anschrägen, Hirnholz versiegeln. Kanten ≥ 2 mm runden.
9. **Von einer Seite her verlegen** — Feder voraus. Je Brett: einlegen, Fugenluft mit Distanzplättchen
   einstellen, ausrichten, an jeder der 3 Traglinien Ø 3,0 durch den Federgrund vorbohren, Ø 3,2 ins
   Alu nachbohren, 4,0 × 40 schräg eindrehen. Nächstes Brett deckt die Schraube ab.
   **Von vorn, im Stehen, von einer Person machbar.**

   > **Praxis-Tipp Zielgenauigkeit:** Die drei Alu-Profile sind nur ~40 mm hoch, der Rest der
   > 2 m Bretthöhe ist dahinter leer — die Präzision entscheidet sich beim **Anreißen, nicht
   > beim Bohren**. Vor der Montage die drei Riegelhöhen auf jedes Brett (Federkante) übertragen,
   > z. B. mit einer Schablone oder durch Anhalten am Rahmen. Der 45°-Winkel selbst läuft **in der
   > Waagerechten** — Bohrer seitlich kippen (Feder-Außenkante → Tiefe), **nicht nach oben/unten**.
   > So bleibt die einmal angerissene Höhe über den ganzen Bohrvorgang exakt erhalten.
10. **Randbretter** symmetrisch auftrennen; letztes Brett muss von vorn befestigt werden — dort einen
    unauffälligen Punkt wählen (Nutgrund des Nachbarn oder oberste/unterste Zone).
11. **Abdeckprofil oben** montieren, Gefälle prüfen.
12. **Endanstrich** vorderseitig.
13. **Funktionsprobe:** Tor mehrfach komplett verfahren, Führungsrollen und Endanschlag beobachten.

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
| **Verklebung Alu/Stahl** | Nicht lösbar, nicht prüfbar, ~143 kg an einem bewegten Bauteil |

---

## 📋 Offene Punkte

| # | Punkt | Warum es zählt |
|---|---|---|
| **O1** | **Holzfeuchte messen** — 20-€-Gerät, 30 Sekunden | Die gemischten Breiten 100–150 mm deuten auf Innenprofilholz (DIN 68122/68126, 8–12 %) statt Fassadenware (14–18 %). Bei 10 % bräuchten die 150er bis 7 mm Fuge. **Ohne diese Zahl ist die Fugenluft nicht bemessbar** |
| **O2** | **Windlast 10,7 kN** gegen Pfosten, Fundament, Laufwagen, Endanschlag | Faktor 12 gegenüber dem offenen Rahmen. Gewicht und Fahrbreite sind geprüft — das hier ist ein davon getrennter Nachweis |
| **O3** | **Läuft die äußere Führungsrolle künftig auf Holz statt Stahl?** Gesamtaufbau ab Stahl-Vorderfläche: 6 + 0,8 + 21 = **27,8 mm ≈ 28 mm** (v1 lag mit dem Rechteckrohr noch bei 41 mm — das Flachprofil hat das Problem bereits verkleinert, aber nicht beseitigt) | Führungsrollen spannen den Rahmen beidseitig spielfrei ein (EP0596362A2). Quellende Fichte mit N+F-Fuge ist keine Rollenbahn. Achtung: die naheliegende Abhilfe „Verkleidung im Riegelbereich aussparen" bricht A4, weil die Aussparung über 6 m von außen sichtbar ist |
| **O4** | **Kippmoment aus der einseitigen Masse: ~50 Nm, dauerhaft** | ~143 kg mit Schwerpunkt ~37 mm vor der Rahmenmittelebene. Die Laufwagenrollen nehmen das als Rollenpaar auf, in jeder Fahrposition plus dynamisch beim Anschlagen. Das ist eine andere Frage als „trägt der Antrieb das Gewicht" |
| **O5** | Federlänge, Nuttiefe **und Federlage im 21-mm-Querschnitt** messen | geht in die Fugenbemessung UND in die Schraubenlänge (Bauteil C) ein — ohne diese Messung ist keine sichere Schraubenlänge bestimmbar |
| **O6** | ~~Wandstärke Rahmenrohr prüfen~~ — **erledigt durch Entscheidung: Blindnietmutter M6, Klemmbereich breit wählen (z. B. 0,5–4,5 mm).** Löst die Unsicherheit auf, statt sie zu messen — bei unbekannter Wandstärke ist die Nietmutter die robustere Wahl, die Direktverschraubung (Bauteil B, Alternative) hängt direkt an einer Zahl, die nicht ermittelbar war, für eine Verbindung, die nie wieder geöffnet wird. Nur falls später doch Interesse an der genauen Wandstärke besteht: zerstörungsfrei per Ultraschall-Wanddickenmessgerät möglich, nicht nötig für diese Entscheidung | Asymmetrisches Risiko: falsch gewählte Direktschraube bei dünnerer Wand als angenommen ist eine dauerhaft schwächere, nicht nachbesserbare Verbindung; ein breiter Klemmbereich bei der Nietmutter deckt jede realistische Wandstärke ab |
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
