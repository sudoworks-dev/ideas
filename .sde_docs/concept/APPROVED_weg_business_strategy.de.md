# 💡 Konzept: Die optimale Geschäftsstrategie hinter dem WEG-Befund

> Deutsche Fassung von `DRAFT_weg_business_strategy.md`. Bei Abweichungen gilt die englische Datei als Original.

## 📌 Status

`DRAFT` · **v2** — v1 empfahl ein ausgelagertes Buchhaltungs-Back-Office. Eine unabhängige Widerlegung gab **`BLOCK`** zurück, und der Einwand hielt stand. v2 **streicht** diese Form, statt sie abzusichern, korrigiert einen juristischen Lesefehler, den v1 mit hoher Konfidenz behauptet hatte, und berichtet, was die Runde tatsächlich hervorgebracht hat: **eine korrigierte Suchspezifikation und eine Gabelung für den Nutzer.**

| Feld | Wert |
|---|---|
| Erstellt | 2026-08-28 |
| Baut auf | `DRAFT_belegverwaltung_produktvision.md` v3 · `DRAFT_erechnung_monetization.md` v3 |
| Team | 2–3 Personen, Agentic-Dev-Hintergrund, **keine Distribution, kein Domänenvertrauen** |
| Ziel | **€8k MRR ≈ €96k/Jahr** (Nutzer, 2026-08-28) |
| Services-Grenze | Nur als Akquise/Onboarding, **dauerhaft <20% der Teamzeit** (Nutzer, 2026-08-28) |
| Recherche | 6 delegierte Pässe + 1 adversarialer Pass |
| Adversarial Review | **`BLOCK`** — aufgelöst durch **Streichung** der vorgeschlagenen Lösung. Der Reviewer hat Beisheim, Scalara, VDIV, das BMF-Schreiben und die Adresslisten eigenständig geprüft und eine Wettbewerbskategorie gefunden, die v1 nie untersucht hatte |
| **Entscheidung** | **Ast B gewählt** (Nutzer, 2026-08-29) — die deutsche Immobilienverwaltung wird verlassen, die Suche gegen die vier Filter neu spezifiziert. Ast A ist geschlossen, nicht vertagt |
| Reviewer-Unabhängigkeit | **`same-model-fallback`** — vierte Runde ohne modellfremde Prüfung. Der Reviewer merkte an, dass v1s juristischer Fehler *genau* die Fehlerklasse ist, die ein gleichmodelliger Prüfer am wenigsten findet — er fand ihn nur durch Abruf der Quelle. Alle juristischen Überlegungen hier sind daher nicht unabhängiger als die von v1 |

---

## ⚖️ Verdikt

**Keine Form in der deutschen Immobilienverwaltung überlebt die gesetzten Randbedingungen.** Das ist ein negatives Ergebnis — und nach drei Konzepten das nützliche, weil der Grund jetzt präzise benennbar ist und nicht an den Ideen liegt.

> **Der Engpass war nie, welche Idee man wählt. Er ist, dass dieses Team keine Distribution und kein Domänenvertrauen hat — und jede Form, die in diesem Feld die Ökonomie schafft, braucht das Zweite stärker als die verworfenen Ideen.**

Zwei Dinge fallen aus dieser Runde ab, beide handlungsfähig:

1. **Eine Gabelung mit ehrlicher Ökonomie auf beiden Ästen** (§ *Die Gabelung*), von denen einer ein reales, unglamouröses, bestehendes Geschäft ist — falls die <20%-Grenze fällt.
2. **Vier Filter**, die jede nächste Idee bestehen muss, jeder aus einem dokumentierten Fehlschlag abgeleitet statt aus einem Prinzip (§ *Die korrigierte Spezifikation*).

**Der Nutzer hat Ast B gewählt** (2026-08-29): die Domäne wird verlassen, nicht die Randbedingung gelockert. Was in die nächste Runde übergeht, sind die vier Filter — nicht die Formen aus diesem Dokument.

**Und eine Handlung, die eine Woche kostet und in drei Runden nie erfolgt ist:** zwanzig Telefonate. Alles hier ist Schreibtischrecherche. Das Projekt hat null Minuten primären Kundenkontakt.

---

## 🎯 Problemstellung

Gegeben, dass (a) die E-Rechnungs-Kategorie geschlossen ist und (b) Distribution in jeder Runde der bindende Engpass war — was ist die beste verfügbare Geschäftsstrategie für 2–3 Entwickler ohne Distribution, um €8k MRR in der deutschen Immobilienverwaltung zu erreichen?

---

## ⛔ v3s WEG/GoBD-Nische — geschlossen, aber nicht aus v1s Grund

**v1 behauptete, die juristische Prämisse sei widerlegt, mit „hoher Konfidenz — Primärquellen". Das war falsch, und es war dieselbe Fehlerklasse, die v1 bei v3 diagnostiziert hatte.**

Das [BMF-Schreiben vom 9.4.2026](https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Umsatzsteuer/Umsatzsteuer-Anwendungserlass/2026-04-09-unternehmereigenschaft.html) (III C 2 – S 7104/00030/006/041) setzt die JStG-2022-Änderung des § 2 Abs. 1 UStG im UStAE um: Unternehmereigenschaft besteht **unabhängig von der Rechtsfähigkeit**, nicht rechtsfähige Gemeinschaften *können* also Unternehmer sein. **Das ist ein erweiterndes Schreiben — es räumt ein Hindernis zugunsten von v3 aus.** v1 las es als einschränkend. Und v3s struktureller Einwand steht unbeantwortet: **§ 4 Nr. 13 UStG** befreit Leistungen der WEG an ihre Mitglieder — was nur Sinn ergibt, wenn diese Leistungen sonst steuerbare unternehmerische Leistungen wären. Eine Befreiung *setzt* Unternehmereigenschaft voraus, statt sie zu verneinen.

**Was zutrifft:** GoBD bindet eine WEG *als solche* nicht — für gewöhnliche WEG-Unterlagen existiert kein gesetzliches Aufbewahrungsregime ([Greiner, ZMR 2018](https://www.greiner.one/images/publications/Aufsaetze/2018_02_Aufbewahrung_WEGUnterlagen_ZMR_2018_131.pdf)) — und in drei Runden wurde kein Fall einer nach § 26a UStG sanktionierten WEG gefunden.

**Die Form schließt trotzdem, aus kommerziellen Gründen, die kein juristisches Argument brauchen:**

| | |
|---|---|
| **Preis** | `selbstverwalten.com/preise`, **erstverifiziert 2026-08-28**: €8,16 / €12,74 / €20,07 pro Einheit/Monat *inkl. MwSt*, jährliche Abrechnung, −20% ab 11 Einheiten, −35% ab 26, −50% ab 51. |
| **Korrigierter ARPU** | Selbstverwaltete WEGs sind Gemeinschaften „bis zu zehn Eigentümer" (Wohnen im Eigentum e.V.), nicht der 22-Einheiten-Durchschnitt, gegen den v3 rechnete → **€41–107 netto**, also **75–195 WEGs** für €8k statt 63–98. |
| **Keine Liste** | Es existiert kein WEG-Register. § 26a WEG registriert zertifizierte *Personen*, keine Gemeinschaften. |
| **Besetzt** | **Matera** (DE seit 2021, 10.000+ Einheiten, sechs Städte, ~€55M eingesammelt) · **dotega** (€1,3M Pre-Seed, HTGF; hält die Partnerschaft mit Wohnen im Eigentum — und WiE hat ~16.000 Mitglieder, der Kanal ist also klein *und* vergeben) · **objego** (ein Joint Venture von ista und Aareal Bank). |
| **Kein Nachfragesignal** | **Null von acht Anbietern bewirbt GoBD-konforme oder revisionssichere Archivierung.** In einem so umkämpften Markt ist das ein Nachfragesignal, keine Lücke. |

⚠️ **Ungelöst und ausgewiesen, nicht geglättet:** Die WEG-Zahlen widersprechen sich um Faktor 3,5 — ~427.000 (BT-Drs. 20/9890, ausdrücklich eine *Grundannahme*, Stand 2020) gegen >1,5 Mio. aus Fachquellen. Zensus 2024 zählt 9.277.939 Wohnungseigentumseinheiten, was keine der beiden Zahlen stützt. Die „43.000 selbstverwalteten WEGs" aus v3 sind keine Quelle, sondern 427.000 × 10% — beide Eingangswerte Annahmen aus demselben Dokument von 2020.

---

## ⛔ Die Umkehrung — an den Verwalter verkaufen — ist ebenfalls geschlossen

Geprüft, bevor irgendetwas empfohlen wurde, und an drei unabhängigen Fronten gescheitert:

- **Jeder Systemanbieter hat 2025 KI-Rechnungserfassung und automatische Kontierung ausgeliefert**: [casavi AI Assist](https://casavi.com/de/software/casavi-ai-assist/), Aareon AAVA, [DOMUS novio](https://www.domus-software.de/stetige-optimierung-und-technische-aufruestung/) (GA 01.04.2025), [Immoware24](https://support.immoware24.de/hc/de/articles/24670590424349-Aktivierung-und-Nutzung-der-KI-Features), [etg24](https://etg24.de/funktionen/e-rechnung-hausverwaltung/), iX-Haus, Facilioo, Scalara.
- **Ein vollständiges ERP inklusive dieser KI kostet ab €0,39 pro Einheit/Monat** ([Immoware24](https://www.hausverwaltungschecker.de/immoware24/), zzgl. €15/Monat Grundgebühr). Jedes Bolt-on wäre teurer als das System, an das es andockt. *(Die oft zitierten €199–599 von Scalara ließen sich nicht bestätigen — `scalara.de/preise` nennt keine Preise, nur ein Angebotsformular. Diese Zahl nicht weiterverwenden.)*
- **[Buena](https://tech.eu/2025/07/23/gv-and-20vc-back-buenas-vision-to-reinvent-property-management-through-ai-powered-rollups-with-58m-investment/) hat $58M eingesammelt** (GV, 20VC), um kleine Hausverwaltungen zu übernehmen — 60.000 Einheiten, 20 Firmen — und adressiert exakt die ~30.000 Kleinfirmen, die eine Kaltakquise anrufen würde. Jede Übernahme entfernt einen Interessenten.

---

## 🗑️ Was v1 vorschlug, und warum es gestrichen wurde

v1 empfahl ein **automatisierungsgetriebenes Buchhaltungs-Back-Office für kleine Hausverwaltungen**, gepreist zu €3–5 pro Einheit/Monat gegen Beisheims €5,90, mit dem Einstieg *„gebt uns die fünf Objekte, die ihr gerade abstoßt."* Die Widerlegung tötete es an vier Punkten, die sich nicht mildern, sondern nur entfernen lassen. Festgehalten, weil jeder eine wiederverwendbare Falle ist:

**1. Die Kategorie wurde nie geprüft.** v1 behandelte [Beisheim](https://beisheim.immo/) als Preisanker und nie als Wettbewerber. Es existiert eine etablierte deutsche Kategorie *Objektbuchhaltung auslagern*, die dasselbe Ergebnis an denselben Käufer mit demselben Fachkräftemangel-Pitch verkauft: [AZIW](https://aziw.de/kunden/) (nach Kundenreife segmentiert — ein ausgereifter Go-to-Market, kein Neueinsteiger), [HausEasy](https://www.hauseasy.de/) (Monatspauschale nach Einheiten, arbeitet *innerhalb* der bestehenden Software des Kunden), [LINSTAD](https://www.linstad.de/objektbuchhaltung-auslagern), [Dash](https://www.dash-abrechnung.de/ueber-uns/) (GoBD-zertifiziert), [Akkurat](https://www.akkurat-abrechnung.de/). v1 führte einen Pass gründlich genug durch, um acht ERP-Anbieter auf GoBD-Marketing zu prüfen — und prüfte nicht, wer sonst verkauft, was es zu verkaufen empfahl.

**2. Der „Undercut" verglich Ungleiches.** Beisheims €5,90 enthält **Zahlungsverkehr per EBICS, GoBD-Archivierung, Forderungsmanagement und Mahnwesen**. v1 schloss die Zahlungsausführung ausdrücklich aus. Schmalerer Umfang zu 51–85% des Preises, von einem unbekannten Anbieter, gegen einen Etablierten mit kostenlosem Onboarding — das ist *teurer* pro geliefertem Ergebnis, und es gibt genau die beiden terminkritischsten Aufgaben zurück, von denen der Kunde entlastet werden wollte.

**3. Der Nenner war falsch, und zwar zugunsten des Designs.** Umsatz ist pro Einheit; **Kosten fallen pro Objekt und pro Buchung an.** Eine 5- und eine 50-Einheiten-WEG haben etwa gleich viele Lieferantenrechnungen, eine Teilungserklärung, ein Bankkonto, einen Wirtschaftsplan, eine § 28-Abrechnung. v1 leitete Minuten-pro-Einheit aus einem **32-Einheiten-Objekt** ab und wandte sie auf einen Wedge aus **5–10-Einheiten-Objekten** an — eine Strafe von 3–6×, die es nie bemerkte. Gate und Wedge wurden an unvereinbaren Stichproben gemessen.

**4. Die 20%-Grenze riss, und die Arithmetik verdeckte es.** Die 67 h/Monat zählten nur Produktionsminuten — ohne Kaltakquise, Onboarding und Migration, ohne die Pro-Kunde-Konfiguration, die v1 seinen *Moat* nannte, ohne Rückfragen, Prüfung und Freigabe, Support und die Eigentümerversammlungs-Saison. Alles davon ist Teamzeit an Kundenarbeit. Schlimmer: die Branche selbst nennt eine Obergrenze, die die Grenze reißt — [mitarbyte](https://mitarbyte.com/blog/weg-abrechnung-ki-automatisieren-mitarbyte/) beziffert realistische Automatisierung auf **60–80% weniger Handarbeit** bei zwingender menschlicher Endfreigabe und schreibt klar: *„eine vollautomatische, rechtssichere WEG-Abrechnung auf Knopfdruck gibt es 2026 nicht."* Bei 60% ist die Grenze gerissen; sie hält erst oberhalb von ~71%, noch bevor die ausgeklammerte Arbeit hinzukommt. **Die Form ist strukturell ein BPO — und genau das schließt Randbedingung 2 aus.**

**Und der Wedge war mechanisch verkehrt herum.** Ein abgestoßenes Mandat ist *ganz* abgestoßen — der Verwaltervertrag endet, es bleibt keine Buchhaltung zum Übergeben. Der tatsächliche Pitch lautete: *„behalte ein Mandat, das du bereits als unrentabel eingestuft hast, und zahle mir obendrauf."* Der VDIV formuliert es selbst so: 57% trennen sich von Mandaten, die die **Wirtschaftlichkeitsanforderungen** verfehlen, 63% von **besonders zeitintensiven** Objekten — und zeitintensiv machen sie Eigentümerkonflikte, Beschlussanfechtungen, Sanierungsstau und ein Fixkostenblock pro Objekt, den 6 Einheiten nicht tragen, nicht die Buchhaltung. Die Antwort des Marktes steht im selben Datensatz: **12% geplante Gebührenerhöhungen, bis zu 17% bei kleinen Objekten.** Man erhöht den Preis; man lagert nicht aus.

---

## 🧩 Was tatsächlich überlebt

**Die Nachfrage ist real und verifiziert.** VDIV-Branchenbarometer 2025 (n=1.072 Firmen, bis zu 446 valide Datensätze je Frage), vom Reviewer unabhängig nachgeprüft: **73% nennen Fachkräftemangel als größte Herausforderung, 70% berichten Überlastung, 57% stoßen unrentable Mandate ab, 63% zeitintensive Objekte, ~14% nehmen keine Neumandate mehr an** (mehr als jede fünfte Kleinstverwaltung). Die Firmenzahl fiel von ~24.000 auf unter 22.000.

**Eine Käuferliste existiert — und ist weniger wert, als v1 behauptete.** Über sechs Anbieter verifiziert: [vertriebslisten.de](https://vertriebslisten.de/products/hausverwaltungen) 11.300 · [datenhalle.de](https://www.datenhalle.de/produkt/Haus-und-Grundst%C3%BCcksverwaltungen-in-Deutschland/) 12.484 · [firmenliste.net](https://www.firmenliste.net/product.php?idListe=311&katId=9&firmenliste=Hausverwaltungsunternehmen) 16.220 · [hausverwaltungen-adressen-kaufen.de](https://hausverwaltungen-adressen-kaufen.de/produkt/hausverwaltungen-adressen-deutschland/) 18.108 **zu €0,02/Adresse** · [adressen.kaufen](https://adressen.kaufen/branchen/immobilien/hausverwaltungen/) 33.459 · [adressbar.de](https://adressbar.de/branchendetail/Hausverwaltungsunternehmen-376) 7.849. Die Spanne von 4,3× und ein Höchstwert oberhalb der Zahl existierender Firmen bedeuten starke Dubletten. **Eine Liste, die jeder für €0,02 kauft, ist keine Distribution.** Sie verwandelt „keine Distribution" in „Kaltakquise zu Kaltakquise-Quoten" — und Erreichbarkeit war nie der bindende Engpass. **Vertrauen war es**, und ist es weiterhin: einem Fremden übergibt niemand Unterlagen über Fremdgeld.

**v1s Regel „gegen Arbeit preisen, nicht gegen Software" wird als Gesetz zurückgezogen und nur als Beobachtung behalten.** Sie beweist zu viel — sie empfiehlt genauso Reinigung oder Callcenter — und enthält keinen Term, der die Stärken dieses Teams referenziert; ehrlich angewandt selektiert sie also *gegen* ein Team, dessen Vorteil Software ist. Sie ist zudem teils ein **Suchartefakt**: Softwarepreise stehen auf öffentlichen Seiten und waren auffindbar; Dienstleistungspreise stehen hinter Angebotsformularen (AZIW, HausEasy, LINSTAD und Dash veröffentlichen alle keine), und Beisheim war auffindbar, *weil* es der Ausreißer ist, der publiziert. Und v1s eigener Satz gibt zu, dass der Vergleich ungültig ist — *„die einzige Variable ist, wie viel menschliches Urteil und Haftung der Verkäufer absorbiert."* Wenn Urteil und Haftung sich unterscheiden, ist es nicht dieselbe Arbeit. Die Lücke von 15–25× **ist** die Arbeit, plus Versicherung, plus Bilanz.

---

## 🔀 Die Gabelung

Beide Äste waren real, als sie geschrieben wurden. **Der Nutzer wählte am 2026-08-29 Ast B**; Ast A steht unten, weil die Argumentation, die ihn zur besseren *Dienstleistungs*-Form machte, wiederverwendbar bleibt — nicht, weil er offen wäre.

### Ast A — Einstieg in die Objektbuchhaltung, unter Aufgabe der <20%-Grenze · **GESCHLOSSEN (Nutzer, 2026-08-29)**

Die kleinste ehrliche Fassung, die die Widerlegung selbst vorschlug: **nur die § 28-Jahresabrechnung + Wirtschaftsplan verkaufen, als Festpreis pro Objekt und Jahr (~€500–900).**

| | |
|---|---|
| **Warum besser als v1s Form** | Objektbasierte Preisbildung **trifft den echten Kostentreiber**, die Kleinobjekt-Inversion verschwindet. Kein dauerhafter Zugriff auf Fremdgeld-Unterlagen — die größte Vertrauensbarriere wird entfernt, nicht gemildert. Das Ergebnis ist diskret, prüfbar und ablehnbar, ein Unbekannter muss also nur *einmal* Vertrauen gewinnen. |
| **Die Arithmetik** | €96k/Jahr ≈ **130–190 Objekte**. Kein MRR — saisonaler Jahresumsatz. |
| **Was es kostet** | Die Lieferung ballt sich in Q1–Q2 und ist brutal. Es ist ein Dienstleistungsgeschäft, Anbieter Nr. N in einer angebotsbepreisten Kategorie gegen AZIW, Akkurat, HausEasy, LINSTAD, Dash. **Randbedingung 2 muss aufgegeben werden, nicht umgangen.** |
| **Ehrliche Einschätzung** | Ein reales Geschäft mit realen Kunden, ohne Fantasie. Aber kein Softwareunternehmen — und die Entwicklungsgeschwindigkeit des Teams ist nicht der knappe Input; ausgebildete Immobilienbuchhalter, WEG-Urteilsvermögen und Vermögensschadenhaftpflicht sind es. |

### Ast B — Die Domäne ist für dieses Team falsch; die Suche wird neu spezifiziert · **GEWÄHLT**

Drei Runden haben eliminiert: generische E-Rechnung, fünf vertikale Wedges, Peppol, Multi-Jurisdiktion, Vereine, Kleinstbetriebe, WEG/GoBD, das Verwalter-Bolt-on und das Back Office. **Die Eliminationsrate ist der Befund.** Eine Strategie, die nach drei Eliminationsrunden als letzte übrig bleibt, wurde durch Erschöpfung gewählt, nicht durch Passung.

---

## 📐 Die korrigierte Spezifikation

Vier Filter, jeder aus einem dokumentierten Fehlschlag abgeleitet statt aus einem Prinzip. Jede nächste Idee muss alle vier bestehen:

1. **Der Käufer kann allein aufgrund des Produkts zusagen** — ohne zuerst Geld, Unterlagen oder Haftung zu übergeben. *(Tötet: jede Form in der Immobilienverwaltung. Vertrauen, nicht Erreichbarkeit, ist der bindende Engpass dieses Teams.)*
2. **Der Preis wird von etwas gesetzt, das nicht kollabiert** — keine Funktion, die jeder Etablierte als Pflicht-Häkchen ausliefern muss, weil Regulierung es erzwingt. *(Tötet: E-Rechnung, das KI-Bolt-on.)*
3. **Der tatsächliche Vorteil des Teams ist der knappe Input.** Ist der knappe Input eine Zulassung, eine zertifizierte Fachkraft oder eine Haftpflicht-Historie, ist Entwicklungsgeschwindigkeit irrelevant. *(Tötet: Ast A nach seinen eigenen Maßstäben, und die Verwalter-Route.)*
4. **Kostentreiber und Preismetrik teilen sich einen Nenner.** *(Die Pro-Objekt-gegen-Pro-Einheit-Falle; allgemeingültig, und unsichtbar, bis gemessen wird.)*

---

## ✅ Empfehlung

**Der Ast ist gewählt. Von der Empfehlung überlebt die Gewohnheit, nicht die Anrufliste.**

Die zwanzig Anrufe unten waren dafür entworfen, Ast A zu bepreisen. Mit dessen Schließung sind sie nicht mehr die nächste Handlung — *aber die Disziplin, die sie kodieren, ist das Einzige, was dieses Projekt nie getan hat, und sie muss unverändert in die nächste Domäne mitgenommen werden:*

> ~~20 Hausverwaltungen aus einer €0,02-Adressliste anrufen.~~ *(Durch die Ast-B-Entscheidung überholt.)* Nur zwei Fragen:
> *„Welche Mandate habt ihr in den letzten 12 Monaten abgegeben, und warum?"* — und — *„Wer macht eure Objektbuchhaltung, und was müsste passieren, damit ihr das ändert?"*
>
> Kosten: eine Woche, ~€400 Adressen. Bepreist Ast A, testet Filter 1 direkt und verwandelt drei Runden Schreibtischrecherche in die ersten Primärdaten des Projekts.

**Als Regel mitnehmen, nicht als Artefakt:** In der nächsten Domäne finden die zwanzig Gespräche *vor* dem Konzeptdokument statt, nicht danach. Filter 1 — *kann der Käufer allein aufgrund des Produkts zusagen?* — ist nur durch Fragen beantwortbar, und es ist der Filter, der hier alles eliminiert hat.

**Die Reihenfolge-Lektion ist inzwischen der Hauptbefund.** Drei Konzeptdokumente, ~330 Tool-Aufrufe, neun Recherchepässe, null Kundengespräche. Jede Runde hat den billigen Falsifikationsschritt empfohlen, keine hat ihn ausgeführt. Für ein Team, dessen Vorteil darin besteht, dass Bauen billig ist, lautet der bindende Engpass: **reden, bevor man entwirft** — und die Kosten des Unterlassens sind jetzt messbar: dieses Dokument ist das dritte.

---

## ⚖️ Verworfen

| Ansatz | Warum |
|---|---|
| WEG-GoBD-Archivierungs-SaaS (v3) | Kommerziell geschlossen — keine Liste, korrigierter ARPU, Matera/dotega/objego, null Nachfragesignal. *Nicht* juristisch widerlegt; v1s Rechtsargument war falsch. |
| KI-Bolt-on für Verwaltersoftware | Jedes ERP hat es 2025 ausgeliefert; ein volles ERP kostet ab €0,39/Einheit; Buena konsolidiert die Käufer. |
| Ausgelagertes Buchhaltungs-Back-Office (v1) | Gestrichen — siehe oben. Besetzte Kategorie, invertierter Wedge, falscher Nenner, strukturell ein BPO. |
| Ergebnisbepreiste Software ohne Dienstleistung | Die bequeme und die schlechteste Option. Die Lücke von 15–25× existiert *weil* der Verkäufer Urteil und Haftung absorbiert; verweigert man das, ist man wieder bei €0,39. |
| § 60b GEG Fristen-Tracking | Tatsächlich unbedient (kein Tracking-Produkt gefunden), harte Norm (≥6 Einheiten, Anlagen vor Okt. 2009 fällig bis **30.09.2027**, €5.000 nach [§ 108 GEG](https://www.gesetze-im-internet.de/geg/__108.html)) — aber das Geld fließt ans SHK-Handwerk (€100–300/Prüfung), es ist ein zweiseitiger Marktplatz mit Cold Start auf beiden Seiten, und die Frist ist eine abklingende Einmalwelle. |
| Trinkwasser / Legionellen (€25.000 + IfSG) | Techem/ista bündeln es bereits. Scheitert am Test „wird nicht vom Etablierten geliefert". |
| Verwalterwechsel-Plattform | Reale Reibung, unbewiesene Monetarisierung — sämtliche Übergabe-Ratgeber sind kostenloser Marketing-Content, und die Vermittlungsportale besitzen den Moment über Lead-Gebühren. |
| Selbst zertifizierter Verwalter werden | § 34c GewO + § 26a-Zertifizierung, frontal gegen Matera (~€55M) und Buena ($58M). |

---

## 📋 Offene Fragen

1. ~~**Welcher Ast?**~~ **Beantwortet (Nutzer, 2026-08-29): Ast B.** Die <20%-Services-Grenze bleibt bestehen, stattdessen wird die Domäne verlassen. Drei Runden in deutscher Compliance-Software haben keine tragfähige Form hervorgebracht, und das wird als Ergebnis akzeptiert statt wegverhandelt.
2. **Werden Kundengespräche dem nächsten Konzeptdokument vorausgehen?** Dreimal empfohlen, nullmal durchgeführt. Ast B macht dies zum ersten Test der neuen Spezifikation, nicht zu ihrer Fußnote.
3. **Welche Domäne kommt als Nächstes?** Hier bewusst offen gelassen — die Wahl ist ein eigener `/sde-concept`-Lauf, und Filter 3 (*der Vorteil des Teams ist der knappe Input*) sollte sie treiben, nicht die Marktgröße.
4. **Wie groß ist die WEG-Population wirklich?** 427.000 vs. >1,5 Mio. ungelöst. Betrifft hier keine Empfehlung und ist mit Ast B gegenstandslos.
5. **`reviewer_model` setzen** in `.sde_docs/config` — vierte Runde auf `same-model-fallback`, und diese Runde beweist die Kosten: v1s zentrale juristische Aussage war falsch und wurde nur durch einen Quellenabruf gefunden.

---

> **Begrenzte Negativa.**
> - **Vom Autor erstverifiziert:** ausschließlich `selbstverwalten.com/preise`. **Vom Reviewer unabhängig verifiziert:** Beisheims €5,90 samt Leistungsumfang, die sechs Adresslisten-Anbieter, die VDIV-Zahlen, das BMF-Schreiben und dass Scalara keine Preise veröffentlicht.
> - **Aus v1 zurückgezogen:** die Preisuntergrenze von €1,50–2,50/Einheit für interne Kräfte war eine eigene Annahme des Autors und ist vermutlich zu niedrig — bei einer typischen Auslastung von 800–1.200 Einheiten je Objektbuchhalter sind es €4–6/Einheit, was das darauf gebaute Argument umkehrt. Die Formulierung „€3–5 ist teurer als ein Angestellter" wird vollständig zurückgezogen.
> - **Aus v1 zurückgezogen:** Scalara zu €199–599. Nicht verifizierbar; der Anbieter veröffentlicht keine Preise.
> - **Fehlende Evidenz ist kein Beweis der Abwesenheit:** keine nach § 26a UStG, § 108 GEG oder TrinkwV sanktionierte WEG; kein § 60b-Tracking-Produkt; kein Dritt-Bolt-on-Anbieter, von dem Erfolg *oder* Scheitern bekannt wäre. Jedes schwächt; keines beweist.
> - **Dass § 60b die GEG-Reform vom Juli 2026 überstanden hat, ist erschlossen** aus dem Änderungsdatum der Gesetzesseite, nicht aus einem Kommentar, der die Textgleichheit bestätigt.
> - **Der Reviewer lief auf dem Modell des Autors.** Seine juristische Argumentation trägt dieselben blinden Flecken wie das Dokument, und er sagt das selbst.
> - `.sde_docs/config` fehlt — läuft auf Defaults; `/sde-status` kann sie anlegen, um `adversarial_review` / `reviewer_model` zu konfigurieren.
