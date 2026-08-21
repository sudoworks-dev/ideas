Das ist ein Beispiel und ein für eure geplante Applikation.

Die Minifigur *sw0181 (Starkiller / Galen Marek - Darth Vader's Apprentice)* hat perfekte Eigenschaften für eine Arbitrage- und Squeeze-Strategie: Sie stammt aus dem Jahr 2008, kam in exakt einem einzigen Set vor (7672 Rogue Shadow), das Set ist seit über 15 Jahren "End of Life" (EOL) und die Figur hat eine extrem starke Fangemeinde (Star Wars: The Force Unleashed). Da LEGO diese Form der Figur nie wieder aufgelegt hat, ist das Angebot auf dem Markt absolut limitiert (Hard Cap).

So würde "Project Minifig-Alpha" (unsere spezifizierte MVP-Anwendung) diese Figur analysieren und konkrete Kaufempfehlungen ausgeben, um Geld zu verdienen:

### 1. Das Output-Dashboard für sw0181 (Simulierte Daten)

Eure Applikation zieht sich die Marktdaten von Bricklink, eBay und anderen Plattformen und normalisiert sie:

* *Globaler Durchschnittspreis (Verkauft, 6 Monate):* Gebraucht ca. 65 € - 70 € | Neu ca. 95 € - 105 €
* *Aktuelles Orderbuch (Angebote Weltweit):* ca. 100 Lots (relativ illiquider Markt, was gut für uns ist).
* *Liquiditäts-Status:* Hoch (wird regelmäßig gekauft, da sehr beliebt).

---

### 2. Strategie A: Cross-Border Arbitrage (Der schnelle Profit)

Eure App screent permanent die Preisdifferenzen zwischen verschiedenen Marktplätzen und Regionen.

* *Die Chance:* Auf eBay.de oder bei lokalen europäischen Bricklink-Händlern taucht die Figur von Privatpersonen oder unwissenden Verkäufern aktuell immer mal wieder für *39 € bis 50 € (Gebraucht)* auf. In den USA liegt der Bodenpreis (Floor Price) für diese Figur auf eBay/Bricklink jedoch oft bei *85 $bis 100$*.
* *Der App-Alert:* "Kaufe Listing X in Deutschland für 45 €. Verkaufspotenzial im US-Markt oder auf globalem Bricklink-Store für 75 €."
* *Die Umsetzung:* Ihr nutzt euer bestehendes WWS und Versand-Setup. Ihr kauft die Figur lokal auf, packt sie ins Lager und listet sie direkt für 75 € international. Nach Abzug von Plattformgebühren und Briefporto (internationaler Großbrief für Minifiguren ist sehr günstig) bleibt eine sofortige, risikoarme *Marge von 20-30%*.

### 3. Strategie B: Der "Market Squeeze" (Verknappung erzwingen)

Hier entfaltet das Algo-Trading der App seine volle Kraft. Die App berechnet die "Order Book Depth" (Auftragsbuchtiefe).

* *Die Analyse:* Eure App analysiert das Bricklink-Orderbuch für "Gebraucht - Europa".
* *Das Szenario:* Nehmen wir an, es gibt europaweit 30 Angebote für den "Starkiller" im Zustand gebraucht. Die Preise staffeln sich so:
* 5 Stück zwischen 45 € - 50 €
* 7 Stück zwischen 51 € - 59 €
* Restliche 18 Stück: > 65 €


* *Der Squeeze-Rechner in der App:* Die Anwendung berechnet: "Es kostet exakt 635 €, um die günstigsten 12 Figuren (alles unter 60 €) vom europäischen Markt aufzukaufen."
* *Die Ausführung:* Ihr kauft per Klick alle 12 günstigen Figuren auf. *Damit habt ihr den "Floor Price" (den günstigsten Einstiegspreis für Käufer) über Nacht künstlich auf 65 € angehoben.* Da die Figur beliebt ist und es keinen Nachschub von LEGO gibt, müssen Sammler diesen neuen Preis zahlen.
* *Der Profit:* Ihr listet eure neu erworbenen 12 Figuren über die nächsten Wochen tröpfchenweise aus eurem Lager für 64,95 € – 68,00 €. Das Kapital war nur kurz gebunden, und ihr habt den Marktpreis diktiert, weil ihr das Angebot kontrolliert habt.

### 4. Strategie C: Algorithmic Repricing (Den eigenen Bestand optimieren)

Angenommen, ihr habt durch die Squeeze-Strategie bereits 5 Starkiller-Figuren im Lager, die ihr für 65 € listet.
Eure App merkt über die Supply/Demand Zeitreihenanalyse, dass das weltweite Angebot in den letzten 4 Wochen um 20% geschrumpft ist (weil Sammler gekauft haben, aber keine neuen Händler gelistet haben).

* *Die Automatisierung:* Statt die 65 € stehen zu lassen, schickt die App einen Befehl an euer WWS: "Angebot verknappt sich, Nachfrage konstant. Erhöhe den Preis für sw0181 im eigenen Bestand sofort auf 72 €."
* *Ergebnis:* Ihr verkauft vielleicht 2 Tage später als vorher, nehmt aber die maximale Marge mit, weil die App den Markttrend in Echtzeit verstanden hat.

---

### Warum euer geplantes System hier so überlegen ist:

Ein normaler LEGO-Händler macht das aus dem "Bauchgefühl" heraus oder schaut einmal im Monat in die Bricklink-Preislisten. Er sieht das große Ganze nicht.

Eure "Project Minifig-Alpha" Applikation macht das *systematisch, in Echtzeit und für zehntausende Figuren gleichzeitig*. Ihr bindet Kapital nur dort, wo die App durch harte Mathematik (Order Book Analysis) bewiesen hat, dass der Markt sich durch ein definiertes Budget leer kaufen ("squeezen") lässt oder ein sofortiges Arbitrage-Gefälle zwischen zwei Ländern besteht.

Bei sw0181 würde das System heute definitiv ein "Buy" Signal generieren, sobald der Preis in Europa unter ~52 € fällt.