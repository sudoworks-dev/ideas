# Strukturierte Nischen-Erschließung mit Agentic Engineering — Erstprinzipien-Bewertung

**Status:** DRAFT (Revision 2, nach unabhängiger Gegenprüfung)
**Datum:** 2026-09-18
**Methodischer Rahmen:** Bewertung ausschließlich aus Erstprinzipien und externer Recherche. Weisungsgemäß wurden weder das Memory-System noch andere Konzeptdokumente unter `.sde_docs/concept/` gelesen oder referenziert. Baseline: `master` @ `9a89d88`, Arbeitsbaum mit unrelated Änderungen unter `.sde_docs/concept/garten/`; keine Remote-Aktualisierung durchgeführt oder erforderlich.

---

## 1. Problem Statement

### Die eigentliche Frage

Der Nutzer stellt zwei Fragen, die auseinandergehalten werden müssen:

1. **Meta-Frage:** Lässt sich eine Einnahmequelle *strukturiert und planbar* erarbeiten — durch systematische Recherche und Prozess — statt auf eine glückliche Idee zu warten?
2. **Konkrete Frage:** Ist die skizzierte Pipeline (AI-Agenten identifizieren Hardware-Nischen → generieren CAD/Schaltplan/Firmware → On-Demand-Fertigung → D2C-Verkauf) der richtige Weg dorthin?

Diese Bewertung beantwortet beide getrennt, weil die Antworten unterschiedlich ausfallen.

### Ausgangslage (bestätigt durch Rückfrage am 2026-09-18)

| Parameter | Wert |
|---|---|
| Zielgröße | Noch offen; Arbeitsannahme **2–3 k€ MRR in 12–18 Monaten** als erste Tragfähigkeitsschwelle. Skalierungsgrenze in §6. |
| Marktzugang | **Kein privilegierter Branchenzugang** — Kaltstart. |
| Kernkompetenz | Ingenieur, sehr stark in Agentic Engineering (Claude Code / Codex, eigene Agenten-Skills und -Frameworks). |
| Gegenprüfung | Durchgeführt, Verdict REVISE, Befunde eingearbeitet (§8). |

### Angestrebtes Ergebnis

Eine belastbare Go/No-Go-Aussage zur Geschäftsrichtung „AI-gestützte Hardware-Nischen", plus — falls No-Go — die *nächstbeste* Verwendung derselben Fähigkeit.

### Akzeptanzkriterien für dieses Konzept

- **A1** — den bindenden Engpass benennen und quantifizieren, nachvollziehbar aus den eigenen Tabellen.
- **A2** — die These „Marge über Software-Mehrwert bei reduzierter Mechanik" mit Zahlen prüfen, nicht mit Plausibilität.
- **A3** — das genannte Beispiel (Futterspender) konkret falsifizieren oder bestätigen.
- **A4** — ausführbarer Prozess mit Abbruchkriterien, unter 5 k€ Cash-Risiko je Versuch.
- **A5** — offenlegen, wo die Analyse unsicher ist und welche Aussage durch Nutzerkontakt widerlegbar wäre.

---

## 2. Erstprinzipien-Analyse: Wo liegt der Engpass wirklich?

### 2.1 Zerlegung des Wegs bis zum ersten Euro

Für ein eigenmarkiges, vernetztes Gerät im EU-Markt. Die Spalte „AI-Hebel" schätzt, wie stark Agentic Engineering den jeweiligen Schritt komprimiert.

| # | Schritt | Dauer solo, ohne AI | AI-Hebel | Dauer mit AI | Cash |
|---|---|---|---|---|---|
| 1 | Nischenidentifikation | 2 Wo | **hoch** | 0,5 Wo | 0 |
| 2 | Mechanik / CAD / Druckiterationen | 6 Wo | gering | 4 Wo | ~300 € |
| 3 | Elektronik: Schaltplan, Layout, 2 Board-Spins | 8 Wo | gering | 6 Wo | ~600 € |
| 4 | Firmware | 6 Wo | **hoch** | 1,5 Wo | 0 |
| 5 | Backend + App | 6 Wo | **hoch** | 2 Wo | 300–500 € |
| 6 | Konformität: EMV, RED-Funk, RED-Cybersecurity, techn. Doku | 14 Wo | **nahe null** | 13 Wo | **6.000–20.000 €** |
| 7 | Marktzugangs-Registrierungen (EAR/WEEE, Garantie, LUCID) — parallel | 4 Wo | nahe null | 4 Wo | 600–2.000 €/Jahr |
| 8 | Erstserie, Verpackung, Logistik | 6 Wo | gering | 5 Wo | 5.000–8.500 € |
| 9 | Go-to-Market, erste Verkäufe | 8 Wo | mittel | 6 Wo | Werbebudget |
| | **Summe** | **60 Wo** | | **42 Wo** | **12.800–31.900 €** |
| | *ohne den parallelen Schritt 7* | *56 Wo* | | *38 Wo* | |

**Zeitersparnis: 30 % (32 % ohne den parallelen Schritt).** Das ist Amdahls Gesetz in Reinform. Die AI beschleunigt die Schritte 1, 4, 5 um Faktor 3–4 — aber diese machen nur rund ein Viertel des Pfades und **praktisch null Prozent der Cash-Kosten** aus. Die Schritte 6, 7, 8 dominieren Geld und Kalender und sind gegen Agenten weitgehend immun: EMV-Messung ist ein physikalischer Vorgang in einer Absorberhalle mit Terminvorlauf, keine Generierungsaufgabe.

**Zur Cash-Spanne:** Die Untergrenze von ~13 k€ unterstellt vorzertifiziertes Funkmodul, selbst erstellte technische Dokumentation und keine benannte Stelle. Die Obergrenze von ~32 k€ unterstellt Fremdvergabe der Dokumentation und Einbeziehung einer benannten Stelle. **Das im Folgenden verwendete Mittelszenario ist ~15 k€** (vorzertifiziertes Modul, Doku in Eigenleistung, Eigenwerkzeuge, Erstserie 100 Stück) — es wird durchgehend als *Szenario* und nicht als Punktschätzung geführt. Werbebudget ist in keiner Zahl enthalten.

> **Kernbefund (A1):** Der bindende Engpass eines Hardware-Produktgeschäfts in der EU ist nicht Engineering-Durchsatz. Er ist **Fixkosten pro SKU aus Konformität, Marktzugang und Logistik** — plus Distribution. Die Pipeline optimiert den nicht-bindenden Engpass.

Auch die Schritte 2 und 3 sind bewusst mit „gering" bewertet: Text-to-CAD ist 2026 für Konzeptexploration nutzbar, liefert aber überwiegend keine produktionsreifen, parametrischen Modelle; die Lücke zwischen Marketing und Realität ist hier am größten, insbesondere bei Gehäusen und Mehrteil-Baugruppen ([getleo.ai, 2026](https://www.getleo.ai/blog/can-ai-generate-cad-models) — Anbieterquelle, siehe §6). PCB-Layout und DFM bleiben manuell-iterativ, und jede Iteration kostet Fertigungsvorlauf, nicht Denkzeit.

### 2.2 Die Konformitätskosten im Detail

| Posten | Kosten | Quelle |
|---|---|---|
| EMV-Prüfung Gesamtgerät (akkreditiert) | 1.500–10.000 € | [aestechno](https://www.aestechno.com/en/ce-red-certification-iot/) |
| RED-Funkprüfung | 3.000–8.000 €, mit vorzertifiziertem Modul 30–50 % weniger | [aestechno](https://www.aestechno.com/en/ce-red-certification-iot/), [compliancetesting.com](https://compliancetesting.com/ce-certification-for-espressif-esp32-devices/) |
| Technische Doku / DoC bei Fremdvergabe | 2.000–6.000 € | [aestechno](https://www.aestechno.com/en/ce-red-certification-iot/) |
| Stiftung EAR / ElektroG: Registrierung + **insolvenzsichere Garantie** (B2C-Pflicht, jährlich) | Garantie z. B. 0,34 % p. a. beim Dienstleister, plus Grundgebühren und Rücknahmesystem | [stiftung-ear.de](https://www.stiftung-ear.de/de/themen/elektrog/hersteller-bv/garantie), [stiftung-ear.de EN](https://www.stiftung-ear.de/en/topic-areas/find-out-your-obligation-as-a-producer/) |
| VerpackG / LUCID + Systembeteiligung | wenige hundert €/Jahr | [ecosistant](https://www.ecosistant.eu/en/epr-authorized-representative-guide) |

*Quellenvorbehalt:* Die drei Prüfkostenzeilen stützen sich auf **dieselbe Quelle**. Vor einer echten Investitionsentscheidung sind zwei Laborangebote einzuholen — die Zahl, auf der dieses Konzept steht, ist derzeit ein Einzelbeleg (§6).

Drei Punkte, die in der Skizze fehlen und die Rechnung verschieben:

**(a) RED-Cybersecurity ist seit dem 01.08.2025 verbindlich.** Die delegierte Verordnung (EU) 2022/30 zu Art. 3(3) d/e/f gilt für *jedes* Funkgerät, das selbst über das Internet kommunizieren kann — direkt oder über anderes Gerät. Die Normenreihe EN 18031-1/-2/-3 wurde am 30.01.2025 im Amtsblatt veröffentlicht. Die Konformitätsvermutung über die harmonisierte Norm ist **eingeschränkt**: bei Passwortdurchsetzung, Kindersicherung und Updatemechanismus greifen Restriktionen, die eine Bewertung durch eine benannte Stelle erzwingen können ([SGS](https://www.sgs.com/en-se/news/2025/06/red-cybersecurity-requirements-mandatory-on-1-august-2025), [In Compliance Magazine](https://incompliancemag.com/reds-cybersecurity-requirements-update-en-18031-x2024/), [SCHUTZWERK](https://www.schutzwerk.com/en/compliance/red/)). Ein ESP32-Gerät mit Cloud-Anbindung und App fällt exakt hierunter.

**(b) Der Cyber Resilience Act erzeugt eine *unbefristete* Pflicht pro SKU.** Meldepflichten für aktiv ausgenutzte Schwachstellen und schwerwiegende Vorfälle gelten **seit dem 11.09.2026** — also bereits jetzt — unabhängig davon, wann das Produkt in Verkehr gebracht wurde. Die vollen Anforderungen (Security-by-Design, Schwachstellenbehandlung über den Supportzeitraum, SBOM, Transparenz) gelten ab **11.12.2027** ([EU-Kommission](https://digital-strategy.ec.europa.eu/en/policies/cra-reporting), [Finite State](https://finitestate.io/blog/cyber-resilience-act-timeline-2026-2027)).

Kleinst- und Kleinunternehmen sind **nicht vom CRA befreit**, erhalten aber zwei konkrete Erleichterungen: Art. 64(10)(a) schließt Bußgelder für das Versäumen der Fristen aus Art. 14(2)(a) und 14(4)(a) aus — **die Meldepflicht selbst bleibt, nur die Sanktion für Verspätung entfällt** —, und die Kommission kann ein vereinfachtes Format der technischen Dokumentation für Kleinst- und Kleinunternehmen einführen ([craact.eu, Art. 64](https://www.craact.eu/article-64-penalties/), [EU-Kommission, CRA & MSMEs](https://digital-strategy.ec.europa.eu/en/policies/cra-msmes)). Alle übrigen Verstöße bleiben voll bußgeldbewehrt.

Strukturell wichtig für eine *Pipeline*: Jedes ausgelieferte SKU erzeugt eine dauerhafte, nicht delegierbare Betriebspflicht. Ein Portfolio aus 10 Geräten ist ein Portfolio aus 10 Lebenszyklus-Verpflichtungen, die sich auch dann nicht auflösen, wenn ein Produkt sich nicht verkauft hat. Man kann ein erfolgloses Hardware-SKU nicht abschalten wie eine Landingpage.

**(c) Die insolvenzsichere Garantie gilt nur für B2C.** Hersteller ausschließlich gewerblich genutzter Geräte müssen sie bei der Registrierung nicht nachweisen ([stiftung-ear.de](https://www.stiftung-ear.de/de/themen/elektrog/hersteller-bv/garantie)). Ein konkreter, quantifizierbarer Vorteil von B2B gegenüber B2C.

### 2.3 Der Portfolio-Trugschluss

Die Skizze überträgt implizit eine Softwarelogik: viele Versuche, geringe Grenzkosten pro Versuch, ein Treffer trägt das Portfolio. Diese Logik funktioniert, weil in Software die Grenzkosten je Versuch gegen null gehen.

In EU-regulierter Hardware sind die Grenzkosten je Versuch **~15 k€ Cash (Spanne 13–32 k€) plus eine dauerhafte Lebenszykluspflicht**. Damit kehrt sich die Portfoliologik um:

```
Software-Portfolio:   Wert = Treffer × Ertrag − n × ~0          → n erhöhen ist gut
Hardware-Portfolio:   Wert = Treffer × Ertrag − n × 15k€ − n × Lifecycle
                                                                → n erhöhen ist teuer
```

Die Pipeline erhöht genau die Variable, die man in dieser Domäne *senken* muss. Sie ist ein Durchsatzverstärker vor einem Kostenengpass.

### 2.4 Der Moat-Punkt

Die Skizze setzt die Marge auf „intelligente Software und Logik statt teurer Mechanik". Das ist als *Kostenargument* richtig und als *Verteidigungsargument* falsch — verstärkt durch die eigene Prämisse: Wenn Agentic Engineering die Firmware- und Backend-Erstellung um Faktor 3–4 beschleunigt, dann tut es das **für jeden Wettbewerber**. Ein Vorteil, der allen gleichzeitig zuwächst, ist kein Vorteil, sondern eine neue Baseline. Der Software-Anteil ist damit der am schnellsten kommoditisierende Teil des Produkts.

Tragfähige Verteidigungsstellungen in kleinen Hardware-Nischen sind: Vertriebskanal, Marke/Vertrauen, installierte Basis mit Wechselkosten, regulatorische Eintrittsbarriere, Skaleneffekte im Werkzeugbau.

Die regulatorische Barriere wirkt in beide Richtungen: Sie ist ein Burggraben **für den, der sie bereits bezahlt hat**. Als Neueinsteiger zahlt man die Maut; als Inhaber eines einzelnen langlebigen SKU profitiert man davon. Daraus folgt direkt die Gegenempfehlung zur Pipeline: **wenige SKUs, hoher ASP, lange Produktlebensdauer** — nicht viele, schnelle, billige.

### 2.5 Der Market-Agent sucht dort, wo Daten sind, nicht wo Geld ist

Ein methodischer Einwand, der unabhängig von allen Kostenzahlen gilt. Der skizzierte „Market-Agent" scannt Marktdaten, Kundenrezensionen und Konkurrenzprodukte — genau die Datenquelle, die zur Verfügung steht, und genau die falsche:

- **Rezensionen messen Ärger, nicht Budget.** Konsumenten beschweren sich am lautesten über Produkte, die sie billig gekauft haben. Rezensionsdichte korreliert mit Verkaufsvolumen im Massenmarkt, also mit *niedriger* Zahlungsbereitschaft pro Einheit — und mit der Anwesenheit finanzstarker Anbieter.
- **Echte B2B-Schmerzen sind nicht publiziert.** Ein Betriebsleiter, der 12 Stunden im Monat mit einer Nachweisdokumentation verliert, schreibt darüber keine Amazon-Rezension.
- **Konsequenz:** Ein rezensionsgetriebener Nischenscanner findet systematisch nur Nischen im gesättigten Konsumsegment. Er ist nicht schlecht implementiert — er ist auf die falsche Verteilung gerichtet.

**Die Fehlerklasse ist allgemeiner, als es zunächst aussieht**, und das ist die wichtigste Einsicht dieses Kapitels: Sie tritt auf jeder Ebene erneut auf, auf der man Datenverfügbarkeit mit Kaufbereitschaft verwechselt. Ein Scanner, der statt Rezensionen *Gesetzestexte und Normen* liest, belegt eine **Pflicht** — nicht die Zahlungsbereitschaft für ein bestimmtes optionales Werkzeug zu ihrer Erfüllung. Pflicht ≠ Budget. Der Prozess in §4.3 muss deshalb nicht Pflichten suchen, sondern **Rechnungsposten**: Wer stellt heute wem wofür eine Rechnung, über welchen Betrag? (Dieser Punkt stammt aus der Gegenprüfung; er korrigiert eine Schwäche der ersten Fassung, die den eigenen Befund eine Ebene höher wiederholt hatte.)

---

## 3. Falsifikation des Beispiels: Futterspender (A3)

### 3.1 Die angenommene Lücke existiert nicht

Die Skizze nennt als Lücke: selektive Fütterung für Mehrkatzenhaushalte mit individuellen Diäten, die „günstige Massenmarkt-Produkte oft nicht lösen". Der Markt ist seit Jahren genau darauf spezialisiert. Entscheidend ist dabei die Unterscheidung, welche Geräte den **implantierten Mikrochip** lesen und welche nur ein mitgeliefertes Halsband-Tag:

| Produkt | Preis | Liest implantierten Mikrochip? |
|---|---|---|
| SureFeed Microchip Pet Feeder (MPF001) | 180–220 $ | **Ja** — bis zu 32 IDs, 9-/10-/15-stellige Formate, Nass- und Trockenfutter |
| SureFeed Connect (+ Hub) | ~199 $ (+ ~50 $) | **Ja**, zusätzlich App, Portionen, Benachrichtigungen, Historie |
| PawsPik RFID | 249,99 $ | beworben als Mikrochip-fähig (nicht eigenständig verifiziert) |
| Closer Pets MiBowl | 129,99 $ | nicht verifiziert |
| Petlibro One RFID | 149 $ | **Nein** — „The RFID reader only works with the dedicated collar tag, not microchips or tags from other brands" ([Herstellerseite](https://petlibro.com/products/one-rfid-pet-feeder)) |

Übersichtsquellen: [thepetbench.com](https://www.thepetbench.com/articles/best-automatic-pet-feeders-for-multiple-cats/), [aitakon.com](https://www.aitakon.com/best-microchip-rfid-automatic-cat-feeder/), [petpalhq.com](https://petpalhq.com/guides/best-smart-pet-feeders-multi-pet-2026)

Die erste Fassung dieses Konzepts hatte Petlibro bei 149 $ als Beleg dafür angeführt, dass das Preisband **mit Mikrochip-Lesung und App** nach unten besetzt sei. Das ist nach Prüfung der Herstellerseite falsch und wurde korrigiert. **Die Schlussfolgerung bleibt:** SureFeed allein besetzt das Zielmerkmal seit Jahren und definiert das Preisband bei 180–250 $; das angebliche Alleinstellungsmerkmal ist das Standardmerkmal des Marktführers.

### 3.2 Die Stückkostenrechnung geht nicht auf

Zielpreis 179 € (unterhalb SureFeed Connect — bereits eine Schwächeposition):

| Position | Betrag |
|---|---|
| Endpreis brutto | 179,00 € |
| ./. USt 19 % (179 / 1,19) | **netto 150,42 €** |
| ./. Plattform/Zahlung/Versand (Amazon-Referral ~15 % oder eigener Shop + Ads) | −25 bis −35 € |
| ./. BOM bei 100 Stück (ESP32 ~4 €, **LF-RFID-Leser 134,2 kHz ISO 11784/11785 12–25 €** — nicht das billige 125-kHz-EM4100-Modul, Servo ~4 €, Wägezelle+HX711 ~5 €, Netzteil ~5 €, PCB+Bestückung ~5 €, Kleinteile ~6 €) | −41 bis −54 € |
| ./. Gehäusesatz 3D-Druck (FDM-Dienstleister) | −40 bis −80 € |
| ./. Verpackung, Anleitung | −5 € |
| **= Deckungsbeitrag je Stück** | **−23,58 € bis +39,42 €** |

Die Untergrenze ist **negativ**: Im ungünstigen Fall verkauft man mit Verlust je Stück. Im günstigsten Fall liegt der Break-even auf 15 k€ Fixkosten bei **381 Stück**.

*Methodischer Vorbehalt (aus der Gegenprüfung):* Die BOM ist mit 100-Stück-Preisen angesetzt, der Break-even liegt aber bei 381 Stück; bei dieser Menge fallen BOM und Druckkosten spürbar, der wahre Break-even liegt also niedriger. Das schwächt diese eine Rechnung — die Schlussfolgerung trägt trotzdem, weil sie an §3.1 und §3.3 hängt, nicht an dieser Tabelle. Zum Vergleich: Die Wettbewerber fertigen im Spritzguss; der Break-even Spritzguss gegen 3D-Druck liegt je nach Teilegröße bei rund 150–800 Stück, bei Gehäusen eher 500–1.500 ([Merit3D](https://merit3d.com/3d-printing-vs-injection-molding-the-volume-math-that-wins/), [hotean](https://hotean.com/blogs/hotean-blog/3d-printing-vs-injection-molding-cost) — beides Anbieterquellen, siehe §6). Man tritt mit der teureren Fertigungsmethode gegen amortisierte Werkzeuge an, in einem Preisband, das die Gegenseite definiert.

### 3.3 Ein Ausschlusskriterium, das das Screening der Skizze nicht erfasst

Ein Futternapf ist ein **Lebensmittelkontaktmaterial**. FDM-Drucke sind durch die Schichtstruktur porös, nicht spülmaschinenfest und praktisch nicht hygienisch zu halten. Man müsste den Napf als spritzgegossenes Zukaufteil beschaffen — womit der zentrale Vorteil „On-Demand-Fertigung ohne Werkzeugkosten" an der einzigen Stelle entfällt, an der er zählt.

Wichtiger als das Beispiel ist die Diagnose: Die Screening-Tabelle der Skizze prüft *physische Komplexität*, *bewegliche Präzisionsteile* und *Zertifizierungsrisiko (Medizin, Hochvolt)* — aber keine der drei Dimensionen, die dieses Produkt tatsächlich killen: belegte Konkurrenzdichte, Fertigungskosten-Nachteil gegenüber Etablierten, und Materialrecht. **Das Screening-Raster ist die Schwachstelle, nicht die Produktwahl.**

> **Zwischenergebnis (A2, A3):** Die These „Marge über Software bei reduzierter Mechanik" hält der Rechnung *im Konsumsegment* nicht stand — nicht weil Software keinen Wert schafft, sondern weil im B2C-Preisband von 100–250 € der Deckungsbeitrag je Einheit zu klein ist, um Fixkosten von ~15 k€ je SKU zu tragen, unabhängig davon, wie schnell die Software entsteht.

---

## 4. Proposed Solution

> **Meta-Frage: Ja.** Eine Einnahmequelle lässt sich strukturiert erarbeiten. Systematische Suche schlägt Warten auf Eingebung — aber nur, wenn die Suche über Rechnungsposten und Fixkosten je Versuch läuft und nicht über technische Machbarkeit oder publizierte Beschwerden.
>
> **Konkrete Frage, präzise beantwortet:** **Nein zur Pipeline** (n > 1 eigene SKUs) — sie multipliziert die teuerste Variable. **Möglicherweise ja zu genau einem Gerät** im B2B mit hohem ASP (§5.2). **Am wahrscheinlichsten richtig: Hardware als Geschäft nein, Hardware als Datenquelle in einem B2B-Softwaregeschäft vielleicht — und das ist ungeprüft** (§5.4). Diese Prüfung gehört in Gate 1 und kostet nichts.

### 4.1 Empfohlene Gestalt: Software-Wertschicht auf fremder, bereits zertifizierter Hardware

**Prinzip:** Man baut kein Gerät. Man wählt ein am Markt verfügbares, bereits CE-gekennzeichnetes Gerät (Industrie-Gateway, Sensorknoten, Datenlogger, Steuerung) und verkauft die *Intelligenz*: Konfiguration, Regelwerk, Auswertung, Nachweis, Integration, Alarmierung.

**Die rechtlich tragende Regel:** Wer ein Produkt unter eigenem Namen oder eigener Marke in Verkehr bringt oder es wesentlich verändert, wird selbst Hersteller mit allen Pflichten inklusive EU-Konformitätserklärung — *„Anyone who merely marks a product with their name and trademark is also considered as manufacturer"* ([Blue Guide 2022, EUR-Lex](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ%3AC%3A2022%3A247%3AFULL), [Sicom Testing](https://www.sicomtesting.com/en/blog/marking-and-roles-obligations/)).

**Wie weit das trägt — und wo nicht.** Die erste Fassung schrieb, die Fixkosten fielen damit „auf nahe null". Das ist überdehnt und wurde korrigiert. Richtig ist: Der Wechsel von der Hersteller- in die Händlerrolle senkt die Fixkosten je Versuch **um mindestens eine Größenordnung** — von ~15 k€ auf einen niedrigen vierstelligen Betrag. Vier Bedingungen müssen dafür gehalten werden, sonst kippt man ungewollt zurück:

1. **Der OEM muss für Deutschland bei der Stiftung EAR registriert sein.** Nach ElektroG gilt der Vertreiber selbst als Hersteller, wenn er schuldhaft Geräte nicht registrierter Hersteller anbietet (§ 3 Abs. 12 i. V. m. § 6 Abs. 2 ElektroG; wettbewerbsrechtlich abmahnfähig, OLG Düsseldorf I-20 W 18/07 — [IT-Recht-Kanzlei](https://www.it-recht-kanzlei.de/fehlende-registrierung-elektrog-regress.html)). Industrielogger kleinerer Anbieter sind häufig **nicht** registriert.
2. **Kein Direktbezug aus Nicht-EU.** Das macht zum **Einführer** — mit eigenen Pflichten (Name und Anschrift am Produkt, Aufbewahrung der Konformitätserklärung, Stichproben-, Melde- und Rückrufpflichten) und unter ElektroG mit Herstellerstatus samt Registrierung und Mengenmeldung.
3. **VerpackG/LUCID bleibt.** Wer Ware versendet, bringt Versandverpackung erstmals in Verkehr — unabhängig von der Geräterolle. Dieser Posten verschwindet nicht.
4. **Keine eigene Systembezeichnung auf der Hardware.** Ein Bündel aus OEM-Logger plus eigener Software unter einem eigenen Produktnamen nähert sich der Blue-Guide-Fallgruppe „assembles, packs, processes or labels ready-made products and places them on the market under their own name". Die OEM-Marke muss am Gerät sichtbar bleiben.

**CRA-Exposition der Softwareseite.** Der CRA regelt Produkte, nicht Dienste. Eine gehostete Nachweisplattform ist im Regelfall **kein** „Produkt mit digitalen Elementen" — es sei denn, sie ist eine *remote data processing solution*, ohne die das zugehörige Gerät seine Funktion nicht erfüllt. Gehört das Gerät einem Dritten und arbeitet es ohne die Plattform weiter, fällt die Plattform typischerweise aus dem Anwendungsbereich ([DLA Piper, 02/2026](https://www.dlapiper.com/en/insights/publications/2026/02/cyber-resilience-act-the-fine-line-between-saas-and-digital-products)). Das ist eine **Architekturentscheidung mit Rechtsfolge**: Die Plattform so bauen, dass der Logger ohne sie weiterläuft (lokale Pufferung, eigenständige Grenzwertlogik) — sonst kippt sie in den Anwendungsbereich. Die erste Fassung hatte hier mehr Pflichten angenommen als bestehen.

**Harte Grenze:** Sobald Messwerte zur *Abrechnung gegenüber Dritten* dienen, greift Mess- und Eichrecht bzw. MID ([kanzlei-herfurtner.de](https://kanzlei-herfurtner.de/messeg-mess-und-eichgesetz/)). Anwendungen, in denen gemessen wird, um Geld zu berechnen, sind auszuschließen.

**Warum das zur Kernkompetenz passt:** Der Wertanteil ist zu ~90 % Software, Domänenregeln und Integration. Genau dort liegt der Faktor-3–4-Hebel aus §2.1 — und er wirkt hier auf den *Engpass* statt daneben.

### 4.2 Revidiertes Screening-Raster

Die Kriterientabelle der Skizze wird ersetzt. Die erste Fassung dieses Konzepts hatte acht Kriterien; die Gegenprüfung hat vier davon als Dubletten identifiziert (Zahlungsbereitschaft war dreifach gefragt, der Rechtsstatus war Mechanismus statt Test). Vier K.-o.-Kriterien bleiben:

| # | K.-o.-Kriterium | Schwelle |
|---|---|---|
| **K1** | **Belegte Zahlungsbereitschaft** — es existiert ein heutiger **Rechnungsposten** oder ein bezifferbarer heutiger Arbeitsaufwand für dieses Problem. Nicht: eine Pflicht, ein Ärgernis, ein Regelwerk. | ≥ 3 Käufer nennen Betrag oder Stundenzahl |
| **K2** | **Käufer ist enumerierbar und kalt erreichbar** — Zielkundenliste aus öffentlichen Quellen erstellbar | Liste mit ≥ 100 Namen in 1 Tag |
| **K3** | **Fixkosten je Versuch < 5 k€ bis Go/No-Go, inklusive gesichertem Rechtsstatus** — Hardware fremd, unverändert, OEM-Marke sichtbar, OEM bei EAR registriert, Bezug über EU-Händler | hart |
| **K4** | **Ausschlussliste** — keine Abrechnungsmessung (Eichrecht), kein Lebensmittelkontakt (VO (EG) 1935/2004), keine Medizin (MDR), kein Hochvolt | hart |

Zwei **Präferenzen**, ausdrücklich keine K.-o.-Kriterien: wiederkehrender Umsatz (Zielbild „langfristig verdienen", schließt aber tragfähige Einmalverkauf-plus-Service-Modelle nicht aus) und kein Massenmarkt-Preisanker.

Bewusst *nicht* mehr im Raster: „niedrige physische Komplexität". Prominent in der Skizze, aber irrelevant, sobald man keine Hardware besitzt — und, wie §3.3 zeigt, ohnehin nie die entscheidende Dimension.

### 4.3 Der Prozess: drei echte Gates

Dies ist die konkrete Antwort auf „strukturiert statt Glück". Die erste Fassung nannte fünf Gates; zwei davon (Longlist, Produktisierung) hatten weder Cash-Risiko noch Abbruchkriterium und erzeugten Scheinstrenge. Es gibt **drei** echte Entscheidungspunkte:

**Vorstufe (1 Woche, 0 €, agentengestützt):** Longlist. Gesucht wird nicht „Pflicht", sondern **Rechnungsposten** — wer stellt heute wem wofür eine Rechnung? Quellen: Ausschreibungen und Vergabebekanntmachungen, Preislisten von Dienstleistern, Verbandspublikationen, Stellenanzeigen für manuelle Tätigkeiten, Handwerks- und Prüfdienstleister-Angebote. Regelwerke dienen dazu, den Kontext zu verstehen — nicht als Nachweis von Budget (§2.5). **Nicht** Amazon-Rezensionen. Ergebnis: 8 Kandidaten durch K1–K4.

| Gate | Dauer | Inhalt | Abbruch, wenn … | Cash |
|---|---|---|---|---|
| **G1 — Gesprächsvalidierung** | 2–3 Wo je Kandidat | 20 Gespräche mit echten Käufern. Keine Konzeptpräsentation, nur Ist-Zustand: Wie läuft das heute? Wie lange dauert es? Was kostet der Fehlerfall? Wer stellt dafür eine Rechnung? **Hier zusätzlich prüfen:** Ist der benötigte Messwert über eine vorhandene API/GLT/Exportdatei erreichbar? (§5.4 Bedingung 1 — kostet hier 0 € und entscheidet über Hardware ja/nein) | < 8 nennen den Schmerz ungefragt **oder** < 3 nennen einen heutigen Rechnungsposten bzw. Stundenaufwand | ~200 € |
| **G2 — Vorverkauf** | 2 Wo | Verkaufen vor Bauen: schriftliche Absichtserklärung oder Anzahlung für einen Pilot zum Zielpreis, von ≥ 2 Käufern | < 2 Zusagen | 0 |
| **G3 — Concierge-Pilot** | 6 Wo | Leistung erbringen, halb manuell. Fremde Hardware von der Stange, Software zur Hälfte gebaut, Rest Handarbeit. Ziel ist **nicht** Automatisierung, sondern Beweis, dass verlängert wird. | Pilot verlängert nicht **oder** der eigene Zeiteinsatz überschreitet 12 h/Woche über 3 Wochen in Folge (Zeitkollision, siehe §7.2) | 1.500–3.000 €, davon ~800–1.500 € Hardware für 2 Pilotobjekte |

**Danach:** produktisieren. Hier zahlt sich der Agenten-Stack voll aus. Eigene Hardware frühestens hier erwägen — und nur, wenn §5.2 erfüllt ist.

**Cash-Risiko je Nische bis Go/No-Go: unter 3,5 k€** (A4 erfüllt) gegenüber ~15 k€ im Blueprint. Realistischer Durchsatz: 3–4 Nischen pro Jahr bis G2, davon 1–2 bis G3.

**Konsequenz aus dem Kaltstart:** G1 ist bei fehlendem Netzwerk der teuerste Schritt — nicht in Geld, sondern in Überwindung und Kalenderzeit zu Bürozeiten. 20 Gespräche je Kandidat bei 3–4 Kandidaten bedeutet ~60–80 Kaltkontakte pro Jahr. Deshalb ist K2 ein K.-o.-Kriterium.

### 4.4 Konkretisierung: ein Kandidat, gegen das Raster geprüft

Dies ist eine **Vorführung des Rasters an einem Beispiel**, keine Nischenempfehlung. Preis- und MRR-Rechnungen sind bewusst weggelassen: Die erste Fassung hatte hier einen durchgerechneten Umsatz stehen, der sich als der am schwächsten belegte Teil des Dokuments erwies und beim Lesen zwangsläufig als Empfehlung wirkt.

**Kandidat: Trinkwasser-Temperaturnachweis für Betreiber** (Pflegeheime, Kliniken, Hotels, Wohnungsunternehmen, Schulen, kommunale Liegenschaften).

*Rechtlicher Kontext, geprüft:* Die TrinkwV 2023 verlangt turnusmäßige Legionellenuntersuchungen (jährlich bei öffentlicher Bereitstellung, alle drei Jahre bei gewerblicher), ein Risikomanagement mit Überprüfung in Abständen von höchstens sechs Jahren (§ 34) sowie Aufzeichnung und Aufbewahrung: *„Der Betreiber einer Wasserversorgungsanlage hat das Original der Niederschrift vom Zeitpunkt der Untersuchung an mindestens **zehn Jahre** aufzubewahren"* ([§ 44 Abs. 3 TrinkwV](https://www.gesetze-im-internet.de/trinkwv_2023/__44.html)). Die 60 °C/55 °C-Anforderungen stammen aus dem technischen Regelwerk (DVGW W 551), nicht unmittelbar aus der Verordnung.

*Zwei Korrekturen gegenüber der ersten Fassung, beide aus der Gegenprüfung:* Die Frist beträgt **zehn**, nicht fünf Jahre — ein Faktor 2 auf der zentralen Produkteigenschaft, und genau die Art Fehler, die im ersten Kaltakquise-Gespräch den Aufhänger verbrennt. Und: Die dort genannten „3 Liter / 250 ml" sind keine Temperaturmessmethodik — die 3 Liter definieren in der TrinkwV eine *Großanlage*, die 250 ml gehören zum Probenahmeprotokoll der Legionellenuntersuchung.

| Kriterium | Bewertung |
|---|---|
| **K1 Zahlungsbereitschaft** | **UNGEPRÜFT — und dies ist die eigentliche G1-Frage.** Die Verordnung verlangt Laboruntersuchung, Risikomanagement und Aufbewahrung; sie verlangt **kein kontinuierliches Temperatur-Monitoring**. Ein Betreiber erfüllt die Pflicht mit Thermometer und Protokoll. Belegte Rechnungsposten existieren fürs Labor und für den Sanitärpartner — nicht für Sensorik-SaaS. Ein Haken hier wäre exakt die Verwechslung, die K1 verhindern soll. |
| **K2 Enumerierbar** | ✔ Pflegeheime, Kliniken, Schulen, kommunale Liegenschaften sind öffentlich gelistet — der entscheidende Punkt beim Kaltstart |
| **K3 Fixkosten / Rechtsstatus** | ✔ Anlege-Temperaturfühler und handelsüblicher Datenlogger von der Stange; OEM-Registrierung bei EAR ist vor G3 zu prüfen (§4.1 Bedingung 1) |
| **K4 Ausschlussliste** | ✔ keine Abrechnungsmessung, kein Lebensmittelkontakt im Rechtssinne, keine Medizin, kein Hochvolt |

*Weitere Gegenrede:* SCHELL, Kemper, Techem und Sanitär-Fachplaner besetzen das Feld bereits mit Wassermanagement-Systemen; eine systematische Anbietererhebung wurde nicht durchgeführt. Der Vertriebszyklus in der Wohnungswirtschaft ist lang, und der Betreiber kauft erfahrungsgemäß lieber beim bestehenden Sanitärpartner. Zudem existiert in Kliniken und größeren Heimen häufig bereits eine Gebäudeleittechnik — womit §5.4 Bedingung 1 („erzeugt Daten, die es sonst nicht gibt") entfiele und die Hardware ersatzlos zu streichen wäre.

**Ein zweiter, nicht ausgearbeiteter Kandidat** zum Vergleich: Prüfmittelüberwachung/Kalibriernachweis in Fertigungs-KMU (ISO 9001, 7.1.5) — auditgetrieben, oft ganz ohne Hardware. **Ausgeschieden:** Retrofit-BDE/OEE für Altmaschinen — dichtes Anbieterfeld, lange Vertriebszyklen, hardwarelastig.

---

## 5. Trade-offs & Alternatives

### 5.1 Blueprint unverändert umsetzen

*Dafür:* Lernen von Hardware-Entwicklung end-to-end; Agenten-Skills entstehen entlang eines echten Produkts; ein Treffer im Konsumsegment skaliert besser als B2B-Nischen.
*Dagegen:* §2.1–§2.4. ~15 k€ je Versuch (13–32 k€), Lebenszykluspflicht ohne Ausstieg, kommoditisierender Software-Vorteil, Fertigungskosten-Nachteil gegen etablierte Werkzeuge.
*Urteil:* **Abgelehnt** als Geschäftsmodell. Vertretbar als bewusst bezahltes Lernprojekt mit gedeckeltem Budget — dann aber auch so zu nennen und nicht als Einnahmequelle zu planen.

### 5.2 Ein einzelnes B2B-Gerät mit hohem ASP (Gestalt B)

Falls Hardware-Eigentum unumgänglich ist, werden alle Parameter der Skizze invertiert: **ein** SKU statt Pipeline, ausschließlich B2B (keine insolvenzsichere Garantie, keine Verbraucherretouren, kein Amazon-Preiskampf), ASP 800–3.000 €, Stückzahl 50–300/Jahr, kabelgebunden oder ausschließlich vorzertifizierte Funkmodule ohne eigenes Antennendesign, wiederkehrender Umsatz über eine angebundene Softwarelizenz.

Deckungsbeitragsrechnung: ASP 1.500 €, DB 60 % = 900 €/Stück → 15 k€ Fixkosten nach 17 Stück gedeckt. Das ist tragfähig, im Gegensatz zu §3.2.

*Was diese Rechnung nicht zeigt (aus der Gegenprüfung):* Sie ist eine Deckungsbeitrags-, keine **Liquiditäts**rechnung. 60 % DB bei 50–300 Stück/Jahr sind gesetzt, nicht hergeleitet. Working Capital für die Erstserie, CRA-Lebenszykluspflicht und Gewährleistungsrückstellung fehlen. Der Cash-Bedarf **vor** dem 17. Stück ist das, was bindet — und er liegt in der Größenordnung von 15–25 k€.

*Bedingung, unter der B gegenüber A gewinnt:* wenn der Messwert oder die Aktorik physisch nicht anders zu bekommen ist **und** kein passendes Gerät von der Stange existiert. Diese Bedingung ist selten erfüllt und wird in **Gate 1** geprüft (nicht, wie in der ersten Fassung, erst in Gate 3 — die Information kostet in G1 nichts).

### 5.3 Agentic-Engineering-Dienstleistung an Hardware-Mittelständler (Gestalt C)

*Dafür:* sofortiger Cashflow, null Konformitätsexposition, baut Domänenwissen und Kundenzugang auf.
*Dagegen:* Bei **Kaltstart ohne Netzwerk** ist die Akquise der Engpass, und das Modell skaliert nicht ohne eigene Arbeitszeit.
*Urteil:* Als Brücke geeignet, nicht als Ziel. Die Antwort auf die Marktzugangsfrage schwächt diese Option gegenüber §4.1 deutlich ab.

### 5.4 Der stärkste Gegeneinwand gegen die eigene Empfehlung

**Wenn die Hardware nur durchgeleitet wird und keine Marge trägt — warum ist dann überhaupt Hardware im Spiel? Dann ist Gestalt A schlicht ein B2B-SaaS, und das ganze Hardware-Framing ist Selbsttäuschung.**

Berechtigt. Hardware trägt in Gestalt A genau drei Dinge bei; trifft keines davon zu, ist sie **ersatzlos zu streichen**:

1. **Sie erzeugt die Daten, die es sonst nicht gibt.** Ist die Größe über eine bestehende API, eine vorhandene Gebäudeleittechnik oder eine Exportdatei erreichbar, gibt es keinen Grund für ein Gerät.
2. **Sie macht den Nachweis prüfbar.** Bei Pflichtdokumentation ist ein automatisch erfasster Messwert gegenüber einer Behörde mehr wert als eine Eingabemaske.
3. **Sie erzeugt Wechselkosten.** Installierte Sensorik wird nicht wegen 10 € Preisunterschied ausgetauscht.

**Diese drei Bedingungen sind in Gate 1 zu prüfen, an echten Käufern, für 0 €** — die erste Fassung hat sie formuliert und dann bei ihrem eigenen Beispielkandidaten nicht angewandt. Trifft keine zu, lautet die richtige Empfehlung **reines B2B-SaaS ohne Hardware**, und dieses Konzept hat die Nutzerfrage dann mit „Hardware lohnt sich in keiner Variante" beantwortet. Das ist ein zulässiges Ergebnis und soll nicht kaschiert werden.

### 5.5 Nullvariante

Nichts tun und beim Ingenieursgehalt bleiben. Ernst zu nehmen: Bei 3–4 Nischen/Jahr ist der Erwartungswert nach 12–18 Monaten mit erheblicher Wahrscheinlichkeit **null zahlende Kunden**.

*Zur Trefferquote:* Die erste Fassung nannte „1 zu 4 bis 1 zu 6" ohne Quelle und ohne Definition. Das war die entscheidungsrelevanteste Zahl des Dokuments und die einzige völlig unbelegte. Sie wird hier **als Setzung gekennzeichnet, nicht als Befund**: Es gibt keine belastbare Basisrate für „strukturierte Nischensuche durch Einzelpersonen im deutschen B2B". Der ehrliche Satz lautet: Die Trefferquote ist unbekannt, und der einzige Weg, sie für den eigenen Fall zu schätzen, ist, die ersten 20 Gespräche zu führen und zu sehen, wie viele Kandidaten G1 überleben. Bis dahin ist jede Prognose Erfindung.

Der Unterschied zum Blueprint ist nicht die Erfolgsgarantie, sondern dass jeder Fehlschlag ~3 k€ statt ~15 k€ kostet und keine Dauerpflicht hinterlässt.

---

## 6. Grenzen und Unsicherheit

- **Die eigentliche Go/No-Go-Frage ist nicht die Hardware-Frage**, sondern die Bereitschaft zu ~60–80 Kaltkontakten im Jahr zu Bürozeiten (§7.3). Keine Zahl in diesem Dokument berührt sie.
- **Quellenqualität, offen gelegt.** Die Rechtsaussagen stützen sich auf Primärquellen (gesetze-im-internet.de, EU-Kommission, EUR-Lex/Blue Guide, stiftung-ear.de, BMG). Die **Kostenaussagen** dagegen stützen sich überwiegend auf Anbieter- und Affiliate-Blogs; die dominante Kostenzeile des gesamten Arguments (EMV + RED + Doku) hängt an einer **einzigen** Quelle. Zwei Laborangebote vor jeder Investitionsentscheidung.
- **Skalierungsgrenze von Gestalt A:** 2–3 k€ MRR sind mit 50–80 zahlenden Objekten/Kunden erreichbar. Ein **Vollersatz eines Ingenieursgehalts** (6–8 k€ netto/Monat) erfordert das Vier- bis Fünffache, also 250–400 Kunden — in einer engen Nische mit Kaltvertrieb nicht in 12–18 Monaten erreichbar und möglicherweise gar nicht ohne Marktwechsel oder eingestellten Vertrieb. Wird das Ziel später auf Vollersatz festgelegt, ist die Nischenbreite in der Vorstufe anders zu wählen.
- **Die Stückkostenrechnung in §3.2** basiert auf Katalogpreisen, nicht auf eingeholten Angeboten, und mischt 100-Stück-Preise mit einem Break-even bei 381 Stück.
- **CRA und SaaS:** Die Produkt-/Dienst-Abgrenzung steht im Verordnungstext, aber die Grenze ist schmal und architekturabhängig. Wird die Plattform so gebaut, dass das Gerät ohne sie seine Funktion nicht erfüllt, kippt sie in den Anwendungsbereich. Das ist eine Gestaltungsfrage, keine offene Rechtsfrage.
- **Der Beispielkandidat in §4.4 ist unvalidiert**, und K1 steht dort ausdrücklich auf UNGEPRÜFT. Die Wahrscheinlichkeit, dass er in G1 stirbt, ist hoch — das ist Teil des Designs.

---

## 7. Open Questions

1. **Zielgröße.** Arbeitsannahme 2–3 k€ MRR. Wird Vollersatz angestrebt, ändert sich die Nischenauswahl grundlegend (§6).
2. **Verfügbare Zeit pro Woche.** G3 verlangt 6 Wochen halbmanuellen Betrieb; G1 verlangt Gespräche zu Bürozeiten. Die Kollision mit einer Anstellung ist der wahrscheinlichste reale Blocker — deshalb ist sie jetzt als Abbruchkriterium in G3 codiert (12 h/Woche über 3 Wochen).
3. **Bereitschaft zum Kaltvertrieb.** Siehe §6, erster Punkt. **Das ist die eigentliche Go/No-Go-Frage.** Besteht sie nicht, scheitert nicht die Nischenwahl, sondern der Ansatz — dann wäre auf ein Modell mit inbound-getriebener Distribution auszuweichen.
4. **Branchenwahl bei Kaltstart.** Ohne bestehenden Zugang entscheidet die Vorstufe über die Domäne. Gibt es persönliches Interesse oder Vorwissen, das eine Domäne bevorzugt? Domänenaffinität schlägt Marktgröße, weil sie über die Durchhaltefähigkeit in G1 entscheidet.
5. **Soll der Agenten-Stack selbst ein Produkt werden?** Eigene Frage, bewusst nicht Teil dieses Konzepts.

---

## 8. Review

### Selbstkritik (Fassung 1, im Dokument umgesetzt)

§2.5 (Market-Agent zielt auf die falsche Datenverteilung), §3.3 (das Screening-Raster, nicht die Produktwahl, ist die Schwachstelle), §5.4 (stärkster Einwand gegen die eigene Empfehlung), §5.5 (Nullvariante), §6 (Grenzen).

### Unabhängige Gegenprüfung

| Feld | Wert |
|---|---|
| Konfiguration | `.sde_docs/config` nicht vorhanden → Default `ask`; einmalig abgefragt, Nutzerantwort „Ja" am 2026-09-18 |
| Modus | Separater Subagent mit frischem Kontext, eigener Webrecherche und Primärquellenzugriff |
| reviewer_model | `claude-opus-5` — **gleiches Modell wie der Autor (Same-Model-Fallback).** Da keine `reviewer_model`-Konfiguration existiert, wurde kein Fremdmodell gewählt. Korrelierte blinde Flecken sind damit **nicht** ausgeschlossen: Fehlerklassen, die beide Instanzen teilen (z. B. dieselbe Neigung, Anbieterblogs als Kostenbeleg zu akzeptieren, oder dieselbe Marktintuition), wären von dieser Prüfung nicht gefunden worden. |
| Verdict | **REVISE** |

### SCOPE-Befund des Reviewers und Disposition

| Befund | Disposition |
|---|---|
| **Tabellensummen §2.1 falsch** (52/40 statt 60/42 → 23 % statt 30 %) | **Bestätigt** durch eigene Nachrechnung. Korrigiert; alle Referenzen auf 30 % umgestellt. Der Fehler wirkte zugunsten der eigenen These. |
| **Cash-Obergrenze 22 k€ folgt nicht aus der Tabelle** (real 31.900 €) | **Bestätigt.** Spanne auf 13–32 k€ korrigiert, Mittelszenario ~15 k€ jetzt explizit benannt statt implizit verwendet. |
| **DB-Untergrenze §3.2 negativ** (−23,58 €, nicht 0) | **Bestätigt.** Korrigiert; Verlustfall wird jetzt ausgewiesen. BOM-/Break-even-Inkonsistenz als Vorbehalt ergänzt. |
| **Trefferquote 1:4–1:6 unbelegt** | **Bestätigt.** Als Setzung zurückgezogen und durch die ehrliche Aussage „unbekannt" ersetzt (§5.5). |
| **§4.4 kürzen: ein Kandidat, ohne Preis/MRR** | **Übernommen.** Preis- und MRR-Rechnung entfernt. Der Kandidat selbst bleibt, weil der Nutzer ausdrücklich um eine Konkretisierung gebeten hat — jetzt aber als Rastervorführung mit K1 auf UNGEPRÜFT. |
| **G0/G4 sind keine Gates** | **Übernommen.** Auf drei echte Gates reduziert, Vorstufe und Nachlauf entetikettiert. |
| **8 Kriterien auf 4 reduzieren** | **Übernommen.** K2/K7/K8 zu einem Kriterium verschmolzen, K4 als Mechanismus in K3 integriert, K6 zur Präferenz herabgestuft. |

### Refutationen und Disposition

| # | Befund | Disposition |
|---|---|---|
| R1 | **TrinkwV § 44 Abs. 3: zehn Jahre, nicht fünf**; „3 l / 250 ml" falsch zugeordnet | **Bestätigt** durch eigenen Abruf des Gesetzestextes. Korrigiert. Schwerster Einzelbefund, weil der Fehler genau im Ausführungsartefakt saß, mit dem Käufer angesprochen werden sollen. |
| R2 | **Pflicht ≠ Budget** — die Vorstufe reproduziert den §2.5-Fehler eine Ebene höher | **Bestätigt und übernommen.** §2.5 um die verallgemeinerte Fehlerklasse erweitert; Vorstufe sucht jetzt Rechnungsposten statt Pflichten; K1 entsprechend umformuliert; K1-Haken bei Kandidat A zurückgenommen. Der methodisch wichtigste Befund. |
| R3 | **K4 „nahe null" überdehnt** — EAR-Herstellerfiktion, Einführerstatus, LUCID, Bündel-Branding | **Bestätigt und übernommen.** „Nahe null" → „mindestens eine Größenordnung"; vier Bedingungen in §4.1 ergänzt; K3 um den Rechtsstatus erweitert. |
| R4 | **CRA falsch dargestellt** — (a) KMU-Erleichterung, (b) SaaS-Scope | **Bestätigt und übernommen.** (a) Art. 64(10)(a) schließt Bußgelder für Fristversäumnis aus, nicht nur Milderung — eigenständig gegengeprüft. (b) Gehostete Plattform fällt im Regelfall aus dem CRA-Anwendungsbereich; korrigiert und als Architekturentscheidung formuliert. §6-Vorbehalt zeigte auf die falsche Unsicherheit und wurde umgeschrieben. |
| R5 | **Petlibro-Fehlzitat** — liest keine implantierten Mikrochips | **Bestätigt** durch Abruf der Herstellerseite. §3.1-Tabelle um eine Spalte „liest Mikrochip?" erweitert, Fehlzitat offen korrigiert, MiBowl/PawsPik als nicht verifiziert gekennzeichnet. Einzelquellen-Abhängigkeit bei den Konformitätskosten in §2.2 und §6 offengelegt. |
| R6/R7 | **Ergebnissatz zu unscharf**; §5.4-Bedingungen nirgends geprüft, Prüfzeitpunkt falsch | **Übernommen.** §4 enthält jetzt die präzise Dreiteilung (Pipeline nein / ein Gerät vielleicht / Hardware als Datenquelle ungeprüft); die §5.4-Bedingungen sind explizit nach Gate 1 verlegt und in §4.4 auf den Beispielkandidaten angewandt. |
| R8 | **Kein Abbruchkriterium für die Zeitkollision** | **Übernommen.** In G3 codiert: 12 h/Woche über 3 Wochen in Folge. Hardware-Anteil am Pilotbudget aufgeschlüsselt. |

### Stärkstes Gegenargument des Reviewers gegen sein eigenes Verdict

Der Reviewer hat selbst eingewandt, dass alle seine Befunde Korrekturen *innerhalb* eines Dokuments seien, dessen Entscheidung bereits richtig ist — mehrere davon stärken die Empfehlung sogar. Die Konsequenz wäre: „Aufhören zu schreiben, die 20 Gespräche führen." **Diese Kritik wird hier ausdrücklich übernommen.** Sie ist der Grund, warum das Dokument in dieser Revision um rund ein Fünftel gekürzt wurde und warum §6 und §7.3 die Kaltvertriebsfrage vor jede Nischenfrage stellen. Ein weiteres Konzeptdokument ist nicht der nächste Schritt.

### Verbleibende Gate-Situation

Alle REVISE-Befunde sind aufgelöst; kein unaufgelöster BLOCK. Die Auflösung erfolgte durch **Autorkorrektur nach eigener Verifikation** der verifizierbaren Befunde (Arithmetik, TrinkwV § 44, CRA Art. 64, Petlibro) — **nicht** durch ein vom Reviewer erteiltes PASS. Eine zweite Reviewrunde wurde nicht durchgeführt.
