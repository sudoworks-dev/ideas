# 💡 Konzept: E-Rechnung als Geschäftsmodell — Tragfähigkeitsanalyse

## 📌 Status

`DRAFT` · **v3** (v1 belegte ein enges „Nein" und behauptete ein weites; v2 prüfte die weite Aussage gegen die grenzüberschreitende Netzwerk-Ebene, und sie hielt stand; v3 rechnet alles gegen das echte Umsatzziel neu — **ein Lebensunterhalt für drei, nicht €4k** — und prüft, ob das größere Ziel irgendeine Variante *wieder öffnet*, statt anzunehmen, dass es alle nur verhärtet)

| Feld | Wert |
|---|---|
| Erstellt | 2026-08-21 |
| Ausgangsidee | MVP-Spezifikation für eine Web-App zum Empfang von E-Rechnungen |
| Gestellte Frage | *„Lohnt es sich, Richtung E-Rechnung etwas zu bauen mit dem Ziel der Monetarisierung?"* |
| Rahmenbedingungen | Team 2–3 Personen · **keine Distribution**, Kaltstart (Nutzer, 2026-08-21) |
| Umsatzziel | **Ein echter Lebensunterhalt für drei Personen** — „kein Spielerei"; nicht von Anfang an nötig, aber die *Perspektive* muss vorhanden sein (Nutzer, 2026-08-21). Modelliert als **€21–29k MRR innerhalb von 36–48 Monaten**; die anfangs genannten €3.000–5.000 MRR werden als Zwischenschritt behandelt, nicht als Ziel |
| Recherche | 4 ausgelagerte Rechercheläufe, ~270 Werkzeugaufrufe: Regulatorik/Markt · Wettbewerb/Preise · vertikale Nischen · Peppol & grenzüberschreitend |
| Gegenprüfung | v1 → **„Überarbeiten"**, 7 Widerlegungspunkte. Alle unten aufgelöst, drei durch Streichung. Die Prüfung lief auf demselben Modell wie die Ausarbeitung und konnte nicht bestätigt werden, unabhängig davon zu sein — **das ist keine echte Cross-Modell-Prüfung**: Diese Gegenprüfung teilt einen realen Teil der blinden Flecken des Autors und ist nicht die Unabhängigkeit, die eine echte Cross-Modell-Prüfung geben würde |
| **Urteil** | **NEIN** — die Spec nicht bauen; nicht als Software-Geschäft in E-Rechnung einsteigen |

---

## 🎯 Problemstellung

**Gibt es einen tragfähigen Weg für ein 2–3-köpfiges Team ohne Distribution, im Bereich deutscher E-Rechnung ein Geschäft aufzubauen, das plausibel drei echte Gehälter tragen kann — so wie der Markt im August 2026 aussieht?**

Der Markt selbst ist nicht das Problem. Er ist riesig und gesetzlich erzwungen: **3.131.417 umsatzsteuerpflichtige Unternehmen** ([Destatis Umsatzsteuerstatistik 2024, Tabelle 73311-01](https://www.destatis.de/DE/Themen/Staat/Steuern/Umsatzsteuer/Publikationen/Downloads-Umsatzsteuern/statistischer-bericht-umsatzsteuer-2140810247005.xlsx?__blob=publicationFile)), alle seit dem 01.01.2025 verpflichtet, E-Rechnungen empfangen zu können. Die Frage ist, ob von dieser Nachfrage irgendetwas **erreichbar** und **monetarisierbar** ist. Das sind zwei getrennte Filter, und diese Kategorie scheitert an beiden.

---

## 🔢 Der Nenner

Das Ziel braucht einen Zeithorizont, eine Abwanderungsannahme (Churn) und ein Budget — sonst entscheidet es die Antwort still im Hintergrund. **Die erste Fassung hatte keines der drei** — und ließ Churn aus, was das eigene Argument sogar *verstärkt* hätte. Ein Zeichen dafür, dass die Tabelle gebaut wurde, um eine bereits feststehende Schlussfolgerung zu illustrieren, statt eine zu finden.

Diese Fassung korrigiert etwas Grundlegenderes. Das Ziel ist **ein Lebensunterhalt für drei Personen, mit der Perspektive vorhanden, auch wenn nicht als Startpunkt.** Drei Entwickler-Gehälter plus Arbeitgeberanteil und Overhead sind grob **€250–350k Jahresumsatz ≈ €21–29k MRR**. Der Arbeits-Nenner:

> **€25k MRR innerhalb von 36–48 Monaten, netto nach ~4 %/Monat Abwanderung, bei ≤€10.000 Gesamt-Akquisekosten — als glaubwürdiger Weg, nicht als Startposition.**

| Preis/Monat | Kunden für **€4k** (alter Zwischenschritt) | Kunden für **€25k** (das eigentliche Ziel) | Brutto-Neukunden/Monat bei 4 % Churn, um €25k zu halten |
|---|---|---|---|
| €9 (beobachteter Marktboden) | 445 | **2.778** | ~111/Monat, dauerhaft |
| €199 | 21 | **126** | ~5/Monat |
| €400 | 10 | **63** | ~2,5/Monat |
| €1.500 (ISV-Lizenz) | 3 | **17** | ~0,7/Monat |

Die €9-Zeile ist jetzt nicht mehr nur eine Tretmühle, sondern arithmetisch unerreichbar: 2.778 zahlende KMU ohne jeden Kanal, gegen vier Anbieter mit 35–60 % Rabatt. **Die untere Hälfte des Marktes ist allein durch das Ziel geschlossen**, bevor überhaupt ein Wettbewerbsargument greift.

## ⛔ Befund 1 — Die Spec existiert bereits zweimal, für €9–10 *(tragend)*

Nicht „ein überfüllter Markt" im Abstrakten. Das in der Ausgangs-Spec beschriebene Produkt **liefert bereits aus**.

| Anforderung der Spec | Bereits umgesetzt von |
|---|---|
| Eigene Eingangs-Adresse | **zeit.io** (`rechnungseingang@firma.zeit.io`), **aipi.email** |
| ZUGFeRD/XRechnung-Parsing + Validierung | beide (~200 Regeln bei aipi) |
| XML → lesbare Visualisierung | beide — plus **kostenlos** bei ELSTER, Quba, Handwerksafe, sevdesk, RechneX |
| Freigabe-Workflow, GoBD-Archivierung, DATEV-Export | beide |
| **EPC/GiroCode-Zahl-QR-Code** | **Handwerksafe — kostenlos, im Browser, ohne Registrierung** |

[zeit.io](https://zeit.io/de/blog/rechnungen-empfangen-mit-dem-e-rechnungs-postfach) €9/Monat · [aipi.email](https://aipi.email/e-rechnungseingang.html) €10/Monat, das die Zahlung über **SEPA-XML-Export an die Bank** löst — besser als ein QR-Code für alle, die mehr als eine Rechnung gleichzeitig bezahlen · [Handwerksafe SEPA-QR](https://www.handwerksafe.de/tools/sepa-qr/), kostenlos, derselbe Handwerker-Kunde.

**Der QR-Code ist keine Differenzierung.** Er ist kostenlos, er existiert bereits, und die EPC-Nutzlast ist ein dokumentierter 12-zeiliger String — ein Zwei-Wochen-Build für jeden Wettbewerber.

---

## ⛔ Befund 2 — In Deutschland hat das Compliance-Minimum keinen Preis

Präziser Geltungsbereich: Dieser Anker bezieht sich auf **Empfang**, also Transport und Postfach. Er bepreist nicht von selbst den Freigabe-Workflow oder die Suche der Spec — das leistet Befund 1. Die erste Fassung blähte einen Empfangs-Anker zu einer Preisobergrenze für den gesamten Workflow auf; die korrigierte Aussage ist enger und trotzdem entscheidend.

- **Das BMF sagt, ein Postfach genügt.** *„Für den Empfang einer elektronischen Rechnung genügt bereits ein E-Mail-Postfach."* ([BMF-FAQ](https://www.bundesfinanzministerium.de/Content/DE/FAQ/e-rechnung.html), Stand März 2026)
- **Der Staat liefert einen kostenlosen Viewer** — [ELSTER](https://www.elster.de/eportal/e-rechnung), seit Februar 2025, vom ZDH erwirkt, genau damit Handwerker nichts kaufen müssen.
- **DATEV hat den Empfang dauerhaft kostenlos gemacht** — keine Einrichtungsgebühr, keine Grundgebühr, jeder Übertragungsweg, und **die Registrierung setzt keine DATEV-Kundschaft voraus**. Versand aus Drittsystemen €0,50/Rechnung; DATEV E-Rechnungsschreibung **€5,00 pro Jahr** ([Preise](https://www.datev.de/web/de/nachrichten/datev/datev-e-rechnungsplattform-kostenfrei-bis-mitte-2026-neue-preise-fuer-danach/)). **1,01 Mio. Kunden; 51 Mio. E-Rechnungen allein im 1. Halbjahr 2026** gegenüber ~64 Mio. im gesamten Jahr 2025 ([DATEV H1 2026](https://www.datev.de/web/de/berufsgruppenuebergreifend/presse/presseinformationen/meldungen-2026/datev-steigert-umsatz-und-kundenbasis)).
- **Vier glaubwürdige Gratis-Stufen**: easybill Free (50 Belege/Monat), Papierkram Free (GoBD-zertifiziert), Accountable Free (unbegrenzt), Qonto Starter.
- **Der bezahlte Boden ist eine Vollsuite, kein Einzelwerkzeug**: [Lexware Office S €7,90](https://www.lexware.de/preise/) und [WISO MeinBüro €7,09](https://www.meinbuero.de/preise/) enthalten beide Empfang *plus* automatisches Mail-Import-Postfach.
- **Kundengewinnung ist der bindende Engpass, und die Preisseiten beweisen es.** Vier unabhängige Anbieter rabattieren gleichzeitig: sevdesk 60 % (€25,90 → €9,95), Lexware 50 % für drei Monate, WISO 35–50 %, Accountable und FastBill ~20 % im Jahresabo. Anhaltender starker Rabatt bei vier unabhängigen Wettbewerbern ist das Erkennungszeichen eines Marktes, in dem **Listenpreise nicht durchsetzbar sind**. Ein Team ohne Kanal und ohne Werbebudget startet darunter.

---

## ⛔ Befund 3 — Schmerz und Zahlungsbereitschaft laufen in entgegengesetzte Richtungen

Zeitplan bestätigt und **nicht verschoben**: § 27 Abs. 38 UStG ([Gesetzestext](https://www.gesetze-im-internet.de/ustg_1980/__27.html)) — Empfangspflicht für alle seit 01.01.2025; Papier-/PDF-Versand erlaubt bis 31.12.2026, verlängert bis 31.12.2027 nur bei Vorjahresumsatz ≤ €800.000; **universelle Versandpflicht ab 01.01.2028**. Der [JStG-2026-Entwurf](https://wts.com/de-de/publishing-article/20260817-regierungsentwurf-jahressteuergesetz~publishing-article) (Kabinett, 12.08.2026) lässt §§ 14/14a und § 27 Abs. 38 unangetastet. Rund **600.000** Unternehmen sind in der 2027er-Welle, **~2,5 Mio.** in der 2028er-Welle (unter €1 Mio. = 2.648.947, also 84,6 % aller Umsatzsteuerpflichtigen).

Die 2027er-Welle zwingt mittelgroße Firmen zum *Versand*, was mechanisch ~2,5 Mio. Kleinbetriebe mit eingehenden E-Rechnungen flutet. **ZDH, n=1.926 Handwerksbetriebe, erhoben 12.01.–27.02.2026** ([ZDH](https://www.zdh.de/ueber-uns/fachbereich-steuern-und-finanzen/umsatzsteuer/umfrageergebnisse-e-rechnung/), [Auswertung](https://www.handwerksblatt.de/themen-specials/die-e-rechnung-wird-pflicht-tipps-fuer-handwerksbetriebe/zdh-umfrage-im-handwerk-noch-mehr-aufwand-mit-der-e-rechnung)) misst den Schmerz bereits: ~50 % der Eingangsrechnungen kommen bereits als E-Rechnung · **47,4 % sagen, die Verarbeitung sei *mehr* Aufwand als bei PDFs** · ein Drittel kann die Daten nicht lesen · **33 % haben keine GoBD-konforme Archivierung** · 56 % liegen unter €800k.

**Aber der Schmerz sitzt genau in der Kohorte, die nicht zahlen wird.** Ihre Versandpflicht beginnt erst 2028; **Kleinunternehmer sind dauerhaft von der Ausstellungspflicht befreit** (§ 34a UStDV); Rechnungen ≤ €250 sind ausgenommen (§ 33 UStDV); und der Empfang ist für €0 durch ein vom BMF gesegnetes Postfach erfüllt. Wer den Schmerz hat, hat eine kostenlose, staatlich abgesegnete Alternative; wer das Budget hat, ist bereits bei DATEV oder in einem ERP. **Keine Produktentscheidung behebt diese Umkehrung.**

---

## ⛔ Befund 4 — Fünf Kandidaten-Varianten, gegen Primärquellen geprüft, alle geschlossen

### A · Hausverwaltung / WEG — **GESCHLOSSEN**
Die Prämisse war, dass strukturierte Positionsdaten endlich die Aufteilung des Lohnanteils nach § 35a EStG automatisieren würden. **Korrektur gegenüber der ersten Fassung, die dies übertrieben hatte:** EN 16931 stellt *durchaus* einen strukturierten Träger bereit — **BG-32 / BT-160 (Positions-Attributname) + BT-161 (Wert), Kardinalität 0..n**, Regel [BR-54](https://docs.peppol.eu/poacc/billing/3.0/rules/ubl-tc434/BR-54/), gemappt auf `cac:AdditionalItemProperty` (UBL) und `ram:ApplicableProductCharacteristic` (CII). Die Aussage „der Standard kann diese Daten nicht liefern" ist damit **so formuliert falsch**.

Sie ist dennoch **in der Praxis wahr**: Keine deutsche Stelle — FeRD, KoSIT, ZDH oder ein Handwerksverband — hat dafür eine Konvention definiert. Keine Codeliste, kein Attributname, keine Mapping-Vorgabe. Die zwei geprüften Implementierungen liefern **lesbaren Text, keine strukturierte XML**: [xrechnungs.de](https://www.xrechnungs.de/de/lohnkostenausweis-rechnung) beschreibt nur ein UI-Feld, und [Sage HWP](https://onlinehilfe.sage.de/onlinehilfe/hwp/53/hwhelp/doku_paragraph_35a.htm) liefert Druckvorlagen-Platzhalter ohne dokumentierten XML-Export. Das ist eine **Adoptionslücke, keine Standardlücke** — und Adoptionslücken schließen sich in einem Release-Zyklus.

Unabhängig davon ist die Nische besetzt: **Aareon/Haufe hat einen XRechnung/ZUGFeRD-Viewer über alle PowerHaus-Archive im Q1 2025 ausgeliefert** ([PowerHaus](https://powerhaus.aareon.de/e-rechnung-powerhaus)); [etg24](https://etg24.de/funktionen/e-rechnung-hausverwaltung/) macht KI-gestützten E-Rechnungseingang *plus* ein Eigentümer-Belegprüfungsportal für €90–400/Monat; VDIVs eigene Handlungsempfehlung stellt Belegeinsicht-gegen-XML nirgends als Problem dar.

### B · Arztpraxen / Heilberufe — **GESCHLOSSEN** (die erste Fassung schloss dies über den falschen Hebel)
Die erste Fassung behauptete, es gebe „keine finanzielle Sanktion für Untätigkeit". **Das war falsch.** § 26a Abs. 2 Nr. 2 UStG sanktioniert die Verletzung der achtjährigen Aufbewahrungspflicht nach § 14b — die auch *empfangene* Rechnungen erfasst — mit einem Bußgeld bis **€5.000** (§ 26a Abs. 3, [Gesetzestext](https://www.gesetze-im-internet.de/ustg_1980/__26a.html)).

Die Nische schließt trotzdem, auf schwächerer, aber ausreichender Grundlage: Das Bußgeld ist ein **Höchstbetrag**, setzt *vorsätzliches oder leichtfertiges* Handeln voraus, und **es fand sich kein Beleg für eine tatsächliche Durchsetzung gegen Kleinbetriebe wegen Archivierungsmängeln** — Praktiker behandeln es als Nebenaspekt von Betriebsprüfungen, nicht als eigenständiges Instrument. Als Kaufauslöser ist es ein Papiertiger. Zugleich befreit § 14 UStG Umsätze nach § 4 Nr. 8–29 ausdrücklich von der Ausstellungspflicht, das BMF sagt, ein Postfach genüge, und **CGM liefert es bereits** (PRAXISARCHIV für Z1/Z1.PRO, ein eRECHNUNG-Modul in MEDISTAR). *Korrektur der Übergeneralisierung der ersten Fassung:* Apotheken (~17.000, voll steuerpflichtig, vollem Vorsteuerabzug, hohem Eingangsvolumen) und Praxen mit gemischten Umsätzen liegen innerhalb dieses Segments und außerhalb des Befreiungsarguments — sie werden nicht durch die obige Argumentation geschlossen, sondern nur durch die Befunde 1–3.

### C · B2D / E-Rechnungs-API für andere Softwarehersteller — **GESCHLOSSEN**
An beiden Enden geschlossen. **Oben: DATEV gibt die API kostenlos ab** — Senden *und* Empfangen, ZUGFeRD 2.x / XRechnung / Peppol BIS 3.x, automatische Visualisierung, **kostenfrei für Lösungsanbieter** ([DATEV-FAQ für Softwarehersteller](https://www.datev.de/web/de/berufsgruppenuebergreifend/ueber-datev/portfolio/oekosystem/partnering/datev-marktplatz/faq-zur-datev-e-rechnungsplattform-fuer-softwarehersteller)). *(Das sind zwei getrennte Dinge, die in der ersten Fassung vermischt wurden: Die Nutzung der Plattform-API steht jedem offen; die **Listung** im DATEV-Marktplatz erfordert 25 aktive Kunden und 3 Referenzen. Die freie API schließt diese Nische; die Listungshürde schließt den Steuerberater-Kanal. Zwei Hürden, zwei Wege.)*

**Unten: kostenlose, ausgereifte, aktuelle Open-Source-Software.** Über die GitHub-API am 21.08.2026 geprüft — [Mustangproject](https://github.com/ZUGFeRD/mustangproject) (Apache-2.0) veröffentlichte **core-2.25.0 am 05.08.2026** mit ZUGFeRD 2.5.2 / Factur-X 1.09.2, deckt Eingangs-Parsing, Validierung, Visualisierung, CLI und REST ab. Der [KoSIT-Validator](https://github.com/itplr-kosit/validator) veröffentlichte v1.6.3 am **20.08.2026**. **Die Mitte ist bereits besetzt bei €10–20/Monat**: [B2Brouter](https://www.b2brouter.net/global/api-e-invoicing/) ab €15, [Factora](https://factora.software/api/) ab €19,90, [rechnungsapi.de](https://www.rechnungsapi.de/pricing) €9,99 — alle White-Label.

### D · Peppol Access Point / Netzwerk-Infrastruktur — **GESCHLOSSEN, und das ist der interessante Fall**
Dies war der stärkste verbliebene Kandidat: Ein **zertifizierungsgebundener Burggraben** ist genau das, was „tragfähig" bedeutet. Er scheitert am Design des Netzwerks selbst.

Einen Access Point zu betreiben ist tatsächlich aufwendig — OpenPeppol-Gebühren **€1.050 Anmeldung + €1.850/Jahr + €1.500 Zertifizierung** für einen 1–50-Personen-AP ([Gebührenordnung](https://peppol.org/join/fees/)); **ISO/IEC 27001 verpflichtend für alle Service Provider ab 01.07.2027** ([AgID](https://peppol.agid.gov.it/en/news/ISO-IEC-27001-Certification-Mandatory-for-Peppol-Service-Providers-from-1-July-2027/)); **99,5 % Verfügbarkeit rund um die Uhr**, nicht verfügbar bereits ab 60 Sekunden ununterbrochenem Ausfall; Haftung gedeckelt auf €500k pro Vorfall / €1 Mio. jährlich. Kein dokumentierter Fall eines 1–5-Personen-Teams, das einen zertifizierten AP betreibt, wurde gefunden.

**Aber man muss es nie selbst tun.** Die Peppol-Service-Provider-Vereinbarung definiert jede Partei, die *über* den AP eines anderen Anbieters abwickelt, als **„End User"** — keine Zertifizierung, keine Mitgliedschaft, kein ISO 27001, kein SLA — und **§ 15.1 erlaubt Unterauftragsvergabe ausdrücklich** ([SP-Vereinbarung](https://peppol.agid.gov.it/attachments/PeppolServiceProviderAgreement_V_1_1_giu2023.pdf)). Storecove, B2Brouter und Tickstar verkaufen White-Label-AP-als-Dienstleistung kommerziell.

> **Der Burggraben ist real, teuer — und auf der falschen Seite.** Er schützt ~800 etablierte Service Provider — darunter Telekom MMS, SAP, SEEBURGER und Siemens — *vor dir*, schützt dich aber vor niemandem, weil jeder Wettbewerber über dieselben Reseller-APIs Zugang zum selben Netzwerk hat.

Was bleibt, ist Reseller-Marge auf ein Gut, dessen beobachtbarer Preis bei **€0,07/Dokument** ([COMPLAVIS](https://www.complavis.de/peppol-dienst/)), **€0,18/Rechnung** ([e-invoice.be](https://e-invoice.be/peppol-ap)) liegt — und **kostenlos in der KMU-Stufe bei Qvalia, selbst ein zertifizierter AP** ([Qvalia](https://qvalia.com/pricing/)) — die €0-Kraft kommt hier über Schweden, getrieben von APs, die Transport als Upsell-Lockangebot behandeln, nicht von einer Steuerbehörde. Bei €0,05–0,10 einbehalten pro Dokument braucht **€4.000 MRR 40.000–80.000 Dokumente/Monat**, also hunderte aktive Geschäftskunden, gewonnen ohne Distribution.

### E · Mehrländer-Compliance-Schicht — **GESCHLOSSEN**
Die €0-Kraft ist tatsächlich deutsch-politisch. Der Grenzübertritt entkommt ihr nicht — **Polens KSeF ist staatlich betrieben und kostenlos, inklusive kostenloser öffentlicher API und kostenloser Steuerpflichtigen-App; Italiens SdI ist kostenlos, inklusive kostenloser 15-jähriger Archivierung; Belgien veröffentlicht eine offizielle Liste kostenloser/günstiger Softwarelösungen.** Drei von vier Märkten reproduzieren das deutsche Problem eins zu eins.

Frankreich ist der eine Markt, der den kostenlosen Weg entfernt hat — und **lizenzierte Knappheit ist dort tot**: Der DGFiP-Datensatz auf dem offiziellen Open-Data-Portal der französischen Regierung listet **137 zugelassene Plateformes Agréées zum 25.06.2026**, 146–166 bis August, Register unbegrenzt und wachsend, darunter bereits **Pennylane, Qonto, Sage, Cegid, Tiime, Indy und Sellsy** — also genau die Buchhaltungsanbieter, die die Distribution besitzen, die diesem Team fehlt. Man wäre Marktteilnehmer Nummer ~150.

Nachfrageseitig: **kein deutscher Käufernachweis überhaupt** — keine Mittelstands-Fallstudie, kein Branchensoftware-Anbieter, der eine unabhängige Mehrländer-Schicht beschafft. Das nächstliegende Beispiel kaufte beim eigenen ERP-Anbieter. Angebotsseitig besetzt von EDICOM, Pagero, ecosio und SEEBURGER, die genau dieses Produkt heute schon verkaufen.

---

## 🔁 Öffnet das größere Ziel irgendetwas wieder? — geprüft, nein

Ein größeres Umsatzziel ist nicht durchweg eine schlechtere Nachricht — es macht **Varianten mit hohem Kundenwert relativ attraktiver**, sodass eine bei €4k geschlossene Variante bei €25k theoretisch wieder aufgehen könnte. Jede geschlossene Variante wurde gegen das neue Ziel erneut geprüft, statt anzunehmen, dass es sich nur verhärtet.

| Variante | Richtung bei €25k | Warum |
|---|---|---|
| Kopieren und unterbieten | **Schlechter** | 2.778 Kunden bei €9. Arithmetisch unerreichbar. |
| Vertikale SaaS | **Schlechter** | 126 Kunden bei €199 *innerhalb einer Vertikale*, gegen Aareon/etg24/CGM als etablierte Anbieter. |
| B2D-API | **Schlechter** | 50–100 Softwarehersteller bei €250–500 gegen eine **kostenlose** DATEV-API. |
| Peppol AP / Reseller | **Deutlich schlechter** | €4k brauchte 40–80k Dokumente/Monat; €25k braucht **250.000–500.000/Monat** bei €0,05–0,10 Marge. |
| Mehrländer-Schicht | **Schlechter** | Skalierung Richtung €25k führt in die Enterprise-Klasse — also direkt gegen EDICOM, Pagero, ecosio, SEEBURGER. |
| Umsetzungs-Consulting | **Neutral bis schlechter** | Siehe unten. |

**Nichts öffnet sich wieder.** Die eine Variante, die eine ernsthafte Prüfung verdient hat, ist die Preislücke — die bekommt sie jetzt.

### Der stärkste verbliebene Pro-Fall — und warum er trotzdem scheitert

Die Recherche fand **nichts Glaubwürdiges zwischen GetMyInvoices (€99–179) und Candis (€389)**. Eine so breite Lücke in einem großen Markt verdient es, ernst genommen zu werden: ~126 Kunden bei €199, oder ~63 bei €400, würden das Ziel erreichen. Der Käufer ist real und identifizierbar — 100–500 Rechnungen/Monat, grob €2–20 Mio. Umsatz, **in der 2027er-Welle und damit unter einer Frist, die vier Monate entfernt liegt**, zu klein für Candis/Finway, zu groß für Lexware. Die von ZDH gemessenen 8–15 Minuten manueller Bearbeitung pro Rechnung sind bei diesem Volumen echtes Geld.

Drei Gründe, warum sie trotzdem geschlossen bleibt:

1. **Die Lücke ist aus strukturellen Gründen leer, nicht aus Versehen.** €200–380/Monat ist die klassische SaaS-Todeszone: zu teuer für Self-Service-Konversion, zu billig, um einen Vertriebler zu finanzieren. Dort einzusteigen bedeutet, Enterprise-Vertriebskosten auf Mittelstandsumsatz zu zahlen — und der fehlende Input ist genau ein Kanal.
2. **Gekauft wird AP-Automatisierung, nicht E-Rechnung.** Freigabe-Routing, Kontierung, ERP-Buchung — E-Rechnung ist der Keil, nicht das Produkt. Das ist eine gut finanzierte Wettbewerbskategorie, und sie landet direkt bei Regel 2 unten: Der Käufer besitzt bereits ein ERP, dessen Anbieter E-Rechnung liefert, weil er muss.
3. **Die Rechnung bleibt eng, selbst im Erfolgsfall.** 126 Kunden bei einem 6–12-monatigen Mittelstands-Vertriebszyklus, mit drei Personen, die gleichzeitig das Produkt bauen und supporten, bedeuten grob 3–4 Abschlüsse/Monat, durchgehend über drei Jahre, aus dem Stand ohne Referenzen.

Das ist der beste verfügbare Fall, und er reicht nicht. Er wird festgehalten, weil es das Argument ist, das eine Leserin erwartungsgemäß beantwortet sehen möchte, nicht übersprungen.

## 🧩 Die Regel dahinter

Die erste Fassung schlug vor: *„E-Rechnung ist ein Compliance-Häkchen, niemand zahlt für ein Häkchen."* **Das übergeneralisierte aus vier deutschen Datenpunkten und wird durch den eigenen besten Befund der ersten Fassung widerlegt** — Handwerksbetriebe zahlen ~€3.000 Einrichtung für ein Häkchen, zu dem sie gesetzlich gezwungen wurden. Zwei engere Regeln bleiben bestehen, und die zweite ist der eigentliche Befund:

1. **Wo Staat und dominanter Buchhaltungsanbieter gemeinsam das Compliance-Minimum kostenlos liefern, hat das Compliance-Minimum keinen Preis.** Wahr in Deutschland, Polen und Italien; kein Gesetz der Kategorie — Frankreich lizenziert private Betreiber, statt sie zu ersetzen.
2. **E-Rechnungs-Transport ist eine Netzwerk-Infrastruktur, und Infrastruktur gewinnt, wer bereits die Kundenbeziehung besitzt.** Das gilt über jede Jurisdiktion hinweg, und deshalb hält das weite „Nein" stand. Peppols offenes Teilnahme-Design garantiert, dass Wettbewerber das Netzwerk genauso günstig erreichen wie man selbst; das einzig dauerhafte Gut ist ein bestehender Kundenstamm, den man auf die eigenen Schienen umziehen kann. **Das ist genau der fehlende Input.**

Eine Folgerung, die für jede nächste Idee mitgenommen werden sollte: **Nach Problemen suchen, bei denen die Ausgaben des Käufers steigen, wenn man sie besser löst** — nicht nach Problemen, bei denen ein Häkchen genügt, und nicht nach Schichten, die innerhalb von etwas ausgeliefert werden, das der Kunde bereits gekauft hat.

---

## ⚖️ Verworfene Ansätze

| Ansatz | Warum verworfen |
|---|---|
| zeit.io/aipi kopieren und unterbieten | Boden bei €9; Empfang dauerhaft €0; 445 Kunden, kein Kanal. Ein €0-Angebot unterbieten ist Arithmetik, keine Strategie. |
| Über UX konkurrieren | Compliance-Tools werden über Vertrauen und Bestandsnähe gekauft. Die Gratis-Stufen sind glaubwürdig, nicht verkrüppelt. |
| Vertikale SaaS (jede Vertikale) | Zwei geprüft und geschlossen; das Scheitern wiederholt sich — jeder vertikale Branchensoftware-Anbieter liefert E-Rechnung als Pflicht-Häkchen und verschenkt es, weil er es nicht verkaufen kann. |
| B2D-Infrastruktur-API | DATEV oben kostenlos, Apache-2.0-Mustangproject darunter, €10–20/Monat in der Mitte. |
| Peppol-AP / Reseller | Burggraben schützt die ~800 Etablierten, nicht dich; Transport bei €0,07–0,18 und kostenlos in der KMU-Stufe. |
| Mehrländer-Compliance-Schicht | PL/IT/BE staatlich kostenlos oder kuratiert-kostenlos; Frankreich hat 137+ lizenzierte Betreiber; kein Käufernachweis; EDICOM/Pagero/ecosio/SEEBURGER etabliert. |
| An die 2027er-Versandwelle verkaufen (~600k Firmen) | Sie haben bereits ERP/DATEV. DATEV berechnet €0,50/Rechnung für Dritte, €5/Jahr für die eigene Schreibung. |
| Datenverwertung / Ausgabenanalyse | Henne-Ei-Problem — braucht Volumen, Volumen braucht das kostenlose Tool, das niemand nutzt, weil DATEV kostenlos ist. DATEV hält 51 Mio. Rechnungen pro Halbjahr. DSGVO- und Kartellrisiko beim Aggregieren fremder Rechnungsdaten. |
| Steuerberater-White-Label | Gehört DATEV. Marktplatz-Listung braucht **erst 25 aktive Kunden + 3 Referenzen** — eine Hürde, kein Zugangsweg. |
| §35a-Lohnanteil-Extraktion | **In v2 gestrichen.** Die erste Fassung empfahl dies als einzig überlebende Idee. Sie wird bereits ausgeliefert: [selbstverwalten.com](https://selbstverwalten.com/blog/hausgeldabrechnung-steuern-absetzen) schreibt wörtlich, es *„erkennt beim Rechnungsupload per KI den Arbeitskostenanteil und die § 35a-Kategorie jeder Rechnung"*, mit dem Ausweis je Eigentümer, der *„in der Jahresabrechnung … automatisch erstellt"* wird. Die erste Fassung hatte gegen jede zu verwerfende Idee hart nach Wettbewerb gesucht — und gegen die eine zu behaltende Idee gar nicht. |
| Umsetzungs-Consulting | Erreicht die Schwelle bei verifizierten Zahlen (siehe unten), ist aber eine Agentur, kein Produkt. |

---

## 💰 Der einzige Ort, an dem nachweislich Geld fließt

ZDH misst **~€3.000 einmalige Einrichtung und ~€800/Jahr laufend** pro Handwerksbetrieb. Das wird für **Umsetzung ausgegeben, nicht für SaaS**. Bei €3.000/Projekt erreichen ~16 Projekte/Jahr den alten €4.000/Monat-Zwischenschritt — aber **das eigentliche Ziel braucht ~83 Projekte/Jahr**, also müsste jede der drei Personen etwa alle zwei Wochen eines abschließen und liefern, durchgehend, ohne Produkt-Hebel und ohne Kanal. Das ist eine Tretmühle am Rand dessen, was drei Personen durchhalten können, und es ist ein Job, kein Vermögenswert: Der Umsatz stoppt in dem Monat, in dem die Arbeit stoppt.

**Die erste Fassung tat dies als „verfällt nach 2028" ab. Das war falsch und widersprach sich selbst** — die eigene Recherche der ersten Fassung stellte den ViDA-Kalender fest: **verpflichtende innergemeinschaftliche digitale Meldepflichten ab 01.07.2030 und vollständige Harmonisierung nationaler Meldesysteme bis 01.01.2035** ([EU-Kommission](https://taxation-customs.ec.europa.eu/taxation/vat/vat-digital-age-vida_en)). Deutsche Unternehmen erreichen 2028 ein inländisches Plateau und 2030 eine zweite, größere EU-weite Welle. Die ehrlichen Einwände sind enger: Es ist eine Agentur, der Umsatz stoppt, wenn das Team stoppt, und es braucht lokale Präsenz — nicht, dass die Nachfrage verfällt.

Es wird festgehalten, nicht empfohlen. Aber es ist das einzige verifizierte Geld in dieser Recherche, und es hat eine Eigenschaft, die sonst nichts hier hat: **Es erzeugt den fehlenden Input selbst.** Achtzig Umsetzungsprojekte sind achtzig Kundenbeziehungen plus Wissen aus erster Hand darüber, wofür diese Käufer bereits bezahlen, um es manuell erledigen zu lassen — also Distribution und Produktentdeckung, finanziert statt gekauft.

Das ist die ehrliche Form eines „erst Dienstleistung, dann Produkt"-Weges, und sein Scheiterrisiko ist ebenso ehrlich und sehr verbreitet: Consulting-Umsatz ist ein lokales Optimum, das die gesamte Kapazität aufbraucht, die meisten Agenturen entkommen ihm nie, und das Produkt, das man irgendwann bauen würde, bedient Käufer, deren Preiserwartung von €0-Tools geprägt wurde. Es ist der einzige Weg in diesem Dokument mit einer Obergrenze über €250.000, und es ist eine Wette darauf, einer Falle zu entkommen, der die meisten Teams nicht entkommen.

---

## ✅ Empfehlung

**Die Ausgangs-Spec nicht bauen.** Sie existiert bereits zweimal für €9–10, ihre genannte Differenzierung ist kostenlos, und der Empfang ist per Ansage von BMF und DATEV bei €0. *(Hohe Zuversicht — hat jeden Angriff der Gegenprüfung überstanden.)*

**Nicht als Software-Geschäft in E-Rechnung einsteigen.** Nicht in erster Linie, weil das BMF es kostenlos gemacht hat — dieser Grund ist an die deutsche Jurisdiktion gebunden und wurde in der ersten Fassung zu stark strapaziert — sondern weil **Transport und Compliance Netzwerk-Infrastruktur sind, die gewinnt, wer bereits die Kundenbeziehung besitzt**, und das ist genau der fehlende Input. Über sechs Varianten und fünf Jurisdiktionen bestätigt.

**Das Lebensunterhalts-Ziel macht dies zu einem härteren Nein, nicht zu einem weicheren.** Jede Variante wurde erneut gegen €25k MRR geprüft, keine öffnete sich wieder; die untere Hälfte des Marktes ist jetzt allein durch Arithmetik geschlossen, bevor überhaupt ein Wettbewerbsargument greift. Die Preislücke bei €200–380 ist der stärkste verbliebene Pro-Fall, und sie scheitert an der Struktur, nicht am Aufwand.

**Wenn das Ziel ein echtes Geschäft für drei Personen ist, ist das bindende Problem nicht das Produkt — es ist, dass keine Distribution vorhanden ist und diese Kategorie einem keine verkauft.** Jeder geprüfte Weg braucht entweder einen Kanal, der fehlt, oder übergibt den Kunden an jemanden, der bereits einen hat. Nur der Dienstleistungsweg erzeugt einen Kanal selbst, und das um den Preis, zunächst eine Agentur zu werden.

**Vor jeder weiteren Idee in diesem Feld günstig falsifizieren**: 15–20 Interviews mit der Frage, wofür der Käufer *heute schon jemanden bezahlt, es manuell zu erledigen*, dann den Service für drei zahlende Kunden manuell erbringen. ~4–6 Wochen für eine Person, ~€200. Wenn drei nicht für eine Concierge-Version zahlen, wird Software daran nichts ändern.

## 📋 Offene Fragen

1. ~~Ist €3.000–5.000 MRR ein Boden oder eine Decke?~~ **Beantwortet (Nutzer, 2026-08-21):** Ein echter Lebensunterhalt für drei, Perspektive erforderlich, auch wenn nicht von Anfang an. Durchgehend eingearbeitet — siehe Nenner-Abschnitt und die Wiederöffnungsprüfung.
2. **Offen — hängt die Bindung an *E-Rechnung* speziell, oder an „eine monetarisierbare B2B-SaaS im deutschen Compliance-Raum" allgemein?** Vom Nutzer offengelassen. Das ist relevant, weil die beiden obigen Regeln der übertragbare Ertrag dieser Recherche sind — falls Letzteres zutrifft, sollte der nächste Konzept-Durchlauf von einer Regel statt von einer Technologie ausgehen.
3. **Offen — wäre der Dienstleistungsweg akzeptabel?** Vom Nutzer offengelassen. Es ist der einzige Weg hier mit einer Obergrenze über €250.000 und der einzige, der Distribution selbst erzeugt — um den Preis, zunächst eine Agentur zu sein.

> **Begrenzte Negativbefunde.** Drei Befunde beruhen auf dem Fehlen von Gegenbeweisen und sollten nicht als Beweis gelesen werden: kein kleines Team, das einen zertifizierten Peppol-AP betreibt; keine Durchsetzung von § 26a gegen Kleinbetriebe; keine deutsche Konvention für §35a über BT-160/161. Die deutschen/französischen Anbieterzahlen sind eigene Auszählungen der Prüfung, keine veröffentlichten Kennzahlen.
