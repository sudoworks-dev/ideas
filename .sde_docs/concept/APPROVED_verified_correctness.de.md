# 💡 Konzept: Verifizierte Korrektheit — und die Randbedingungen, die sie getötet haben

> Deutsche Fassung von `verified_correctness.md`. Bei Abweichungen gilt die englische Datei als Original.

## 📌 Status

`DRAFT` · **v2** — v1 empfahl eine Shopify-App zur Behebung von Barrierefreiheitsmängeln. Eine unabhängige Widerlegung gab **`BLOCK`** auf Primärquellen zurück, und der Einwand hielt vollständig. v2 **streicht** diese Form, hält fest warum, und berichtet den Befund, der sie überlebt: **die Randbedingungen sind überbestimmt — und genau das ist jetzt die Entscheidung.**

| Feld | Wert |
|---|---|
| Erstellt | 2026-08-29 |
| Folgt auf | `APPROVED_weg_business_strategy.md` (Ast B) |
| Team | 2–3 Personen, KI-/Agentic-Engineering · **kein Branchenzugang, keine Reichweite, kein Kapital** |
| Ziel | €8k MRR ≈ $9k · Services <20% der Teamzeit |
| **Entscheidung** | **Gabel C gewählt** (Nutzer, 2026-08-29) — €8k MRR ist eine **Etappe, kein Boden**. Erstes Ziel **€2–3k MRR** |
| Recherche | 6 Domänen-/Belegungspässe + 1 adversarialer Pass |
| Adversarial Review | **`BLOCK`** — aufgelöst durch **Streichung**. Der Reviewer holte drei direkte Wettbewerber und Shopifys eigene API-Scope-Regel aus Primärquellen, die der Autor nie geöffnet hatte |
| Reviewer-Unabhängigkeit | **`same-model-fallback`** — sechste Runde. Der Reviewer benennt die Kosten diesmal konkret: *„der blinde Fleck des Autors war, die App-Store-Seite nicht zu öffnen"*, und ein gleichmodelliger Prüfer *„teilt die Neigung des Autors, delegierten Zusammenfassungen mehr zu trauen als der Primärabfrage"* |

---

## ⚖️ Verdikt

**Keine Form überlebt. Aber diese Runde ist nicht auf neue Weise gescheitert — sie ist identisch gescheitert, und genau das ist das Ergebnis.**

> **Vier Runden, rund fünfzehn Formen, ein wiederkehrender Mechanismus: der automatisierbare Teil der Arbeit ist bereits gratis, der wertvolle Teil braucht einen Menschen. Jede Form läuft damit auf ein Dienstleistungsgeschäft hinaus — und ein Dienstleistungsgeschäft verletzt die 20%-Grenze.**

Das ist kein Pech in vier unabhängigen Domänen. Es ist das, was diese Randbedingungen erzeugen. **€8k MRR + Services unter 20% + keine Reichweite + kein Zugang + kein Kapital** ist mit hoher Wahrscheinlichkeit überbestimmt, und der ehrliche nächste Zug ist keine fünfte Domäne, sondern die Entscheidung, welche Randbedingung sich ändert.

**Der Nutzer hat Gabel C gewählt** (2026-08-29): €8k als gestufte Etappe, erstes Ziel €2–3k MRR. Die eigentliche Wirkung ist nicht arithmetisch — siehe § *Was Gabel C wirklich verändert*.

---

## 🎯 Problemstellung

Für 2–3 KI-Entwickler ohne Branchenzugang, ohne Reichweite und ohne Kapital: Welche Domäne erlaubt ein monetarisierbares Produkt, bei dem der Käufer kein Vertrauen braucht, der Preis nicht kollabiert und Zuverlässigkeits-Engineering der knappe Input ist?

---

## ✅ Was diese Runde belegt hat und was Bestand hat

Diese Befunde haben die Widerlegung überstanden und sind domänenunabhängig wiederverwendbar.

**1. Der knappe Input ist Zuverlässigkeits-Engineering — Filter 3 ist beantwortet.** 57% der Organisationen betreiben Agenten in Produktion; **89% haben Observability, aber nur 52% haben Evaluations**, und „Qualität" ist mit 32% die meistgenannte Deployment-Hürde (LangChain, *State of Agent Engineering 2026*). **95% der GenAI-Pilotprojekte in Unternehmen erzeugen keinen P&L-Effekt, und eingekaufte Systeme gelingen doppelt so oft wie selbstgebaute** (MIT NANDA: 52 Interviews, 153 Führungskräfte, 300 Deployments). KI-Kompetenzen sind die am schwersten zu besetzende Kategorie — ~1,6M offene Stellen gegen ~518k Qualifizierte, bei 56% Gehaltsaufschlag gegenüber 25% im Vorjahr (ManpowerGroup 2026, 39.063 Arbeitgeber; PwC, ~1 Mrd. Stellenanzeigen). Modellzugang ist eine API, Prompting ist nicht knapp; die Lücke zwischen 89% und 52% ist es.

**2. Das KI-Tötungsmuster.** Keine eigenen Daten, kein Workflow-Lock-in, und **der Preis ist die Marge zwischen API-Kosten und Aufschlag**. Opfer: die Wrapper-Kohorte, „ChatGPT für PDFs" (nativer Datei-Upload, Nov 2023), KI-Budget-Apps (Mai 2026), RAG-Middleware (Assistants API). Gemessen: **Jasper fiel von ~$120M auf $55–88M**, nachdem ChatGPT seine $29-Untergrenze unterbot. Überlebende halten etwas anderes — Abridge ($5,3 Mrd., $100M ARR, 250+ Kliniksysteme) über die Integration in die Patientenakte; Granola, indem es nach dem öffentlichen Sherlocking zur Datenschicht wurde, die andere Werkzeuge abfragen.

**3. Verifikation wird tatsächlich getrennt von Erzeugung verkauft** — Stanford fand, dass die von LexisNexis und Thomson Reuters als *„hallucination-free"* beworbenen Werkzeuge **in 17–33% der Fälle halluzinieren**, woraufhin ein Markt reiner Prüfprodukte entstand. Die Vorlage ist real. **Falsch war an v1 nicht die Vorlage, sondern wo sie angewandt wurde.**

**4. Beide akzeptierten Käufertypen sind schlechter, als sie aussehen.**
- **Entwickler:** Es existiert kein belegter Fall, in dem ein 2–3-Personen-Team ohne Reichweite in unter ~12 Monaten $8–10k MRR self-serve erreicht hat. Jeder schnelle Fall hatte vorhandenes Publikum (ShipFast: 95k Twitter + 20k Newsletter). Die publikumsfreien Gewinner — Plausible, Honeybadger — brauchten **18–24+ Monate**. Churn unter $300k ARR: 6,5%/Monat (ChartMogul).
- **Prosumer:** hohe Zahlungsbereitschaft nur dort, wo das Werkzeug am Einkommen oder an Regulierung hängt (SimplePractice $49–99/Monat; Clio $49–149/Nutzer, $500M ARR). Aber: **nur ~10% der Monatszahler erreichen Jahr 2, 56–72% der Jahresabos kündigen im ersten Jahr**, und unter $20k MRR scheitern 8–12% der Abbuchungen pro Zyklus (RevenueCat, 75–115k Apps).

**5. Distribution hat genau eine mietbare Antwort — und sie kostet in einer anderen Währung.** Der **Shopify App Store** ist das einzige Ökosystem mit wiederholten Belegen für Kleinteams bei $5–50k MRR, 0% Rev-Share bis $1M Lebenszeit, und einer Discovery, die ohne Publikum funktioniert. Aber: **Median-App unter $1k MRR, nur ~0,18% der Entwickler über $1M/Jahr, und $5–50k MRR ist das oberste Dezil einer Kategorie.** Neue Apps brauchen **10+ Bewertungen in 30 Tagen**, um überhaupt zu erscheinen; ~60% der Installs kommen aus der internen Suche; Shopify verkauft Anzeigen über der organischen Ebene. Alles andere fiel durch — Chrome Web Store (~70% verdienen ~$0), App Store (>90% des Umsatzes an das oberste 1%), Steam (Median-Launch 2026 ~$350 lifetime), **ChatGPT- und Claude-Verzeichnisse (2026 kein Bezahlweg)**. Und SEO ist kein Kaltstartkanal mehr: **−58% CTR auf Platz 1**, wo AI Overviews erscheinen (Ahrefs, 300k Keywords), gegenüber −34,5% ein Jahr zuvor.

---

## 🗑️ Was vorgeschlagen und gestrichen wurde

v1 empfahl eine **Shopify-App, die Barrierefreiheitsmängel auf Theme-Code-Ebene behebt, positioniert gegen die Overlay-Kategorie, die die FTC gerade sanktioniert hatte** ($1M-Verfügung gegen accessiBe, April 2025, mit dauerhaftem Verbot unbelegter Konformitätsbehauptungen). Fünf Befunde haben sie getötet, jeder aus einer Primärquelle, die der Autor nie geöffnet hatte.

**1. Die Kategorie ist mit exakt dieser Positionierung besetzt.** Shopifys Accessibility-Kategorie umfasst **129 Apps**, darunter drei direkte Nicht-Overlay-Wettbewerber:

| App | Start | Preis | Ihre eigenen Worte |
|---|---|---|---|
| **Patrol** | Dez 2024 | Gratis / **$200/Mon.** | *„is not an overlay widget. Our product resolves ADA violations in a merchant's theme files or directly in Github"* |
| **TestParty** | Jun 2025 | Gratis / **$599/Mon.** | *„Fix ADA & WCAG violations in two weeks. Source code fixes, no overlays"* |
| **EnableAll** | Nov 2025 | Gratis / $49 / $149 / **$399** · Built for Shopify | *„Go beyond traditional accessibility overlays with automated Code-Fix technology"* |

Dazu ~10 Audit-/Scanner-Apps und ~25 Alt-Text-Apps — **die meisten kostenlos**, angeführt von AltKing (167 Bewertungen, gratis, Built for Shopify). Alt-Text ist die größte automatisierbare Fehlerklasse; Kontrast, die zweitgrößte, ist eine Theme-Einstellung. Zieht man beide ab, ist der automatisierbare *und* unbesetzte Rest dünn.

**2. Der Mechanismus ist von der Plattform gesperrt, und der erlaubte Weg ist das Anti-Ziel.** Shopifys eigene Doku: Asset-`PUT`/`DEL` erfordert den `write_themes`-Scope, und eine App-Store-App *„needs to be **granted an exemption by Shopify**."* Barrierefreiheit steht **nicht** auf der Berechtigungsliste — während *„Editing a CSS class or adding attributes to an existing theme element"* ausdrücklich als **nicht berechtigt** geführt wird, mit der empfohlenen Alternative: Theme App Embeds, die *„load scripts to target specific elements of the page."* **Shopifys sanktionierter Weg für den Kernvorgang des Produkts ist Laufzeit-DOM-Manipulation — strukturell das, was ein Overlay tut.** Bezeichnend: EnableAlls Listing weist nur *lesenden* Theme-Zugriff aus, während es Code-Fixes an der Quelle bewirbt — das Unterscheidungsmerkmal wird also bereits von einem Anbieter behauptet, der es technisch nicht leisten kann, und kein Käufer kann es erkennen.

**3. „Der Käufer prüft ohne Vertrauen" — die ganze Existenzberechtigung des Konzepts — ist falsch.** **Ein Overlay besteht denselben axe-/Lighthouse-Test**; dafür existieren Overlays. Das kostenlose Werkzeug kann das Produkt nicht von der sanktionierten Kategorie unterscheiden, also ist die eine Behauptung, auf die es ankommt, genau die, die es nicht entscheiden kann. Empirisch prüfen Händler nicht: Auf Shopify steht UserWay bei **2,6★ (10 Bewertungen)**, accessiBe bei 3,9★ (16), während **kostenlose Widgets die Kategorie anführen** (Avada, 293 Bewertungen, 5,0). Würde Prüfbarkeit den Kauf steuern, wäre die Rangfolge umgekehrt.

**4. Die 20%-Grenze ist durch offenbartes Verhalten widerlegt, nicht bloß ungeprüft.** Alle drei Wettbewerber sind unabhängig bei Retainer-plus-Mensch gelandet: Patrol-Kunden beschreiben *„monthly meetings"* und bezahlen *„their developers"* für das, was die KI nicht kann; TestParty verkauft *„monthly manual audits (screen reader, keyboard, zoom)"*; EnableAlls Stufen $149 und $399 sind ausdrücklich **manuelle** Prüfung und Behebung. Drei Anbieter, drei Preispunkte, eine Antwort.

**5. Die „entscheidende Unbekannte" fällt gegen das Konzept aus — und war vor der Empfehlung beantwortbar.** Shopifys **Theme-Store-Anforderungen** sind eine harte Zulassungshürde für jedes gelistete Theme: Lighthouse-Accessibility ≥90 über Home/Produkt/Kollektion auf Desktop und Mobil, volle Tastaturbedienbarkeit, sichtbarer Fokus, `alt` über `image.alt`, Label-Input-Zuordnung, 4,5:1 und 3:1 Kontrast, **Fokus-Reihenfolge = DOM-Reihenfolge**, und **24×24 px Touchziele — WCAG 2.2 AA SC 2.5.8**. Das ist nahezu eine Aufzählung der maschinell erkennbaren Defekte, die das Produkt verkaufen wollte, bereits bei der Theme-Zulassung ausgeräumt. Die Restlücke zu vollem WCAG 2.2 AA besteht genau aus den urteilsabhängigen Kriterien, die sich nicht automatisieren lassen — weshalb alle drei Etablierten einen monatlichen Menschen mitverkaufen.

> **Und das Prozessversagen muss klar benannt werden, weil es sich wiederholt hat.** Die Vorrunde wurde blockiert, weil eine Kategorie empfohlen wurde, ohne zu prüfen, wer sie bereits bedient. v1 führte diese Prüfung hier für den *verworfenen* Kandidaten durch, ließ sie beim *empfohlenen* aus — und behauptete im Dokument, die Lektion sei angewandt worden. Anschließend zitierte es **testparty.ai**, einen direkten Wettbewerber mit $599/Monat auf demselben Kanal, als neutrale Quelle für Marktstatistiken, lediglich als „anbieternah" markiert. Zweimal hintereinander dieselbe Fehlerklasse, beim zweiten Mal unter der Behauptung, sie vermieden zu haben.

---

## 🧩 Der Befund, der die Form überlebt

Die Skopus-Analyse der Widerlegung hat etwas Allgemeines hervorgebracht, und es ist der nützlichste Ertrag dieser Runde:

> **Jeder Schnitt, der die Services-Grenze rettet, löscht die Eigenschaft, die die Problemstellung verlangt; und jeder Teil, der die Problemstellung erfüllt, reißt die Grenze.**

Nimmt man das Barrierefreiheitsprodukt auf reines Audit und Monitoring zurück, verschwindet die Dienstleistungslast — aber auch das Produkt: das ist die *kostenlose* Stufe der Wettbewerber, und Zuverlässigkeits-Engineering hört auf, der knappe Input zu sein. Behält man die Behebung, kehrt der Mensch zurück. **Die beiden Anforderungen schließen sich in dieser Domäne gegenseitig aus — und derselbe Ausschluss hat die drei Vorrunden getötet.** Daraus ein fünfter Filter, erarbeitet statt angenommen:

> ### Filter 5
> **In jeder Domäne, in der Korrektheit von menschlichem Urteil abhängt, ist der automatisierbare Anteil genau der kommoditisierte Anteil.** Erkennung ist gratis, weil sie mechanisch ist; der Rest ist wertvoll, *weil* er Urteil braucht — und Urteil ist eine Person, also ein Dienstleistungsgeschäft. **Sucht kein Produkt im Rest.**

Vier Runden sagen inzwischen dasselbe aus vier Richtungen. **Ein Produkt für ein Team, das keine Dienstleistung verkaufen kann, niemanden erreicht und kein Kapital hat, muss eines sein, bei dem der maschinell prüfbare Teil selbst der ganze Wert ist — nicht die billige Hälfte davon.**

---

## 🔀 Die Gabel

Die Randbedingungen sind überbestimmt. Drei Lockerungen standen zur Wahl; sie sind nicht gleichwertig.

### A · Die 20%-Services-Grenze fallen lassen · *nicht gewählt*
Öffnet den Objektbuchhaltungs-Ast der Vorrunde und diese Runde als Anbieter Nr. 4 gegen Patrol, TestParty und EnableAll. **Ehrliche Lesart:** Der zweite ist schlechter als der erste. Wären Dienstleistungen akzeptabel, wäre die frühere § 28-Jahresabrechnung zu €500–900 pro Objekt und Jahr die stärkere Form — und sie steht noch.

### B · Das fehlende Gut beschaffen statt eine Bedingung lockern · *nicht gewählt, aber nicht ausgeschlossen*
Jeder schnelle Gewinner der Recherche hatte das eine, was dem Team fehlt, und es ist der einzige fehlende Input, der sich herstellen statt kaufen lässt: **Reichweite.** ShipFast erreichte $250k in fünf Monaten auf 95k Twitter-Followern und 20k Newsletter-Abonnenten, die vorher aufgebaut wurden; Photo AIs $132k MRR liefen auf Pieter Levels' bestehender Reichweite — die Recherche markierte das ausdrücklich als **keinen** Beleg für einen Start ohne Publikum. Die publikumsfreien Gewinner, Plausible und Honeybadger, setzten stattdessen **18–24 Monate** Kompoundierung ein. *Ehrliche Kosten:* Es ist Publizieren, nicht Entwickeln, und es zahlt nichts, solange es läuft.

### C · €8k als Etappe statt als Boden behandeln · **GEWÄHLT**
Ein erstes Ziel von €2–3k MRR öffnet Mikronischen, die €8k allein durch Arithmetik schließt. Der Nutzer hat es als gestuft und nicht als reduziert gerahmt — die Lesart, unter der es keine bloße Vertagung ist.

---

## 🎚️ Was Gabel C wirklich verändert

Die naheliegende Lesart — ein kleineres Ziel braucht weniger Kunden — stimmt und ist der uninteressanteste Teil.

| Ziel | bei $29/Mon. | bei $49/Mon. | bei $99/Mon. |
|---|---|---|---|
| €2–3k MRR (≈$2,2–3,3k) | 76–114 | 45–67 | **22–33** |
| €8k MRR (≈$9k) | 310 | 184 | 91 |

**Die eigentliche Wirkung ist, dass sich ändert, welche Wettbewerber überhaupt auftauchen.**

- **Auf Shopify ist $2–3k MRR etwa oberes Quartil statt oberstes Dezil.** Die 90.-Perzentil-Anforderung, die die Arithmetik in Runde 4 so hart machte, war eine Funktion des Ziels, nicht der Plattform.
- **Eine Nische mit €30k Jahresumsatz ist für einen finanzierten Wettbewerber unsichtbar.** Jeder Etablierte, der in vier Runden eine Form geschlossen hat — Buena ($58M), Matera (~€55M), dotega, TestParty, Patrol, EnableAll — braucht einen um eine Größenordnung größeren Markt, damit sich der Eintritt lohnt. **Der Wettbewerbersatz aus Runde 4 wurde ebenso sehr von der Größe des Ziels gezogen wie von der Wahl der Domäne.** Das ist der erste strukturelle Vorteil, den das Team geschenkt bekommt, statt ihn aufbauen zu müssen.
- **Filter 5 gilt weiter, und C hebt ihn nicht auf.** C macht eine Nische tragfähig, in der die *ganze* maschinell prüfbare Aufgabe der Wert ist — nicht die billige Hälfte einer urteilsabhängigen. **Klein und vollständig schlägt groß und Restposten.** Das ist ab jetzt die Suchspezifikation.
- **An der Distribution ändert C nichts.** Es senkt die Latte, liefert aber kein Publikum. Gabel B bleibt verfügbar und schließt C nicht aus — ein kleineres Ziel macht schlicht ein kleineres Publikum ausreichend.

---

## ✅ Empfehlung

1. **Die Gabel ist entschieden: C.** Der nächste Konzeptlauf sucht unter einem ersten Ziel von €2–3k MRR, und seine Spezifikation ist Filter 5, positiv gelesen — **finde eine Aufgabe, die vollständig maschinell prüfbar ist, klein genug, dass kein finanzierter Wettbewerber sie will, und bepreist nach dem, was ein Fehler kostet.** Nicht den Rest einer urteilsabhängigen Aufgabe.
2. **Nicht die Runde-4-Suche unter einer kleineren Zahl wiederholen.** Barrierefreiheit, Feeds und die Immobiliendomäne sind über Belegung und Mechanismus geschlossen, nicht über die Zielgröße.
3. **Erste Handlung ist Primärabfrage, nicht delegierte Recherche.** Zwei aufeinanderfolgende Blocks entstanden daraus, Zusammenfassungen zu trauen, statt die Seite zu öffnen. Die entscheidenden Fakten dieser Runde standen auf einer öffentlichen App-Store-Seite und in Shopifys eigener API-Doku — beide kostenlos, beide Minuten entfernt, keine geöffnet. **In der nächsten Runde wird die Belegungsprüfung für die *empfohlene* Form von Hand gemacht, zuerst, bevor die Form aufgeschrieben wird.**
4. **Gabel B bleibt auf dem Tisch.** Ein €2–3k-Ziel macht ein bescheidenes Publikum ausreichend, C und B ergänzen sich also, statt zu konkurrieren.

---

## 📋 Offene Fragen

1. ~~**Welche Gabel?**~~ **Beantwortet (Nutzer, 2026-08-29): C.** €8k ist eine gestufte Etappe; erstes Ziel €2–3k MRR.
2. ~~**Ist €8k ein Boden oder eine Etappe?**~~ **Beantwortet: eine Etappe.** In den Runden 1–4 wurde es durchgehend als Boden behandelt, was jeden Wettbewerbersatz stillschweigend aufgebläht hat.
3. **Welche Nische kommt als Nächstes, unter Filter 5 positiv gelesen?** Offen, und Gegenstand des nächsten `/sde-concept`-Laufs.
4. **Soll Gabel B parallel laufen?** Ein €2–3k-Ziel macht ein kleines Publikum ausreichend; beides ergänzt sich. Nicht entschieden.
5. **`reviewer_model` setzen** in `.sde_docs/config`. Sechs Runden `same-model-fallback`, und diese Runde benennt die konkreten Kosten: ein gleichmodelliger Prüfer teilt die Neigung des Autors, delegierten Zusammenfassungen mehr zu trauen als Primärquellen — genau das Versagen, das geprüft wurde.

---

> **Begrenzte Negativa.**
> - **Der Autor hat in dieser Runde nichts erstverifiziert.** Jede obige Streichung beruht auf der Primärabfrage des Reviewers — Shopify-Listings und Shopifys eigene API-Dokumentation — was stärkere Evidenz ist als das Dokument, das sie umstößt.
> - **Die ADA-Klagezahlen (3.117 Klagen 2025, +27%, 22,64% auf Overlay-Seiten) bleiben unverifiziert**, und eine der beiden dafür zitierten Quellen ist ein direkter Wettbewerber. Der Reviewer erreichte keine neutrale Quelle (Seyfarth, UsableNet), bevor sein Budget erschöpft war. **Diese Zahlen nicht wiederverwenden.**
> - **Innerhalb dieser Runde korrigiert:** Shopifys 0%-Band ist eine einmalige Lebenszeit-Freigrenze von $1M, kein jährlicher Reset; „~$93k durchschnittlicher Entwicklerumsatz" ist ein von Gewinnern verzerrter Mittelwert gegen einen Median unter $1k MRR.
> - **Der deutsche BFSG-Winkel ist der schwächere, nicht der stärkere** — 14 Monate nach dem Stichtag 28. Juni 2025, bei Bußgeldern bis €100.000 nach § 37, ließ sich **keine Sanktion, kein Bußgeldbescheid und keine Untersagung finden**, und die Behauptungen „Behörden beginnen im Q3 2026 zu scannen" stammen aus Marketing-Blogs von Anbietern. Die Kleinstunternehmer-Ausnahme (<10 Mitarbeiter **und** ≤€2M, nur Dienstleistungen) nimmt das untere Ende heraus.
> - **Die Angabe „~30–40% der WCAG-Verstöße sind automatisch erkennbar" ist Branchenkonsens, keine gemessene Studie** — und die Widerlegung hat gezeigt, dass sie das Produkt deckelt, statt es zu begründen.
> - `.sde_docs/config` fehlt — läuft auf Defaults.
