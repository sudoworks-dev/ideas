# 💡 Konzept: „Einfache Belegverwaltung für die E-Rechnungspflicht" — Wirtschaftlichkeitsbewertung

> Deutsche Fassung von `DRAFT_belegverwaltung_produktvision.md`. Bei Abweichungen gilt die englische Fassung als SDE-Artefakt.

## 📌 Status

`DRAFT` · **v2** — v1 wurde vom Adversarial Review an fünf quantitativen Punkten widerlegt und hier neu geschrieben, nicht geflickt. **Das weitreichende Urteil aus v1 ist zurückgezogen.**

| Feld | Wert |
|---|---|
| Erstellt | 2026-08-28 |
| Quelle | `.sde_docs/context/ebill_produktvision_2026-08.md` — Gründerdokument, *„Interne Diskussionsgrundlage, Stand August 2026"* |
| Verwandt | `DRAFT_erechnung_monetization.md` v3 bewertete eine **andere, frühere** Spezifikation und ergab NEIN. Hier als **neu herzuleitende Vorannahme** behandelt, **nicht** als Beweis |
| Frage | *„Lässt sich diese Idee monetarisieren und lohnt sich somit das Bauen?"* — ausdrücklich über ein Hobbyprojekt hinaus |
| Team | 2–3 Personen, starker Software- und Agentic-Dev-Hintergrund, **keine Distribution** |
| Geprüfte Ziele | **(A) €4–8k MRR** — spürbares Nebeneinkommen / **ein Gehalt** · **(B) €25k MRR** — Lebensunterhalt für drei |
| Recherche | 4 delegierte Pässe, ~273 Tool-Calls. Rechnungsradar + DATEV-Preise **selbst verifiziert**; Rest subagent-belegt mit URL |
| Adversarial Review | **`REVISE`** — 12 Widerlegungen, 5 davon urteilsverändernd. Alle unten aufgelöst, vier **durch Streichung**. Reviewer: **`same-model-fallback`** |
| **Urteil** | **NEIN zur Vision wie geschrieben** (hohe Konfidenz) · **Weitreichende Aussage „gar nicht in E-Rechnung einsteigen" zurückgezogen** — eine Ausprägung überlebt und wurde nie geprüft |

> ⚠️ **Vor den Befunden lesen.** Der Reviewer lief auf **demselben Modell wie ich**, weil `.sde_docs/config` fehlt und kein `reviewer_model` gesetzt ist. Das ist die **zweite Runde in Folge** ohne wirklich unabhängige Prüfung. Er hat trotzdem fünf echte Fehler gefunden — aber er teilt einen realen Teil meiner blinden Flecken. Gewichte das Dokument entsprechend. `/sde-status` kann die Config anlegen.

---

## 🎯 Problemstellung

**Kann ein 2–3-Personen-Team ohne Distribution eine einfache E-Rechnungs-/Belegverwaltungs-SaaS für Vereine, selbstverwaltete WEGs und Kleinstbetriebe über Hobbyniveau hinaus monetarisieren — im deutschen Markt des August 2026?**

Die Vision ist strategisch gut gedacht: Sie erkennt richtig, dass das generische Produkt besetzt ist, verengt auf Segmente, die Platzhirsche ignorieren, und benennt einen konkreten Differenzierer. **Drei ihrer Tatsachenprämissen sind dennoch falsch — jede in unter einer Stunde prüfbar.**

---

## 🔁 Was der Adversarial Review geändert hat — offen benannt

Ich halte das fest, weil die Korrekturen **gegen meine eigene v1-Schlussfolgerung** laufen. Wer nur v2 liest, wüsste nicht, wie knapp v1 daran vorbeigeschrammt ist, selbstbewusst falsch zu sein.

| v1 behauptete | Korrigiert |
|---|---|
| „€9 ist der Preis, bei dem dieser Markt clearing hat" | **Falsch.** v1 zitierte selbstverwalten.com mit *„€8,16–€20,07 **pro Einheit** pro Monat"* — und rechnete dann mit €9 als **Organisations-ARPU**. Eine 10-Einheiten-WEG zahlt **€82–€201/Monat**. Faktor bis 14, immer zugunsten des Urteils |
| „€25k ist arithmetisch geschlossen" | **Zurückgezogen.** Bei korrigierten Preisen sind €25k ≈ **197–306 WEGs von ~43.000** = 0,5–0,7% Marktanteil. Ein hartes Vertriebsproblem, keine arithmetische Unmöglichkeit |
| „Die Kategorie hat eine Preisobergrenze von null" | **Falsch.** DATEVs €0 und das BMF-*„ein E-Mail-Postfach genügt"* decken **nur Empfang/Transport**. **GoBD-Archivierung** — die vierte MVP-Funktion — liefert niemand kostenlos |
| Vereins-Churn-Multiplikator ~4,2%/Mon. | **Gestrichen.** Unbelegt, meine eigene Konstruktion, in keiner Tabelle verwendet, und kausal falsch — Vertragspartner ist der *Verein*, nicht der Kassenwart |
| vermieter1s €449-Lifetime-Deal „sollte die Diskussion beenden" | **Falsch herum gelesen.** Derselbe Anbieter verkauft daneben €9,90/Monat. €449 ÷ €9,90 = **45 Monate** — Beleg für *höhere* Zahlungsbereitschaft, nicht niedrigere |
| „Zweite unabhängige Bewertung" | **Zurückgezogen.** Gleicher Autor, gleiches Modell, gleicher Belegkorpus, v3-Regel als Filter importiert. Serielle Korrelation, keine Unabhängigkeit — rechtfertigt *geringere* Konfidenz, nicht höhere |
| Verbands-Kanal geschlossen | **Wieder offen.** LSB Thüringen hat einen einzelnen Anbieter gewählt (IntelliVerein); der WLSB führt laufende *Rahmenverträge*. Und `lsb-vergleichsportal.de` ist ein **kostenloses, selbstgelistetes Verzeichnis mit hoher Kaufabsicht** — für ein Team, dessen Defizit Distribution ist, ein Aktivposten, den ich als Hindernis abgelegt hatte |

**Vier von v1s sechs Fehlern liefen in dieselbe Richtung: Sie ließen das Urteil sicherer wirken, als die Belege trugen.** Dasselbe Fehlermuster zeigt die v1→v3-Historie des Vorgängerdokuments. Das ist der nützlichste Befund hier.

---

## 🔢 Der Nenner — korrigiert

Kaufende Einheit ist die **Organisation**, und die Segmente sind unterschiedlich bepreist. v1s einzelner €9-Anker war der Fehler, der das Urteil erzeugte.

**Beobachtete Wettbewerbspreise, pro Organisation:**

| Segment | Anker | ARPU/Organisation |
|---|---|---|
| selbstverw. WEG, 10 Einheiten | selbstverwalten.com €8,16 / €12,74 / €20,07 **pro Einheit/Monat** | **€82 / €127 / €201** |
| Verein, ≤100 Mitglieder (der Median: 60,9%) | WISO MeinVerein XS | **€11–13** |
| Verein, größere Stufen | WISO MeinVerein bis L | €22–€72 |
| Kleinstbetrieb | lexoffice S €6,90 · sevdesk €8,90 · Rechnungsradar €9 | **€7–9** |

| ARPU/Org | €4k | €8k | €25k | €25k als % von ~43.000 WEGs |
|---|---|---|---|---|
| €9 (v1s falscher Anker) | 444 | 889 | 2.778 | 6,5% |
| €30 | 133 | 267 | 833 | 1,9% |
| €82 | 49 | 98 | 305 | **0,7%** |
| €127 | 31 | 63 | 197 | **0,5%** |

**Unit Economics bei 85% Bruttomarge** *(ein Platzhalter, keine Annahme — siehe Vorbehalte)*:

| ARPU | Churn | LTV | Max. CAC bei 3:1 | Amortisation bei CAC €500 |
|---|---|---|---|---|
| €13 (Median-Verein) | 4% | €276 | **€92** | 45 Monate |
| €22 | 4% | €468 | €156 | 27 Monate |
| €82 (10-Einh.-WEG, Basis) | 4% | €1.742 | **€581** | 7,2 Monate |
| €127 (10-Einh.-WEG, Komfort) | 4% | €2.699 | **€900** | 4,6 Monate |
| €127 | 7% | €1.542 | €514 | 4,6 Monate |

> **Die Schwelle: Bei 4%/Monat Churn muss der ARPU über ~€71/Organisation liegen, damit ein CAC von €500 auf 3:1 kommt.** Vereine und Kleinstbetriebe liegen weit darunter. Eine pro Einheit bepreiste WEG liegt komfortabel darüber. **Diese eine Zeile trennt die toten Segmente vom lebenden** — und v1 hat sie verfehlt, weil sie alle drei auf €9 verankerte.

*Einschränkung, die der Reviewer unterschlägt:* €127/Monat bei selbstverwalten.com kaufen den **gesamten § 28-WEG-Apparat** — Wirtschaftsplan, Hausgeld, Beschlüsse, Banking, Jahresabrechnung —, nicht ein Belegpostfach. Ein reines Archivierungsprodukt kann diesen Preis nicht unterstellen. Aber selbst €30/Organisation (≈€3/Einheit bei 10 Einheiten) ergeben LTV €638 und €212 max. CAC — immer noch 3× über dem Median-Verein.

---

## ⛔ Befund 1 — Für Vereine existiert der Zwang weitgehend nicht

Die Ausgangslage steht auf: *„Dies zwingt Millionen von Betrieben, Vereinen und Eigentümergemeinschaften…"* Das BMF sagt das Gegenteil:

> *„**Betreffen Leistungen den nichtunternehmerischen Bereich des Vereins, muss der Verein weder E-Rechnungen empfangen können noch selbst E-Rechnungen ausstellen.**"* — [BMF-FAQ E-Rechnung](https://www.bundesfinanzministerium.de/Content/DE/FAQ/e-rechnung.html)

§ 14 UStG bindet **Unternehmer**. Wo die Pflicht *doch* greift: *„Für den Empfang einer elektronischen Rechnung genügt bereits ein E-Mail-Postfach"* (BMF; bestätigt von der Bundesregierung, [hib 1017282](https://www.bundestag.de/presse/hib/kurzmeldungen-1017282)). Und die Frist 2027/2028 kommt nie an: § 34a Satz 4 UStDV macht die Kleinunternehmer-Ausnahme vom *Ausstellen* **dauerhaft** — *„kann … immer als sonstige Rechnung … übermittelt werden"*.

**Zwei ehrliche Einschränkungen, die den Befund schwächen:**

1. **Ich kann nicht „die meisten" sagen.** v1 tat es unbelegt: Die Zahl der *unternehmerisch tätigen* Vereine wurde in **keiner Quelle gefunden**. Sportvereine mit Bandenwerbung, Sponsoring, Vereinsgaststätte oder Zweckbetrieb sind unternehmerisch — womöglich ein großer Anteil.
2. **Glaubensgetriebene Nachfrage ist real, und ich habe sie unterbewertet.** ClubDesk schreibt *„praktisch alle Vereine … müssen E-Rechnungen empfangen können"*. Deutsche Compliance-Software trägt regelmäßig bezahlte Anbieter auf *wahrgenommener* Pflicht — TSE/KassenSichV, DSGVO-Tooling, Hinweisgeberschutz. Nachfrage folgt der Angst vor der Prüfung, nicht der Gesetzeslektüre.

**Der Befund verengt sich daher auf:** Zwang ist eine schwache und juristisch angreifbare Basis für das Vereinssegment. Was Vereine tatsächlich schließt, ist nicht dieser Befund — es ist der **ARPU von €11–13 gegen einen maximal tragfähigen CAC von €92**, plus 70+ Konkurrenzprodukte und ein dauerhaft kostenloser Tarif (ClubDesk bis 50 Mitglieder).

*Korrektur zugunsten des Teams:* **WEGs sind tatsächlich verpflichtet.** Eine WEG **ist** Unternehmer nach § 2 UStG; § 4 Nr. 13 befreit Leistungen *an Mitglieder*, ohne die Unternehmereigenschaft zu beseitigen, und die Ausnahme nach § 4 Nr. 8–29 knüpft an den **berechneten Umsatz** an — die steuerpflichtige Handwerkerleistung an die WEG fällt voll darunter. § 14b UStG gilt, mit Bußgeld bis €5.000 nach § 26a.

---

## ⛔ Befund 2 — Der Differenzierer wird in Deutschland für €9/Monat verkauft *(selbst verifiziert)*

[Rechnungsradar](https://rechnungs-radar.de/), abgerufen 2026-08-27: *„Gmail und Microsoft per OAuth, alle übrigen Anbieter über verschlüsseltes IMAP"* · *„durchsucht dein Postfach auch rückwirkend"* · *„100 % Genauigkeit bei E-Rechnungen"* · *„Dein Kanzleikonto kostet nichts"* · EU-Server · **€9/Monat**. Ebenfalls mit Postfachüberwachung: GetMyInvoices, Tailride (Free-Tier), Pleo Fetch, Dext. **Und kostenlos als Open Source**: paperless-ngx (IMAP-Regeln + dokumentiertes Gmail/Outlook-OAuth) + [Mustangproject](https://github.com/ZUGFeRD/mustangproject) (Apache-2.0, v2.25.0, 05.08.2026).

**Präzise eingegrenzt — v1 hat überzogen.** Rechnungsradar ist ein **Zubringer in Buchhaltungssoftware**, nicht das Produkt der Vision: kein GoBD-Langzeitarchiv, kein Prüf-/Freigabe-Workflow, keine ausgehende XRechnung, keine § 28-Jahresabrechnung. Der Befund widerlegt **die Differenzierungsbehauptung**, nicht das ganze Produkt.

**Zwei weitere Korrekturen an v1:**

- **„Keine Verhaltensänderung" bleibt falsch — und ist für diesen Käufer invertiert.** Microsoft `Mail.Read` ist high-impact: Endnutzer-Zustimmung ist gesperrt, ein **Tenant-Admin muss freigeben**. Einen Ehrenamtlichen zu bitten, einem Zwei-Personen-Startup Lesezugriff auf ein Postfach mit Mitglieder- und Spenderkorrespondenz zu geben, ist eine *größere* Hürde als eine Weiterleitungsadresse — und erzeugt eine Art.-28-AVV-Pflicht für einen Kunden ohne Datenschutzbeauftragten.
- **Aber CASA ist eine Scope-Entscheidung, keine dauerhafte Steuer.** v1 schrieb „vierstelliges Jahres-Audit, für immer". Googles Restricted-Scope-Regime (Selbstscan [abgekündigt](https://appdefensealliance.dev/casa/tier-2/tier2-overview), $675–1.800/Jahr, 100-Nutzer-Deckel bis zur Freigabe) greift **nur bei Gmail-Support**. Einfaches IMAP funktioniert weiter bei GMX/Web.de/T-Online/IONOS/self-hosted. Diese plus Weiterleitungsadresse für Gmail/O365 → CASA-Kosten **€0**.

Und die KI-Extraktion ist ein abschreibendes Gut: ~**$0,0013/Seite** bei Claude-Vision, während eine echte ZUGFeRD gar kein OCR braucht — und ab **01.01.2027** müssen alle inländischen B2B-Rechnungen strukturiert nach EN 16931 sein.

---

## ⛔ Befund 3 — Beide „besonderen Hebel" existieren bereits

**„SEPA-Lastschrift … von keiner Standardlösung sauber bedient"** — vierfach widerlegt: WISO MeinVerein führt *„Rechnungen & Lastschriften"* in **jedem** Tarif; SPG-Verein nennt es Kernfunktion; ClubDesk ab €10; easyVerein bewirbt es als Stärke. Commodity.

**„Ein einfacher Export für die WEG-Jahresabrechnung würde die Lösung unverzichtbar machen"** — [selbstverwalten.com](https://selbstverwalten.com/) adressiert selbstverwaltete WEGs mit **6–20 Einheiten** und liefert bereits KI-Feldextraktion (*„alle Felder automatisch erkennen: Betrag, Fälligkeit, Kategorie, IBAN"*), Banking **und** *„Jahresabrechnung nach § 28 WEG"*. etg24 liefert XRechnung/ZUGFeRD-Eingang mit Freigabeworkflow; objegos Basis-Modul *„kostet nichts und bleibt auch kostenlos"*.

**Und das Vereinsprodukt existiert billiger:** netxp-Verein für **€7,50/Monat pauschal** unter 250 Mitgliedern — *„E-Rechnungen werden automatisch ausgelesen, digitale Belege archiviert und für den Zahlungsverkehr … vorbereitet"*.

*(Subagent-belegt mit URL; nicht selbst nachgeprüft — WebFetch-Kontingent erschöpft.)*

---

## ⛔ Befund 4 — Kanal und Fokus

**Der Steuerberater-Multiplikator ist strukturell feindlich.** DATEV ist eine **Genossenschaft von 40.176 Steuerberatern** mit ~80% eines Berufsstands von 89.549 — der gewünschte Kanalpartner ist Miteigentümer des Wettbewerbers, der ~1,7 Mio. Firmen auf DATEV Unternehmen online führt und in H1 2026 51 Mio. E-Rechnungen bewegt hat. sevdesk und Lexware Office geben Kanzleien bereits kostenlosen Zugang — ein dritter Anbieter hat nichts mehr zu bieten. Die *„50+ Mandanten"*-Prämisse widerspricht dem einzigen beobachtbaren Programm: BuchhaltungsButlers **oberste** Partnerstufe verlangt *„mindestens 10 Mandanten"*. *(Ein Datenpunkt; die Gegenargumentation ist strukturelle Schlussfolgerung, kein Beleg.)*

**Drei „PRIMÄR"-Segmente sind eine Absicherung, keine Strategie.** Jedes braucht ein anderes Produkt, einen anderen Kanal, ein anderes Killer-Feature. Das ist das einzige Problem, das allein durch Entscheidung behebbar ist.

**Der Verbandskanal ist wieder offen — gegen v1.** v1 schloss ihn, weil vier Landessportbünde ein neutrales Vergleichsportal betreiben. Doppelte Fehllesung: **LSB Thüringen hat einen einzelnen Anbieter gewählt** (IntelliVerein, kostenlos für Mitgliedsvereine bis 2026), der WLSB führt laufende *Rahmenverträge*. Und [lsb-vergleichsportal.de](https://www.lsb-vergleichsportal.de/) ist ein **kostenloses, nichtkommerzielles, von Anbietern selbst gepflegtes Verzeichnis** mit eigenem Finanzbuchhaltungsvergleich — es erreicht genau den Käufer, den v1 für unerreichbar erklärte. Für ein Team, dessen Defizit Distribution ist, der nützlichste Fund dieser Recherche.

---

## 🤖 Befund 5 — Agentic Dev, Kommodisierung, und der Burggraben, der wirklich da ist

Ihr habt das direkt gefragt. Die Antwort hat zwei Hälften, und v1 hatte die zweite falsch.

**Das Bauen kommodisiert, und es war nie der Burggraben.** Nicht-Entwickler deployen heute Auth + Datenbank + Stripe im Dialog; Codex hat 5 Mio. Wochennutzer überschritten, Nicht-Entwickler wachsen 3× schneller; Claude Cowork (12.01.2026) setzt einen Agenten auf das Dateisystem nichttechnischer Nutzer. Im Designli Moat Report (04.08.2026, n=100) bewertete **kein einziger Gründer** seine technische Verteidigbarkeit mit 5/5.

**Aber Compliance widersteht dem — und das ist das Stärkste, was in dieser gesamten Recherche für euch spricht.** Die bestbegründete Analyse 2026 verortet die Vibe-Coding-Todeszone bei mittelpreisiger, einfunktionaler Workflow-SaaS und **schließt Produkte in Audit-Trails und Compliance-Regimen ausdrücklich aus**. Die Belege sind konkret: ein Scan vibe-codierter Apps fand 2.038 hochkritische Schwachstellen, 400+ geleakte Secrets und 175 Fälle exponierter PII inklusive Bankdaten; Veracode fand OWASP-Top-10-Lücken in 45% der KI-generierten Samples. **Revisionssichere Archivierung ist eine Zusicherung, kein Feature — und Zusicherung kann ein Wochenend-Build nicht erzeugen.** Kleine deutsche Anbieter schaffen diese Hürde: Papierkram nennt PKF öffentlich als GoBD-Prüfer; ISO 27001 kostet bei kleinem Scope €8k–€40k.

**v1 hat das dann auf einer falschen Prämisse abgetan.** Staat und DATEV liefern den **Empfang** kostenlos. **GoBD-Archivierung liefert keiner von beiden** — DATEVs kostenloses E-Rechnungspostfach archiviert nicht; GoBD-konforme Ablage verlangt DATEV Unternehmen online zu €11,56/Monat, und der ELSTER-Viewer *„löst nur das Leseproblem – nicht die Anforderungen an eine GoBD-konforme digitale Archivierung."*

> **Korrigierte Regel — der übertragbare Ertrag dieser Runde:**
> **Compliance ist nur dort ein tragfähiger Burggraben, wo das Compliance-Minimum nicht kostenlos vom Staat oder vom dominanten Platzhirsch geliefert wird — und dieser Test gilt pro *Funktion*, nicht pro Kategorie.**
> In der deutschen E-Rechnung: **Transport ist €0 und bleibt es. Archivierung nicht.** v1 verallgemeinerte das Erste zum Zweiten und hätte dabei fast die einzige lebende Ausprägung begraben.

*(Kostenlose private Tarife mit Archivierung existieren — Accountable, Zervant, sevDesk, WISO MeinBüro, objego. Ob einer davon ein echtes GoBD-Testat trägt, ist ungeprüft. Der beobachtbare Preis für testierte Archivierung liegt bei ~€10–12, nicht bei €0.)*

---

## 🟡 Ausprägung 4 — der Fall, den v1 nie erzeugt hat

Der stärkste Zug des Reviews war keine Widerlegung, sondern eine Konstruktion: **GoBD-Zusicherung für den § 28-WEG-Zyklus, pro Einheit bepreist, verkauft an einen persönlich exponierten Ehrenamtlichen.** Sie überlebt die Befunde 1–4 und wurde nie geprüft:

- **Die Pflicht ist hier echt** (anders als bei Vereinen): WEG ist Unternehmer, § 14b greift, § 26a droht mit bis zu €5.000.
- **Die Archivierung verschenkt niemand** — das ist die korrigierte Fassung von Befund 5.
- **Das Segment zahlt bereits pro Einheit**: €82–€201/Monat für eine 10-Einheiten-WEG, deutlich über der €71-Schwelle. vermieter1s €449-Lifetime-Deal beziffert die Zahlungsbereitschaft unabhängig auf **45 Abo-Monate**.
- **Das Käuferprofil ist Lehrbuch-Compliance-WTP**: ein Verwaltungsbeirat, der fremdes Geld nach § 28 WEG verwaltet, einer jährlichen Eigentümerversammlung rechenschaftspflichtig ist, persönlich exponiert und terminlich gebunden.
- **Es gibt eine Budgetzeile** — das Hausgeld, aus dem sonst €25–35/Einheit/Monat für einen professionellen Verwalter flössen. €127/Monat für 10 Einheiten sind ~15% eines Monats Profiverwaltung.
- **Die Population wächst** — und v1 hat den Grund als Negativum abgelegt, obwohl er das Gegenteil ist. Das VDIV-Branchenbarometer 2025 sagt: Selbstverwaltung wächst, **weil professionelle Verwalter Mandate ablehnen**. Ein angebotsseitiges Vakuum: Organisationen mit gesetzlicher Pflicht, jährlicher Pflichtleistung, Budget — und niemandem, der sie bedient.

**Warum es trotzdem kein „Ja" ist:** selbstverwalten.com sitzt bereits drin, mit vollerem Produkt und Segmentkenntnis; ~43.000 Organisationen sind ein kleines, registerloses Universum ohne kaufbare Liste; 197 Kunden zu €127 sind ein echtes Vertriebsproblem für drei Leute, die gleichzeitig bauen; Preis-pro-Einheit für ein *reines* Archivprodukt ist unbewiesen; und das Belegvolumen pro WEG steht in **keiner Quelle**. Distribution bleibt die bindende Restriktion.

**Aber es ist eine zu prüfende Hypothese, keine zu verwerfende Ausprägung** — und dieser Unterschied ist der Unterschied zwischen v1 und v2.

---

## ⚖️ Die beiden Ziele, getrennt beantwortet

**€4k — in der WEG-Ausprägung erreichbar, sonst nicht.** 31–49 Organisationen zu €82–127, oder 133 zu €30. LTV €638–€2.699 trägt einen CAC von €212–900. Bei Vereinen (€13 ARPU, €92 max. CAC) oder Kleinstbetrieben (€7–9 gegen DATEV zu €0) nicht erreichbar.

**€8k — das Ziel, das v1 nie bewertet hat, und das interessanteste.** 63–98 WEGs zu €82–127. ≈ **€96k/Jahr: ein finanziertes Gehalt plus Overhead für ein Zweierteam.** Das ist eindeutig über Hobbyniveau, es entspricht eurem eigenen Ziel A (*„ein Gehalt"*), und es ist bei korrigierten Preisen die belastbarste Zahl in diesem Dokument.

**€25k — ein hartes Vertriebsproblem, keine arithmetische Unmöglichkeit.** 197–306 WEGs = 0,5–0,7% des Universums. v1s „arithmetisch geschlossen" ist **zurückgezogen**. Was es schließt, ist der Kanal: 197 beziehungsgetriebene Abschlüsse in ein registerloses Segment, durch drei Leute, die gleichzeitig bauen und supporten, gegen einen bereits anwesenden Platzhirsch.

**Und v1s „€4k ist ein Hobbyprojekt" ist als unzulässige Latte zurückgezogen.** Es teilte €4k durch drei Personen und kam auf „€1.333/Person" — und importierte damit v3s Drei-Gehälter-Rahmen in ein Ziel, das ihr als *„spürbares Nebeneinkommen / ein Gehalt"* definiert hattet. Ein Gehalt heißt ein Gehalt.

---

## ✅ Empfehlung

**1. Baut die Vision nicht wie geschrieben.** *(Hohe Konfidenz — Befunde 1–3 haben das Review unbeschadet überstanden.)*

**2. Streicht die Drei-Segment-Absicherung.** Vereine sind über den Preis geschlossen (€11–13 ARPU vs. €92 max. CAC, 70+ Produkte, Free-Tier, kein Zwang). Kleinstbetriebe sind über DATEV geschlossen (€0 Empfang, 1,7 Mio. Firmen auf DUO, kostenlose Kanzleizugänge bei sevdesk und Lexware). **Nur selbstverwaltete WEGs überleben — und nur für die Archivierungsaufgabe.**

**3. Akzeptiert kein kategorieweites „Nein".** v1 hat eins ausgesprochen und lag falsch. Die richtige Eingrenzung lautet: *Transport und Empfang sind dauerhaft €0 und nicht monetarisierbar; GoBD-Archivierung für einen gesetzlich verpflichteten, pro Einheit bepreisten, persönlich exponierten Käufer nicht.*

**4. Führt den €200-Test durch, bevor ihr ein weiteres Visionsdokument schreibt.** Zweimal über zwei Runden empfohlen, nie gemacht — während zwei vollständige Visionsdokumente entstanden sind. Konkret:

> **15–20 Gespräche mit Verwaltungsbeiräten selbstverwalteter WEGs (6–20 Einheiten), gefunden über Haus & Grund-Gruppen und Eigentümerforen. Fragt, wofür sie heute zahlen und was sie heute mit § 14b tun. Dann liefert GoBD-Archivierung für drei zahlende WEGs vier Wochen lang von Hand, zu €40–80/Monat.** ~4–6 Wochen einer Person, ~€200. **Testet den Preis pro Einheit, nicht pro Organisation.**

Zahlen drei selbstverwaltete WEGs nicht für eine Concierge-Version, ändert Software daran nichts. Zahlen sie, habt ihr die einzige überlebende Ausprägung bepreist — für €200 statt für einen Build.

**5. Die Reihenfolge ist die eigentliche Lehre.** Alle drei falschen Prämissen — und vier von v1s eigenen sechs Fehlern — waren in unter einer Stunde gegen eine Primärquelle prüfbar. Für ein Team, dessen erklärter Vorteil ist, dass Bauen billig ist, ist die bindende Restriktion nicht die Konstruktion, sondern **Falsifizieren vor Entwerfen**. Billig bauen nützt wenig, wenn es schnell das Falsche baut.

---

## 📋 Offene Fragen

1. **Hängt ihr an *E-Rechnung* oder an „einer monetarisierbaren B2B-SaaS in deutscher Compliance"?** Aus v3 übernommen, unbeantwortet, jetzt dringend — zwei Runden in einer Kategorie.
2. **Wäre ein Services-First-Weg akzeptabel?** ZDH (n=1.926, erhoben Jan–Feb 2026) misst **~€3.000 einmalig** pro Handwerksbetrieb — das einzige verifizierte Geld über beide Runden, und der einzige Weg, der die fehlende Distribution *herstellt*, um den Preis, zuerst Agentur zu sein.
3. **Wird der Falsifikationsschritt diesmal vor dem Entwurfsschritt laufen?** Die einzige Variable vollständig in eurer Hand.
4. **Neu — setzt `reviewer_model`.** Zwei Runden in Folge `same-model-fallback`. Da schon der gleichmodellige Reviewer fünf urteilsverändernde Fehler fand, wird ein echt unabhängiger vermutlich mehr finden.

---

> **Vorbehalte — vor Verwendung jeder Zahl lesen.**
> - **Selbst verifiziert (27./28.08.2026):** Rechnungsradar-Preise/Mechanik; DATEV-E-Rechnungsplattform-Preise. **Alles andere ist subagent- oder reviewer-belegt mit URL und von mir nicht nachgeprüft** — einschließlich aller Zahlen zu selbstverwalten.com, netxp-Verein, WISO MeinVerein, objego, vermieter1 und LSB Thüringen. **Die korrigierte Preisstruktur pro Einheit, die v2s geändertes Urteil trägt, liegt in dieser ungeprüften Gruppe. Prüft sie zuerst, wenn ihr danach handelt.**
> - **Nicht gefunden, aber tragend:** der Anteil *unternehmerisch tätiger* Vereine; das Belegvolumen pro selbstverwalteter WEG; jede verifizierte Zahl selbstverwalteter WEGs (nur die 10%-Annahme der Bundesregierung, Stand 2020, BT-Drs. 20/9890).
> - **Die 85% Bruttomarge sind ein Platzhalter.** Falsch in beide Richtungen: bei €9 ARPU sind allein EU-Kartengebühren 4–6% des Umsatzes; und GoBD erzwingt **8–10 Jahre Aufbewahrungskosten, die nach der Kündigung weiterlaufen** — eine Verbindlichkeit, die die LTV-Formel gar nicht abbilden kann.
> - **Der DACH-CAC-Benchmark (€500–2.000) stammt aus einer Population mit 10–50× diesem ARPU**, und CAC skaliert mit ACV. Er dient hier nur zur Bestimmung einer *Schwelle* (~€71 ARPU), nicht zum Schließen eines Falls. v1 nutzte ihn zum Schließen — das war ein Kategorienfehler.
> - **Ungelöster Widerspruch:** UStG behandelt die WEG als Unternehmer; der VDIV hält sie für *Verbraucher* nach § 13 BGB und hat die Frage ans BMF eskaliert. Keine veröffentlichte Antwort gefunden.
> - **Nicht behaupten:** dass GoBD die WEG *als solche* bindet — kein Statut gefunden; sauberer Anknüpfungspunkt ist § 14b UStG. Ebenso wenig, dass eine DSFA für Postfach-Scanning zwingend ist — die DSK-Muss-Liste ist nicht abschließend, und keine Aufsichtsbehörde hat zu diesem Sachverhalt entschieden.
> - **Aus v1 als unhaltbar gestrichen, damit es nicht wiederkehrt:** der Vereins-Churn-Multiplikator; die vermieter1-„Lifetime-Deal beendet die Diskussion"-Lesart; der App-Store-Umsatzkonzentrationsblock (Consumer-Mobile überträgt nicht auf deutsche B2B-Compliance-SaaS); die Konfidenzbehauptung „zweite unabhängige Bewertung".
> - **Korrektur am Vorgängerdokument:** Die in `DRAFT_erechnung_monetization.md` zitierte DATEV-Preis-URL liefert jetzt HTTP 404; umleiten auf `https://e-rechnungsplattform.datev.de/`.
> - `.sde_docs/config` fehlt — Defaults aktiv.
