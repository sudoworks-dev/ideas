# 💡 Konzept: Minifig Scout — Bewertungswerkzeug für einen Solo-BrickLink-Händler

> 🇩🇪 Deutsche Fassung von [`DRAFT_minifig_price_scout.md`](./DRAFT_minifig_price_scout.md). Diese Datei ist eine Übersetzung zur Lesbarkeit — die englische Fassung bleibt die maßgebliche Version für weitere Bearbeitung und Freigabe.

## 📌 Status

`DRAFT` · **v6** (v5 hat das Kostenmodell verifiziert; v6 beantwortet direkt, ob irgendein Skalierungsweg zu ernsthaftem Einkommen führt — Verdikt: **nein**, nicht über diesen Mechanismus)

| Feld | Wert |
|---|---|
| Erstellt | 2026-08-21 |
| Ziel | **Kommerzieller Handel** — nur Minifiguren (BrickLink-Typ `M`) |
| Kapital | 2.000 € zum Start → 20.000 €+ später (Nutzer, 2026-08-21) |
| Repository | Eigenes Repo; dieses Konzept bleibt in `ideas` |
| API-Zugang | Registrierungsformular wird angezeigt, Consumer-Keys lassen sich anlegen. **Noch nicht verifiziert:** ob die Schlüsselausstellung abgeschlossen wird, ob ein Member-Tier-Key auf `/items/minifig/{no}/price` ein 200 liefert, oder ob der Account die Prüfung übersteht |
| Unabhängiges Review | v2 → **Block** (aufgelöst). v3 → **Block** mit 16 Widerlegungen, meist interne Widersprüche; hier durch Streichung aufgelöst. Das Review lief auf demselben Modell wie der Autor — es teilt also einen realen Teil von dessen blinden Flecken und ist keine echte unabhängige Zweitmeinung |
| Marktrealität | **17.883 Shops · 6.294.965 gelistete Minifiguren.** Meistverkaufte Minifigur = 1.388 Transaktionen in 6 Monaten ≈ **7,7/Tag weltweit**; Rang 20 ≈ 2,3/Tag ([browse](https://www.bricklink.com/browse.asp), [sold stats](https://www.bricklink.com/catalogStatsSold.asp?itemType=M&v=0), abgerufen 2026-08-21) |
| Beispiel | `sw0181` (Starkiller) — aus einer separaten Beispielnotiz; dessen Zahlen sind **KI-simuliert und unverifiziert** |

---

## 🎯 Problemstellung

**Wo lässt sich Kapital so in Minifiguren einsetzen, dass die Rendite Gebühren, Versand, Steuern und Liegezeit übersteht — wiederholbar, in einer Größe, die eine Person betreiben kann?**

Die maßgebliche Restriktion ist **Kapitalumschlag, nicht Wertsteigerung**. Ein Sammler optimiert den Preis; ein Händler optimiert die Rendite pro Euro pro Woche.

Entscheidend: **Keine Menge an Preisdaten beantwortet diese Frage.** Die beiden Unbekannten sind die Gesamt-Take-Rate und die *tatsächliche* Liegezeit, und beide sind nur durch echten Handel beobachtbar. Genau diese Erkenntnis hat dieses Konzept von einer Datenplattform auf ein Skript und eine Tabelle reduziert.

---

## 🔢 Die verifizierte Ökonomie

### Ein Inlandsgeschäft, jede Abzugsposition belegt

Deutscher, umsatzsteuerpflichtiger Verkäufer, gekauft für 45 €, verkauft für 75 € brutto an einen deutschen Käufer, 4,99 € Versand berechnet:

| Position | Betrag | Quelle |
|---|---|---|
| Artikelpreis (inkl. 19 % USt) | 75,00 € | — |
| abzgl. 19 % USt | −11,97 € | gesetzlich |
| Netto-Artikelpreis | 63,03 € | — |
| **BrickLink-Provision** — 3 % des **USt-Netto-Artikelpreises**, Versand ausgenommen | −1,89 € | [help #38](https://www.bricklink.com/help.asp?helpID=38) |
| **PayPal DE** 2,99 % + 0,39 € auf 79,99 € Eingang | −2,78 € | [PayPal DE](https://www.paypal.com/de/webapps/mpp/merchant-fees) |
| Berechneter Versand / tatsächliches Porto (DHL Kleinpaket, getrackt) | +4,99 € / −3,19 € | Portobetrag aus Sekundärquelle, unverifiziert |
| Wareneinsatz | −45,00 € | — |
| **Netto, vor Verpackung, Arbeit und Tooling** | **≈ +16,16 €** | |

**Die Plattform-Take-Rate liegt bei ~6,2 % vom Brutto** — davon ist BrickLink nur 2,5 Prozentpunkte; **PayPal 3,7**. Die Provision ist *nach Bestellgröße* gestaffelt, fällt auf 2 % über 500 $ und 1 % über 1.000 $, ohne Monats- oder Einstellgebühren ([help #38](https://www.bricklink.com/help.asp?helpID=38)). Die vielzitierte "5 % BrickLink-Gebühr" ist falsch — sie stammt aus KI-generierten SEO-Blogs.

**Zwei sofort umsetzbare Konsequenzen:**

- **Stripe statt PayPal nutzen.** Stripe DE liegt bei 1,5 % + 0,25 € auf EWR-Karten gegenüber PayPals 2,99 % + 0,39 € ([Stripe DE](https://stripe.com/de/pricing)). Bei dieser Bestellung sind das 1,45 € statt 2,78 € — **1,33 € gespart, ~8 % der Nettomarge**, für eine einmalige Einrichtung. Vorbehalt: Unterschiede bei Chargeback/Käuferschutz vorher prüfen.
- **Die Kleinunternehmer-Entscheidung übertrifft alles, was die Software je optimieren könnte.** Nach §19 UStG entfällt die 11,97-€-USt-Zeile und derselbe Trade bringt **≈ 28,13 €** statt 16,16 € netto — dafür entfällt der Vorsteuerabzug. Diese eine Entscheidung ist **~12 € auf einen einzigen 75-€-Verkauf wert, mehr als sämtliche Plattformgebühren zusammen.** Keine Preisoptimierung kommt dem nahe. Das gehört zum Steuerberater, bevor irgendetwas anderes passiert.

### Der US-Kanal ist geschlossen — Cross-Region-Arbitrage gestrichen

Das war eines von drei Signalen im Skript von v4 und stammte aus "Strategie A" der Beispielnotiz. Es übersteht die Versandregeln 2025/26 nicht:

- Waren sind **vom internationalen Briefversand ausgeschlossen**: "Im internationalen Briefversand sind Waren grundsätzlich – bis auf wenige Ausnahmen – ausgeschlossen" ([Deutsche Post](https://www.deutschepost.de/de/b/brief-national2027_Aenderungen.html)). Der 1,80–3,30-€-Weg "einfach als Großbrief International verschicken", den kleine Verkäufer nutzen, ist für gewerbliche Ware kein zulässiges Produkt.
- **Warenpost International erfordert einen Geschäftsvertrag ab ≥200 Sendungen/Jahr** ([Deutsche Post](https://www.deutschepost.de/de/w/warensendung.html)) — ein Einsteiger-Händler qualifiziert sich nicht.
- **Postalischer Warenversand in die USA läuft seit 23.09.2025 nur für Geschäftskunden**, über PDDP ([DHL](https://group.dhl.com/de/presse/pressemitteilungen/2025/dhl-paket-nimmt-postalischen-warenversand-aus-deutschland-in-die-usa-und-puerto-rico-fuer-geschaeftskunden-wieder-auf.html)); die US-Bagatellgrenze endete am 29.08.2025, jede Sendung ist seitdem zollpflichtig ([WKO](https://www.wko.at/aussenwirtschaft/wegfall-de-minimis-regel-usa)).
- Ohne Vertrag bedeutet gewerblicher US-Versand DHL Express/UPS/FedEx — Referenzwert **22,49 €** für ein Päckchen M, sofern überhaupt buchbar ([paketda](https://www.paketda.de/ausland/usa.html)).

Plattform- und Zahlungsabzüge bei einem US-Verkauf betragen **8,62 € auf 75 € (11,5 %)**, etwa das Doppelte des Inlandswerts — und dann **übersteigt der günstigste legale Versand die gesamte Bruttomarge von 30 €**. **Nur mit Inland + EU rechnen.**

### Die Obergrenze für Phase A

| | |
|---|---|
| Eingesetztes Kapital (2.000 € abzgl. ~20 % Puffer) | ~1.600 € |
| Einkaufspreis für einen Flip-Kandidaten | 10–15 € |
| Gehaltene Lots | ~110–160 |
| Realisierte Umschläge pro Jahr | 1,3–3 (Liegezeit 4–9 Monate, **unbemessen**) |
| **Optimistischer Nettogewinn, Jahr eins** | **≈ 500–1.500 €** |

Optimistisch: kein Ladenhüter, keine Retouren, die eigenen Stunden mit null bewertet. **Das ist die Zahl, die jeden Build mit mehrjähriger Amortisation disqualifiziert** — genau das Design von v3.

### Bauen oder kaufen — die unbequeme Rechnung

**[BL Metrics](https://www.blmetrics.com/) verkauft dieses Produkt bereits**: "Sourcing — find the right sets, parts and minifigures to buy, with regional ROI and arbitrage opportunities" plus "smart pricing formulas that automatically adjust based on market data, cost, and sell-through rates". **49 $ / 99 $ / 129 $ pro Monat.** [Bricqer](https://www.bricqer.com/guides/pricing-formulas) verkauft automatisches Repricing für 3,5 % vom Verkaufswert, mindestens 50 $/Monat.

Dagegen der Phase-A-Gewinn von 500–1.500 €/Jahr ≈ **42–125 €/Monat**:

> **Das kommerzielle Werkzeug kostet ungefähr hundert Prozent des Phase-A-Gewinns.** Bei 2.000 € Kapital kannst du dir dieses Tooling weder kaufen noch — sobald deine Stunden etwas zählen — selbst bauen. Software wird erst ab einem Kapitalniveau rechtfertigbar, bei dem der Jahresgewinn deutlich über den ~1.200 €/Jahr Tooling-Kosten liegt — und selbst dann könnte Kaufen das Bauen schlagen.

Das ist die ehrliche Einordnung, und sie ist der Grund, warum der Build unten 150 Zeilen umfasst statt eine Plattform zu sein.

---

## 🚧 Durch Recherche belegte Einschränkungen

### Scraping ist ausgeschlossen
- [`robots.txt`](https://www.bricklink.com/robots.txt) sperrt **`/catalogPG.asp`** — genau die Price-Guide-Seite.
- [Web Robots / Spiders Policy](https://www.bricklink.com/help.asp?helpID=139): "any robot, spider, other automatic device, **or manual process** to monitor or copy our web pages".
- [API-ToS](https://www.bricklink.com/v3/terms_of_use_api.page): verbietet Reverse-Engineering interner Feeds "**even if such data is not available in the BrickLink API**".
- **AWS WAF** auf `bricklink.com`; `help.bricklink.com` liefert Cloudflare-403 an Nicht-Browser-Agenten.

### API-Eignung — nicht geklärt
Die [API-ToS](https://www.bricklink.com/v3/terms_of_use_api.page) (Revision vom 02.02.2023) besagt: "**Registered sellers of the Website ("BrickLink Sellers") may register to the API.**" Neu eingeführt in dieser Revision; bestätigt durch [BricklinkSharp](https://github.com/gebirgslok/BricklinkSharp) und [BrikBiz](https://www.brikbiz.com/faqs.html).

**v3 behauptete, dies sei gelöst, weil das Formular angezeigt wird. Das war derselbe Fehler wie bei Playwright in v1** — erst diagnostizieren, dass eine nicht durchgesetzte Kontrolle keine Lizenz ist, dann eine gerenderte Seite als eine behandeln. Ein gerendertes Formular belegt nur, dass eine Seite rendert. Die eigentliche Lösung ist das [Seller-Upgrade](https://www.bricklink.com/help.asp?helpID=2440), das die Händler-Entscheidung ohnehin erfordert.

### Der Datenvertrag
`GET /items/minifig/{no}/price?guide_type=sold` liefert neben Aggregaten ein `price_detail[]` mit einzelnen datierten Verkäufen (`unit_price`, `quantity`, `seller_country_code`, `date_ordered`). `guide_type=stock` liefert aktuelle Angebote als `(unit_price, quantity, shipping_available)` — **keine Verkäuferidentität, keine Lot-ID.** Kontingent: **5.000 Calls/Tag**; Neu und Gebraucht sind separate Calls.

Das 6-Monats-Fenster ist live und unarchiviert ([Help #31](https://www.bricklink.com/help.asp?helpID=31)), und es existiert keine öffentliche historische Minifiguren-Zeitreihe. Das bleibt wahr — es ist nur nicht mehr das Problem, das dieses Projekt lösen muss (siehe *Gestrichen*).

---

## 💡 Der Build

Drei Schritte. Gesamte Software: **ein Skript.**

### Schritt 1 — Das Handelsprotokoll (diese Woche, vor jedem Code)

Eine Tabelle. **Zehn abgeschlossene Trades**, rund 300 € Kapital, jede Abzugsposition notiert: Einkaufspreis, BrickLink-Provision, Zahlungsgebühr, Porto, Verpackung, Liegezeit, Netto.

Das ist das entscheidende Experiment, und v3 hatte es überhaupt nicht eingeplant. Es beantwortet das eine Risiko, das die Prämisse kippen kann — *sind die Margen da?* — und misst die beiden Unbekannten, die die Problemstellung benennt. Nichts in Software bringt diesen Tag näher, und vier Monate Bauzeit vor dem ersten echten Datenpunkt war der schlimmste Fehler in der Reihenfolge von v3.

### Schritt 2 — Das Bewertungsskript (~150 Zeilen)

Python 3.12 + uv. `httpx` + `requests-oauthlib` für OAuth1 HMAC-SHA1, oder ~80 Zeilen von Hand geschrieben. Kein Scheduler, keine Datenbank, keine Web-App.

Eine Funktion, `value(item_no, condition)` → 2–3 Live-Calls, liefert:

| Output | Quelle |
|---|---|
| Verkaufsmedian (robust gegen Ausreißer) | Median aus `sold` → `price_detail[].unit_price`. ⚠️ Strukturell **nach unten** verzerrt — siehe *Risiken* |
| Verkäufe pro 182 Tage — **Liquidität** | `sold` → `unit_quantity` |
| Lots unter 70 % des Medians — **Tiefe** | Anzahl über `stock` → `price_detail[]` |
| **Verteilung der Liegezeit** — das differenzierende Signal | Abstände zwischen aufeinanderfolgenden `date_ordered`-Werten in `sold` → `price_detail[]` |
| Angebotsdeckel, auf Anfrage | `/items/minifig/{no}/supersets` → Anzahl Sets |

**Die Ableitung der Liegezeit ist das einzige hier, was noch nicht kommodifiziert ist.** Kein öffentlicher Datensatz bildet ab, wie lange eine Minifigur im Regal liegt, und die kommerziellen Tools werben nur mit einer aggregierten "Sell-Through-Rate". Aber `price_detail[].date_ordered` liefert datierte Einzeltransaktionen, sodass die *Verteilung* der Intervalle zwischen Verkäufen pro Figur aus einem einzigen Call berechenbar ist. Da Umschlag — nicht Marge — die bindende Restriktion ist (siehe *Risiken*), ist das die Zahl, die jede Kaufentscheidung steuern sollte, und der stärkste Grund, ein eigenes Skript zu schreiben statt eines zu mieten.

**CSV rein, CSV raus**, sodass eine gelieferte Bulk-Lot-Liste in einem Lauf bepreist wird: 200 Figuren = 200 Calls = 4 % des Tageskontingents. Das macht ~25 Bulk-Lot-Bewertungen pro Tag möglich, ganz ohne gespeicherte Daten.

**Plus fünf Zeilen: jede Rohantwort gzippen und auf die Platte schreiben**, mit dem Schlüssel `(no, condition, fetch_date)`. Das ergibt ein wachsendes Archiv genau der Figuren, die tatsächlich angefasst werden, bei null zusätzlichen Call-Kosten und fast null Code — und ist der einzige überlebende Teil der Archiv-Ambition von v1–v3.

### Schritt 3 — Gesteuert durch Schritt 1, bewusst offen gelassen

Zeigt das Handelsprotokoll echte Margen, wird gebaut, was es als Engpass identifiziert. Ist Sourcing die Restriktion, wird Sourcing gebaut; ist es die Bepreisung des eigenen Bestands, wird der Repricer gebaut. **Jetzt schon zu entscheiden hieße, ohne die Information zu entscheiden, für die Schritt 1 existiert** — genau die Regel, die v3 aufgestellt und dann für seine größte Komponente außer Kraft gesetzt hat.

---

## 🔧 Übernommene Korrekturen

Reale Fehler aus früheren Versionen; sie gelten für das obige Skript.

- **`country_code` und `region` schließen sich im API-Vertrag gegenseitig aus.** Werden beide gesendet, wird eines stillschweigend ignoriert. Beide filtern nach *Shop-Standort*, nicht nach "liefert zu dir", und der Price Guide **liefert überhaupt keine Versandkosten**. Pro Call nur eines verwenden: `region=eu` für statistische Breite bei `sold`, `country_code=DE` für Kaufbarkeit bei `stock`.
- **Währung ist eine Archiv-Falle.** `currency_code=EUR` rechnet zum Kurs des Abfragetages um, sodass derselbe historische Verkauf bei späterem erneutem Abruf einen anderen Eurowert liefert. Preis niemals in einen Dedup-Key aufnehmen; immer das Abrufdatum speichern.
- **Truncation ist unbemessen, und sie trifft dort am härtesten, wo es für einen Händler am meisten zählt.** Ist `price_detail[]` bei umsatzstarken Figuren gedeckelt, sind die Daten ausgerechnet bei der liquiden, schnell drehenden Ware am schlechtesten, die die Umschlags-Doktrin zu handeln empfiehlt. Beim ersten Live-Call die Eintragsanzahl gegen `unit_quantity` vergleichen und einmal gegen die Website gegenprüfen. Wiederholtes Abrufen behebt Truncation nicht — fünf identische abgeschnittene Enden sind ein abgeschnittenes Ende.
- **Die 25-€-Kollision.** v3 verwendete 25 € gleichzeitig als minimalen *Verkaufs*preis und als durchschnittlichen *Einkaufs*preis, wodurch die Marge konstruktionsbedingt null wird. Es sind unterschiedliche Zahlen: Verkaufsuntergrenze ≈ 25 €, Einkaufspreis ≈ 10–15 €.
- **Die 2-Monats-Liegezeit war erfunden.** Der eigene Text von v3 widersprach ihr zweimal (30 % Ladenhüter über ein Jahr hinaus; 20–60 Transaktionen/Jahr bei einer mittelklassigen Figur). Vertretbarer Bereich sind **4–9 Monate**, und das Handelsprotokoll wird die Schätzung durch eine Messung ersetzen.

---

## ⚖️ Nach Review gestrichen

Streichung, keine Absicherung — jeder Punkt ist weg, mit ehrlich benannter Konsequenz.

| Gestrichen | Warum | Was dadurch fehlt |
|---|---|---|
| **Voll-Katalog-Sweep** (37k Calls/Durchlauf, Enumeration, adaptive Taktung, GB/Jahr) | **Die entscheidende Erkenntnis.** Alle drei Features sind *Live-Call*-Features — Repricing, Lot-Bewertung und Umschlags-Ranking brauchen jeweils einen Call jetzt, über einen Artikel, der gerade vorliegt. Ein 37 Tage alter Median ist strikt schlechter als ein frischer Call. Der einzige einzigartige Output des Sweeps ist eine mehrjährige Reihe, deren Nutzen im Dokument selbst mit 24–36 Monaten datiert wurde — gegen ein Geschäft, das bei ~1.000 €/Jahr gedeckelt ist und das Schritt 1 erst validieren oder verwerfen soll | Die Langzeitreihe. Sie um 6 Monate zu verschieben kostet 6 Monate Historie *für Figuren, die nicht gehandelt werden* — der Verlust ist real, aber klein gegen eine 3-Jahres-Amortisation, und die Logging-Gewohnheit aus Schritt 2 bewahrt sie für alles, was tatsächlich angefasst wird |
| **Seine Rechtfertigung** | v3 begründete den Sweep mit "Entdeckung braucht die Grundgesamtheit" für Zweck #2 — und stufte Zweck #2 im selben Dokument ab und übergab ihn "ab Tag eins" an BrickEconomy. Die Rechtfertigung verflüchtigte sich, ohne dass es auffiel. Die Abdeckung lag bei 100–300 beobachteten Figuren pro handelbarer Figur, und die am Rand gesweepte Figur ist konstruktionsbedingt eine, die sich nicht verkauft | — |
| **Repricing als erstes Feature** | Widersprach der eigenen Phasierung des Dokuments ("manuell ist bei 50–100 Lots machbar", "Automatik ab ~300 unvermeidlich"). Es ist das **kapitalabhängigste** Feature, also bei 2.000 € das letzte und bei 20.000 € das erste — die Kapitallogik war invertiert. Es gibt keinen Bestand, keinen Seller-Account, Automatik könnte untersagt sein, und der Ertrag liegt bei ~220 €/Jahr gegen den Bau eines authentifizierten Schreibpfads | Heute nichts. Bei ~100 Lots ist Repricing von Hand unter einer Stunde im Monat |
| **18,5k einmaliger Superset-Sweep** | Supersets für die ~150 tatsächlich in Betracht gezogenen Figuren abrufen: 150 Calls, auf Abruf | Nichts |
| **SQLite + Rohantwort-Tabelle** | Gzippte Dateien sind bei diesem Volumen dasselbe Archiv mit weniger Code | Nichts |
| **Stage-2-Web-App** (FastAPI/Jinja2/HTMX/Chart.js) | Eine CSV in einer Tabelle erledigt es bei ~100 Lots | Nichts. Das war deine geäußerte Präferenz für die Oberfläche und wird verschoben, nicht abgelehnt — sinnvoll wird es irgendwo jenseits einiger hundert Lots |
| **Die tägliche 40-Figuren-Ask-Watchlist + 60-Tage-Gate** | Der Korb müsste jetzt gewählt werden, vor Bestand, These oder einer einzigen realisierten Marge — 60 Tage Daten über einen ohne Information gewählten Korb | Das Lot-Überlebens-Experiment. Nach Schritt 1 wieder einführen, wenn der Korb aus tatsächlich gehandelten Figuren gewählt werden kann |
| **BrickEconomy als Kernkomponente** | Anleger-Horizont-Metriken für ein Geschäft, das in Wochen denkt | Nichts; als gelegentlichen manuellen Nachschlag behalten |
| **Das 20.000-€-Ranking-Metrik-Design** | Verfrüht und selbstwidersprüchlich — siehe *Der 20.000-€-Widerspruch* unten | Nichts; löst sich zu einer Zahl in einer Konfigurationsdatei auf, wenn es soweit ist |

### Der 20.000-€-Widerspruch — gelöst: kein Skalierungsweg führt zu ernsthaftem Geld

v5 hat das als "deine Entscheidung" offengelassen. Direkt gefragt — **gibt es eine vernünftige, realistische Chance, das zu ernsthaftem Einkommen zu skalieren?** — lautet die ehrliche, unten hergeleitete Antwort **nein**, nicht über diesen Mechanismus. Das ist die einzelne entscheidendste Schlussfolgerung im gesamten Dokument, deshalb wird sie hier explizit hergeleitet statt als Geschäftsentscheidung ohne Verdikt stehen zu bleiben.

**Definition "ernsthaft":** ~24.000 €/Jahr (2.000 €/Monat) — ein echtes Einkommen, kein Taschengeld. Was würde das erfordern?

**Gleiche Stückökonomie, mehr Kapital.** Phase As eigene optimistische Obergrenze liegt bei 31–94 % Jahresrendite auf eingesetztes Kapital (500–1.500 € netto auf 1.600 € eingesetzt — bevor auch nur eine Arbeitsstunde bewertet wird). Hält man diese Rendite konstant, braucht 24.000 €/Jahr **25.000–80.000 € eingesetztes Kapital** — schon über der genannten 20.000-€-Grenze, und das noch bevor die Rendite selbst absinkt.

**Sie sinkt tatsächlich, in eine von zwei Richtungen, und beide zeigen sich in den eigenen Zahlen des Dokuments:**

- **Bei 10–15-€-Einkaufspreisen bleiben, Kapital skalieren.** Bei 25.000 € eingesetzt, 6-Monats-Umschlag, ~12 € durchschnittlicher Einkauf: **~350 Käufe/Monat = ~350 Verkäufe/Monat ≈ 16–17 Pakete/Tag.** Bei 80.000 € sind es ~50/Tag. Das ist kein Solo-Nebenjob mit Software-Unterstützung mehr — das ist ein Vollzeit-Packbetrieb, noch bevor Sourcing, Einstellen, Zustandsbewertung und Reklamationen mitgezählt werden. Das ist die Arbeitszeit-Decke aus *Scale* in v3, und sie entspannt sich mit mehr Kapital nicht — sie wird linear schlimmer.
- **Zu 100-€+-Einkaufspreisen wechseln, um die Paketzahl vernünftig zu halten.** Bei 25.000 € eingesetzt sind ~250 Einheiten bei 6-Monats-Umschlag ein überschaubares ~1,3 Pakete/Tag. Aber nach der eigenen Supply-Cap-These dieses Konzepts sind 100-€+-Figuren genau das Ende mit gedeckeltem Angebot, langer Retirement-Zeit und **dünnem Markt**. Die Marktdaten, die bereits in diesem Dokument stehen, sind unmissverständlich, was "liquide" an diesem Ende bedeutet: Die meistverkaufte Minifigur der *gesamten Plattform*, aufsummiert über alle 17.883 konkurrierenden Shops, bewegt sich **7,7 Mal am Tag**; Rang 20 schafft 2,3/Tag. Der eigene Bestand eines Shops an ein paar Einheiten einer 100-€+-Figur, ein Angebot unter Dutzenden Konkurrenten, dreht sich realistisch in einem Horizont von vielen Monaten bis Jahren — nicht sechs. Die realisierte Rendite auf diesem Weg ist nicht die optimistischen 31–94 %; sie ist unbekannt, vermutlich deutlich niedriger, und die Tätigkeit ist kein Handel mehr — sie ist spekulatives Sammeln mit Gewerbeschein.

**Es gibt außerdem eine harte Decke auf die Gesamtchance, unabhängig vom eigenen Kapital.** [BL Metrics](https://www.blmetrics.com/) verkauft bereits Sourcing-Arbitrage und automatisches Repricing gegen genau diese Datenquelle — und **begrenzt sich bewusst auf 100 Nutzer**. Das ist keine Marketing-Entscheidung — ein Anbieter, der seinen eigenen Umsatz deckelt, sagt damit direkt: Die ausbeutbare Ineffizienz in diesem Datensatz trägt nicht mehr gleichzeitige Nutzer als das. Diesen Ansatz zu skalieren bedeutet nicht, ein größeres Stück von einem wachsenden Kuchen zu bekommen — es bedeutet, härter um einen Anteil an einem Pool zu konkurrieren, den ein Konkurrent bereits vermessen und für klein genug befunden hat, um ihn zu rationieren.

**Wie ein echter Weg zu 24.000 €+/Jahr tatsächlich aussieht:** ein etablierter BrickLink-Shop in echter Einzelhandelsgröße — tausende Angebote, Lagerfläche, Sourcing-Beziehungen (Nachlassauflösungen, Großhandel, aufgelöste Sammlungen), eine mehrjährige Feedback-Historie und realistisch fremde Arbeitskraft für Kommissionierung und Verpackung. Solche Shops existieren und tragen sich. Aber das ist ein **Einzelhandelsgeschäft** — Kapital, Reputation, Arbeit und Jahre sind die entscheidenden Faktoren, nicht Preissignal-Software. Die Recherche fand keinen belastbaren Datensatz zu realisierten Minifiguren-Flipping-Margen auf irgendeiner Skala, und die deutlichste verfügbare Aussage aus erster Hand ist konsistent und unverblümt: es "only pays off if you don't count work hours" (es lohnt sich nur, wenn man die Arbeitsstunden nicht mitzählt). Jede Empfehlung in diesem Konzept, ab Schritt 1, ist auf einen Skript-und-Tabellen-Betrieb zugeschnitten, genau weil diese ehrliche Decke existiert — mehr Software hebt sie nicht an.

**Was sich praktisch ändert:** nichts am nahen Build. Schritt 1 (das Handelsprotokoll) und Schritt 2 (das Bewertungsskript) bleiben unabhängig von dieser Antwort richtig, weil sie auch der billigste Weg sind, herauszufinden, ob selbst die kleine Version ihre Kosten deckt. Was sich ändert, ist die Einordnung von "später": 20.000 €+ ist nicht dieses Konzept hochskaliert — es ist ein anderes, schwereres Geschäft, zu dem die Software dieses Konzepts nur einen kleinen Beitrag leistet, und die Entscheidung dafür sollte als Einzelhandels-Geschäftsentscheidung getroffen werden, nicht als Fortsetzung dieses Werkzeugs.

### Nicht gebaut: der "Market-Squeeze"-Rechner
Die Beispielnotiz schlägt vor, die günstigsten Lots aufzukaufen, um den Boden anzuheben und Sammler ihn zahlen zu lassen. Hier nicht entworfen: sein Zweck ist es, Angebot zu monopolisieren, und es funktioniert ohnehin nicht — BrickLink ist global, Angebot wird durch aufgelöste Sammlungen nachgefüllt, und ein 100-Lot-Orderbuch repariert sich in Wochen, während Kapital brachliegt. Die eine gute Idee aus diesem Abschnitt, **Orderbuchtiefe**, bleibt in Schritt 2 für den umgekehrten Zweck erhalten: zu beurteilen, ob ein günstiges Angebot real ist.

### Verworfene Quellen
**Rebrickable:** "There is no Set/Part pricing data available" ([docs](https://rebrickable.com/api/v3/docs/)). **Brickset:** Minifig-Operationen sind auf die eigene Sammlung des Nutzers beschränkt, und es führt LEGO-*Neupreise*. **BrickOwl:** hat `catalog/price_history`, aber der Zugang ist anfragegebunden, nur GBP, dünner Markt. **eBay/Multi-Marktplatz:** eigenständiges, größeres Projekt; unverifiziert, außerhalb des Umfangs.

---

## ⚠️ Risiken

1. **Der Vorteil wird bereits verkauft — und rationiert.** BL Metrics liefert Sourcing-Arbitrage, regionalen ROI und automatisches Repricing schon heute, und **begrenzt sich bewusst auf 100 Nutzer** ([blmetrics.com](https://www.blmetrics.com/)). Ein Anbieter, der seinen eigenen Umsatz deckelt, gibt damit explizit zu, dass dieses Alpha **mit der Zahl der Leute zerfällt, die es fahren**. Das ist das stärkste Einzelargument gegen die Prämisse, und es ist keine Spekulation — es ist die erklärte Geschäftsentscheidung eines Konkurrenten.
2. **Umschlag ist unterhalb der Katalogspitze brutal.** Die meistverkaufte Minifigur der gesamten Plattform wird ~7,7 Mal pro Tag *weltweit* gehandelt; Rang 20 schafft ~2,3/Tag; unterhalb der Top 50 bewegt sich eine SKU plattformweit eine Handvoll Mal pro *Monat* — bei 17.883 Shops und 6,29 Mio. gelisteten Minifiguren ([browse](https://www.bricklink.com/browse.asp), [sold stats](https://www.bricklink.com/catalogStatsSold.asp?itemType=M&v=0)). Jedes Modell, das annimmt, man kaufe unterbewertet und drehe schnell, kämpft gegen diese Verteilung. Das bestätigt auch den Review-Einwand, dass die Supply-Cap-These *illiquide* Ware selektiert.
3. **Der Price Guide ist strukturell nach unten verzerrt.** Verkaufspreise werden in USD zum historischen Kurs erfasst und zum heutigen zurückgerechnet, und USt ist ausgeklammert — sodass der angezeigte "Durchschnitt" leicht unter dem wahren Markt liegt, und Verkäufer, die sich daran orientieren, ihn weiter nach unten drücken ([BrickStore #80](https://github.com/rgriebl/brickstore/issues/80)). **Ein Algorithmus, der dem Guide mechanisch vertraut, beteiligt sich am Rennen nach unten, statt ihm zu entkommen.** Jede Preisregel muss das bewusst korrigieren.
4. **Repricing hat eine harte Durchsatzgrenze, die sich technisch nicht umgehen lässt.** Es gibt **keinen Bulk-Update-Endpoint** — Repricing ist ein `PUT /inventories/{id}` pro Lot, gegen dasselbe 5.000-Calls/Tag-Kontingent. Bricqer, ein ausgereiftes serverseitiges Produkt, gibt an, dass ein vollständiger Preis-Refresh deshalb "several hours to several days" dauern kann. Hier gibt es keinen Geschwindigkeitsvorteil für irgendjemanden.
5. **Die deutsche Rechtslage ist eine dokumentierte, präzedierte Kostenposition.** BrickLink stellt kein natives Impressum/AGB/Widerrufsbelehrung bereit — Verkäufer bauen das selbst in Freitext-Splash-Seiten ein. Eine Abmahnwelle 2018 hat **~90 von ~800** aktiven deutschen Shops zum Schließen gebracht, mit der Einschätzung, ein vollständig konformer deutscher BrickLink-Shop sei "nahezu unmöglich" ([promobricks](https://www.promobricks.de/bricklink-deutsche-haendler-derzeit-abgemahnt/)). Es existiert ein Abo-Markt allein für diese Texte (**5,90 €/Monat netto**, [IT-Recht Kanzlei](https://www.it-recht-kanzlei.de/Service/agb-BrickLink.php)). Ebenfalls Pflicht: EU-DSA-Selbstzertifizierung ([help #2655](https://www.bricklink.com/help.asp?helpID=2655)), und eine **10.000-€/Jahr**-Schwelle für EU-Fernverkäufe, die eine OSS-Registrierung erzwingt ([help #2550](https://www.bricklink.com/help.asp?helpID=2550)).
6. **Die steuerliche Behandlung ist strukturell, kein Prozentsatz.** **Differenzbesteuerung (§25a UStG)** entscheidet, ob USt auf die *Spanne* oder den *vollen Preis* fällt; allein die Kleinunternehmer-Entscheidung macht ~12 € Unterschied bei einem 75-€-Verkauf. **PStTG/DAC7**-Plattformmeldepflichten greifen früh bei jeder echten Verkaufsrate. **Nicht recherchiert, keine Steuerberatung** — Steuerberater vor dem ersten Verkauf.
7. **Bulk-Lot-Bewertung ist eine Arbeits-Arbitrage, keine Informations-Arbitrage.** Ein Verkäufer, der eine Artikelliste exportieren kann, hat bereits Tools, die gegen denselben Guide bepreisen. Der echte Vorteil ist, dass Bulk-Verkäufer hohe Rabatte für einen schnellen Ausstieg geben, *weil Zerlegen Arbeit ist*. Real, aber die Decke ist die eigene Paketkapazität pro Tag. Erfahrene Verkäufer sind sich hier einig: es "only pays off if you don't count work hours" ([Brickset-Forum](https://forum.brickset.com/discussion/28087/starting-out-selling-on-bricklink-advice-please)).
8. **Summe der Mediane überbewertet ein Lot.** 200 Figuren bei ~40 Verkäufen/Monat sind fünf Monate der gesamten Kapazität für einen Einkauf — und das Einstellen macht *dich* zu den geballten günstigen Lots in genau diesen Figuren. Lot-Bewertung muss liquiditätsgewichtet und selbstwirkungskorrigiert sein.
9. **Es ist ein Job.** Kommissionieren, Zustand bewerten, Verpacken, Versenden, Reklamationen, Feedback. Kein Repricing-Tool berührt irgendetwas davon, und dort gehen die eigentlichen Stunden hin.

**Die eine ehrliche Lücke in diesem Gegenbeweis:** Es wurde kein Erstberichte gefunden, dass jemand API-signalgesteuertes Minifiguren-Flipping versucht und Geld verloren hat. Der Fall oben ist strukturell und hergeleitet — zusammengesetzt aus Plattformdaten, Konkurrenzverhalten und Aussagen benachbarter Verkäufer — nicht aus einem passenden Fehlschlagsbericht. Diese Abwesenheit ist **schwaches Indiz in beide Richtungen** und sollte nicht als Beruhigung gelesen werden.

## 📋 Offene Fragen

1. **Kleinunternehmer oder Regelbesteuerung?** ~12 € Unterschied bei einem 75-€-Verkauf wert — mehr als sämtliche Plattformgebühren zusammen, und mehr als jede Preisoptimierung, die diese Software je liefern könnte. Dazu Differenzbesteuerung (§25a) und PStTG/DAC7. **Steuerberater, vor dem ersten Verkauf.** *(Blockierend, und wichtiger als alles Technische.)*
2. **Was zeigen zehn echte Trades?** Die Take-Rate ist jetzt a-priori bekannt (~6,2 %); unbekannt ist die **realisierte Liegezeit**, und Risiko 2 legt nahe, dass sie deutlich schlechter als 4–9 Monate sein könnte. *(Blockierend — aber es ist Handeln, kein Bauen.)*
3. **Seller-Upgrade — jetzt beginnen.** Erfordert einen Kauf mit positivem Feedback, dann Ausweis- + Geschäftsadress- + Bestandsnachweis, dann **bis zu zwei Wochen oder länger** manuelle Prüfung ([help #2440](https://www.bricklink.com/help.asp?helpID=2440)). Reine Kalenderzeit — parallel zu allem anderen starten.
4. **Wird `price_detail[]` bei umsatzstarken Figuren abgeschnitten?** Ein Check beim ersten Live-Call, siehe *Korrekturen*.
5. ~~**Gibt es einen realistischen Weg, über 20.000 € hinaus zu ernsthaftem Einkommen zu skalieren?**~~ ✅ **Gelöst: nein**, nicht über diesen Mechanismus — siehe *Der 20.000-€-Widerspruch*. Was noch deine Entscheidung ist: ob du das andere, schwerere Geschäft (echte Einzelhandelsgröße) verfolgen willst, das diese Frage aufdeckt, unabhängig von diesem Konzept.
6. **Was sagt das Handelsprotokoll über den Engpass?** Bestimmt Schritt 3. Bewusst unbeantwortet.

7. **Stripe statt PayPal?** Spart ~1,3 Prozentpunkte vom Brutto (~8 % der Nettomarge). Vorher Unterschiede bei Chargeback und Käuferschutz prüfen.

**Gelöst:** ~~erlaubt BrickLink automatisiertes Repricing~~ → **ja**, die API-ToS enthält keine Klausel gegen algorithmische Preisgestaltung, und "reasonable commercial uses of the API are permitted" · ~~US-Cross-Region-Arbitrage~~ → **gestrichen**, der Kanal ist strukturell geschlossen · ~~Hobby oder Handel~~ → Handel · ~~wie viel Kapital~~ → 2.000 € → 20.000 €+ · ~~welche Serien tracken~~ → hinfällig, der Sweep ist gestrichen · ~~rendert das Registrierungsformular~~ → ja, aber das klärt weniger als v3 behauptete
