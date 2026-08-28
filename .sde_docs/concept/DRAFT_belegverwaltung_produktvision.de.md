# 💡 Konzept: „Einfache Belegverwaltung für die E-Rechnungspflicht" — Wirtschaftlichkeitsbewertung

> Deutsche Fassung von `DRAFT_belegverwaltung_produktvision.md`. Bei Abweichungen gilt die englische Fassung als SDE-Artefakt.

## 📌 Status

`DRAFT` · **v3** — ergebnisorientierte Neufassung von v2. Substanz unverändert; die Refutations-Prozessgeschichte ist entfernt, weil sie dem Autor diente, nicht dem Leser.

| Feld | Wert |
|---|---|
| Erstellt | 2026-08-28 |
| Bewertet | `.sde_docs/context/ebill_produktvision_2026-08.md` — Gründerdokument, August 2026 |
| Frage | *„Lässt sich diese Idee monetarisieren und lohnt sich somit das Bauen?"* — über ein Hobbyprojekt hinaus |
| Team | 2–3 Personen, starker Software-/Agentic-Dev-Hintergrund, **keine Distribution** |
| Ziele | **(A) €4–8k MRR** — Nebeneinkommen / ein Gehalt · **(B) €25k MRR** — Lebensunterhalt für drei |
| Recherche | 4 delegierte Pässe, ~273 Tool-Calls · Adversarial Review: `REVISE`, in v2 aufgelöst |
| Unabhängigkeit des Reviews | **`same-model-fallback`** — gleiches Modell wie der Autor. Echte Minderung der Unabhängigkeit; `/sde-status` kann `reviewer_model` setzen |

---

## ⚖️ Urteil

**Baut die Vision nicht wie geschrieben.** Drei ihrer Tatsachenprämissen scheitern an Primärquellen — jede war in unter einer Stunde prüfbar.

**Aber die Kategorie ist nicht geschlossen.** Transport und Empfang von E-Rechnungen sind dauerhaft €0 und nicht monetarisierbar. **GoBD-Archivierung ist es nicht** — und eine Ausprägung auf dieser Unterscheidung überlebt: *Archivierung für selbstverwaltete WEGs, pro Einheit bepreist.* Beim €8k-Ziel ist das die belastbarste Zahl in diesem Dokument. Eine zu prüfende Hypothese, kein zu startendes Geschäft.

**Streicht die Drei-Segment-Absicherung.** Vereine und Kleinstbetriebe sind über den Preis geschlossen. Nur WEGs überleben.

---

## 🎯 Problemstellung

Kann ein 2–3-Personen-Team ohne Distribution eine einfache E-Rechnungs-/Belegverwaltungs-SaaS für Vereine, selbstverwaltete WEGs und Kleinstbetriebe über Hobbyniveau hinaus monetarisieren — im deutschen Markt des August 2026?

Die Vision ist strategisch gut gedacht: Sie erkennt, dass das generische Produkt besetzt ist, verengt auf ignorierte Segmente und benennt einen konkreten Differenzierer. Ihre Prämissen sind das Problem.

---

## ⛔ Die drei Prämissen, die scheitern

### 1. Vereine sind nicht verpflichtet

Die Ausgangslage steht auf *„Dies zwingt Millionen von Betrieben, Vereinen und Eigentümergemeinschaften…"*. Das BMF sagt das Gegenteil:

> *„Betreffen Leistungen den nichtunternehmerischen Bereich des Vereins, muss der Verein weder E-Rechnungen empfangen können noch selbst E-Rechnungen ausstellen."*
> — [BMF-FAQ E-Rechnung](https://www.bundesfinanzministerium.de/Content/DE/FAQ/e-rechnung.html)

§ 14 UStG bindet **Unternehmer**. Wo die Pflicht greift, *„genügt bereits ein E-Mail-Postfach"* (gleiche Quelle). Und die Frist 2027/2028 kommt nie an: § 34a Satz 4 UStDV macht die Kleinunternehmer-Ausnahme vom Ausstellen **dauerhaft**.

Zwei Einschränkungen, die das abschwächen: Der Anteil *unternehmerisch tätiger* Vereine wurde in **keiner Quelle gefunden** — „die meisten" lässt sich also nicht behaupten. Und glaubensgetriebene Nachfrage ist real: Anbieter und Landessportbünde behaupten aktiv das Gegenteil, und deutsche Compliance-Software trägt regelmäßig bezahlte Anbieter auf *wahrgenommener* Pflicht (TSE/KassenSichV, DSGVO-Tooling).

**Was Vereine tatsächlich schließt, ist nicht das Recht — es ist der Preis.** €11–13 ARPU für den Median-Verein (60,9% haben ≤100 Mitglieder) gegen einen maximal tragfähigen CAC von €92, plus 70+ Konkurrenzprodukte und einen dauerhaft kostenlosen Tarif (ClubDesk bis 50 Mitglieder).

*Zugunsten des Teams:* **WEGs sind tatsächlich verpflichtet.** Eine WEG **ist** Unternehmer nach § 2 UStG; § 4 Nr. 13 befreit Leistungen *an Mitglieder*, ohne die Unternehmereigenschaft zu beseitigen, und die Ausnahme nach § 4 Nr. 8–29 knüpft am berechneten Umsatz an — die steuerpflichtige Handwerkerleistung an die WEG fällt voll darunter. § 14b gilt, mit Bußgeld bis €5.000 nach § 26a.

### 2. Der Differenzierer wird für €9/Monat verkauft

> *„Kern-Differenzierungsmerkmal … Das System überwacht das bestehende Postfach des Kunden via IMAP oder OAuth."*

[Rechnungsradar](https://rechnungs-radar.de/) verkauft genau das — *„Gmail und Microsoft per OAuth, alle übrigen Anbieter über verschlüsseltes IMAP"*, rückwirkende Postfachsuche, kostenloses Kanzleikonto, EU-Server — für **€9/Monat**. *(Selbst verifiziert, 27.08.2026.)* Ebenfalls mit Postfachüberwachung: GetMyInvoices, Tailride, Pleo, Dext. Und kostenlos als Open Source: paperless-ngx + [Mustangproject](https://github.com/ZUGFeRD/mustangproject).

Präzise eingegrenzt: Rechnungsradar ist ein **Zubringer in Buchhaltungssoftware** — kein GoBD-Archiv, kein Freigabe-Workflow, keine ausgehende XRechnung, keine § 28-Jahresabrechnung. Es widerlegt die *Differenzierungsbehauptung*, nicht das ganze Produkt.

Zwei Punkte zum Mitnehmen:
- **„Keine Verhaltensänderung" ist für diesen Käufer invertiert.** Microsoft `Mail.Read` braucht **Tenant-Admin**-Zustimmung. Einen Ehrenamtlichen zu bitten, einem Zwei-Personen-Startup Lesezugriff auf ein Postfach mit Mitglieder- und Spenderkorrespondenz zu geben, ist eine *größere* Hürde als eine Weiterleitungsadresse — und erzeugt eine Art.-28-AVV-Pflicht für einen Kunden ohne DSB.
- **Googles CASA-Audit ($675–1.800/Jahr, 100-Nutzer-Deckel bis zur Freigabe) ist eine Scope-Entscheidung, keine fixe Kostenposition.** Es greift nur bei Gmail-Support. Einfaches IMAP funktioniert weiter bei GMX/Web.de/T-Online/IONOS. Diese plus Weiterleitungsadresse → €0.

### 3. Beide „besonderen Hebel" existieren bereits

**SEPA-Lastschrift für Mitgliedsbeiträge** — behauptet als *„von keiner Standardlösung sauber bedient"*. Vierfach widerlegt: WISO MeinVerein führt es in **jedem** Tarif, SPG-Verein nennt es Kernfunktion, ClubDesk ab €10, easyVerein bewirbt es als Stärke.

**WEG-Jahresabrechnungs-Export** — [selbstverwalten.com](https://selbstverwalten.com/) adressiert selbstverwaltete WEGs mit 6–20 Einheiten und liefert bereits KI-Feldextraktion, Banking **und** *„Jahresabrechnung nach § 28 WEG"*. etg24 liefert XRechnung/ZUGFeRD-Eingang mit Freigabeworkflow; objegos Basis-Modul ist dauerhaft kostenlos.

Und das Vereinsprodukt existiert billiger: **netxp-Verein, €7,50/Monat pauschal** unter 250 Mitgliedern, mit automatischem E-Rechnungs-Auslesen und Archivierung.

---

## 🔢 Die Zahlen

Kaufende Einheit ist die **Organisation** — und WEG-Software wird **pro Einheit** abgerechnet.

| Segment | Anker | ARPU pro Organisation |
|---|---|---|
| selbstverw. WEG, 10 Einheiten | selbstverwalten.com €8,16 / €12,74 / €20,07 **pro Einheit/Monat** | **€82 / €127 / €201** |
| Verein, ≤100 Mitglieder (Median) | WISO MeinVerein XS | **€11–13** |
| Kleinstbetrieb | lexoffice €6,90 · sevdesk €8,90 · Rechnungsradar €9 | **€7–9** |

| ARPU/Org | €4k | €8k | €25k | €25k als % von ~43.000 WEGs |
|---|---|---|---|---|
| €30 | 133 | 267 | 833 | 1,9% |
| €82 | 49 | 98 | 305 | 0,7% |
| €127 | 31 | 63 | 197 | **0,5%** |

| ARPU | Churn | LTV | Max. CAC bei 3:1 | Amortisation bei CAC €500 |
|---|---|---|---|---|
| €13 (Median-Verein) | 4% | €276 | **€92** | 45 Monate |
| €82 (10-Einh.-WEG) | 4% | €1.742 | **€581** | 7,2 Monate |
| €127 (10-Einh.-WEG) | 4% | €2.699 | **€900** | 4,6 Monate |

> **Die eine Zahl, die alles entscheidet: Bei 4%/Monat Churn muss der ARPU über ~€71 pro Organisation liegen, damit ein CAC von €500 auf 3:1 kommt.**
> Vereine (€13) und Kleinstbetriebe (€7–9) liegen weit darunter. Eine pro Einheit bepreiste WEG liegt komfortabel darüber.

*Einschränkung:* €127 bei selbstverwalten.com kaufen den **gesamten § 28-Apparat** — Wirtschaftsplan, Hausgeld, Beschlüsse, Banking —, nicht ein Belegpostfach. Ein reines Archivprodukt kann diesen Preis nicht unterstellen. Aber selbst €30/Organisation (≈€3/Einheit × 10) ergeben LTV €638 und €212 max. CAC — immer noch 3× über dem Median-Verein.

---

## 🟡 Was überlebt: GoBD-Archivierung für den § 28-WEG-Zyklus

Vier Bedingungen treffen hier zusammen und sonst nirgends in dieser Vision:

- **Echte Pflicht** — WEG ist Unternehmer, § 14b greift, § 26a droht mit bis zu €5.000.
- **Diese Funktion verschenkt niemand.** DATEVs kostenloses E-Rechnungspostfach und das BMF-*„ein E-Mail-Postfach genügt"* decken **nur den Empfang**. GoBD-konforme Ablage verlangt DATEV Unternehmen online zu €11,56/Monat; der ELSTER-Viewer *„löst nur das Leseproblem – nicht die Anforderungen an eine GoBD-konforme digitale Archivierung."*
- **Ein Käufer mit persönlicher Exponierung** — ein Verwaltungsbeirat, der fremdes Geld nach § 28 WEG verwaltet, einer jährlichen Eigentümerversammlung rechenschaftspflichtig, terminlich gebunden. Lehrbuch-Zahlungsbereitschaft für Compliance.
- **Eine Budgetzeile** — das Hausgeld, aus dem sonst €25–35/Einheit/Monat für einen professionellen Verwalter flössen. €127/Monat für 10 Einheiten sind ~15% eines Monats Profiverwaltung.

Die Population wächst zudem, aus einem Grund, den man richtig lesen muss: Das VDIV-Branchenbarometer 2025 berichtet, Selbstverwaltung wachse, **weil professionelle Verwalter Mandate ablehnen**. Das ist ein angebotsseitiges Vakuum — Organisationen mit gesetzlicher Pflicht, jährlicher Pflichtleistung und Budget, die niemand bedient.

**Warum das trotzdem kein „Ja" ist:** selbstverwalten.com sitzt bereits drin, mit vollerem Produkt; ~43.000 Organisationen sind ein kleines, registerloses Universum ohne kaufbare Liste; 197 Kunden sind ein echtes Vertriebsproblem für drei Leute, die gleichzeitig bauen; Preis-pro-Einheit für ein *reines* Archivprodukt ist unbewiesen; und das Belegvolumen pro WEG steht in **keiner Quelle**. Distribution bleibt die bindende Restriktion.

---

## 🎯 Die beiden Ziele

| Ziel | Urteil |
|---|---|
| **€4k** | In der WEG-Ausprägung erreichbar (31–49 Organisationen zu €82–127). Bei Vereinen oder Kleinstbetrieben nicht. |
| **€8k** | **63–98 WEGs ≈ €96k/Jahr — ein finanziertes Gehalt plus Overhead für ein Zweierteam.** Entspricht eurem Ziel A und ist die belastbarste Zahl hier. |
| **€25k** | 197–306 WEGs = 0,5–0,7% Anteil. Ein hartes Vertriebsproblem, *keine* arithmetische Unmöglichkeit. Was es schließt, ist der Kanal, nicht die Mathematik. |

---

## 🧩 Die übertragbare Regel

> **Compliance ist nur dort ein tragfähiger Burggraben, wo das Compliance-Minimum nicht kostenlos vom Staat oder vom dominanten Platzhirsch geliefert wird — und dieser Test gilt pro *Funktion*, nicht pro Kategorie.**

Das ist die Antwort auf eure Frage zur Agentic-Dev-Kommodisierung. Das Bauen kommodisiert und war nie der Burggraben: Im Designli Moat Report (04.08.2026, n=100) bewertete **kein einziger Gründer** seine technische Verteidigbarkeit mit 5/5. Aber Compliance widersteht dem — ein Scan vibe-codierter Apps fand 2.038 kritische Schwachstellen, 400+ geleakte Secrets und 175 Fälle exponierter PII; Veracode fand OWASP-Top-10-Lücken in 45% der KI-generierten Samples. **Revisionssichere Archivierung ist eine Zusicherung, kein Feature — und Zusicherung kann ein Wochenend-Build nicht erzeugen.** Kleine deutsche Anbieter schaffen diese Hürde: Papierkram nennt PKF öffentlich als GoBD-Prüfer.

Hier angewandt: **Transport ist €0 und bleibt es; Archivierung nicht.** Das Erste zum Zweiten zu verallgemeinern hätte fast die einzige lebende Ausprägung begraben.

---

## ✅ Empfehlung

1. **Baut die Vision nicht wie geschrieben.** *(Hohe Konfidenz.)*
2. **Lasst Vereine und Kleinstbetriebe fallen.** Geschlossen über den Preis bzw. über DATEV.
3. **Prüft die WEG-Archivierungs-Ausprägung, bevor ihr weiterschreibt.**

> **Der €200-Test:** 15–20 Gespräche mit Verwaltungsbeiräten selbstverwalteter WEGs (6–20 Einheiten), über Haus & Grund-Gruppen und Eigentümerforen. Fragt, wofür sie heute zahlen und was sie heute mit § 14b tun. Dann liefert GoBD-Archivierung für drei zahlende WEGs vier Wochen lang von Hand, zu €40–80/Monat. **Preis pro Einheit, nicht pro Organisation.** ~4–6 Wochen einer Person, ~€200.

Zahlen drei WEGs nicht für eine Concierge-Version, ändert Software daran nichts. Zahlen sie, habt ihr die überlebende Ausprägung für €200 bepreist statt für einen Build.

**Die Reihenfolge ist die eigentliche Lehre.** Alle drei falschen Prämissen waren in unter einer Stunde gegen eine Primärquelle prüfbar — und die Vision wurde geschrieben, bevor diese Stunde investiert war. Für ein Team, dessen Vorteil ist, dass Bauen billig ist, lautet die bindende Restriktion: **Falsifizieren vor Entwerfen.**

---

## 📋 Offene Fragen

1. **Hängt ihr an *E-Rechnung* oder an „einer monetarisierbaren B2B-SaaS in deutscher Compliance"?** Zwei Runden in einer Kategorie.
2. **Wäre ein Services-First-Weg akzeptabel?** ZDH (n=1.926, Jan–Feb 2026) misst **~€3.000 einmalig** pro Handwerksbetrieb — das einzige verifizierte Geld über beide Runden, und der einzige Weg, der die fehlende Distribution *herstellt*, um den Preis, zuerst Agentur zu sein.
3. **Läuft der Falsifikationsschritt diesmal vor dem Entwurfsschritt?** Zweimal empfohlen, noch nicht gemacht — während zwei vollständige Visionsdokumente entstanden.
4. **Setzt `reviewer_model`** in `.sde_docs/config` — zwei Runden liefen auf `same-model-fallback`.

---

> **Vorbehalte — vor Verwendung jeder Zahl lesen.**
> - **Selbst verifiziert:** nur Rechnungsradar- und DATEV-Preise. **Alles andere ist subagent-belegt mit URL und nicht nachgeprüft** — einschließlich aller Zahlen zu selbstverwalten.com, netxp-Verein, WISO MeinVerein, objego und vermieter1. **Die Preisstruktur pro Einheit, die das Urteil dieses Dokuments trägt, liegt in dieser ungeprüften Gruppe. Prüft `selbstverwalten.com/preise` zuerst selbst, wenn ihr danach handelt.**
> - **Nicht gefunden, aber tragend:** der Anteil *unternehmerisch tätiger* Vereine; das Belegvolumen pro selbstverwalteter WEG; jede verifizierte Zahl selbstverwalteter WEGs (nur die 10%-Annahme der Bundesregierung, Stand 2020, BT-Drs. 20/9890).
> - **Die 85% Bruttomarge sind ein Platzhalter.** Bei €9 ARPU sind allein EU-Kartengebühren 4–6% des Umsatzes; und GoBD erzwingt **8–10 Jahre Aufbewahrungskosten, die nach der Kündigung weiterlaufen** — eine Verbindlichkeit, die LTV nicht abbilden kann.
> - **Der DACH-CAC-Benchmark (€500–2.000) stammt aus einer Population mit 10–50× diesem ARPU**, und CAC skaliert mit ACV. Er dient hier nur zur Bestimmung der ~€71-Schwelle, nie zum Schließen eines Falls.
> - **Ungelöst:** UStG behandelt die WEG als Unternehmer; der VDIV hält sie für *Verbraucher* nach § 13 BGB und hat die Frage ans BMF eskaliert. Keine veröffentlichte Antwort gefunden.
> - **Nicht behaupten**, dass GoBD die WEG *als solche* bindet (kein Statut gefunden — sauberer Anknüpfungspunkt ist § 14b UStG), ebenso wenig, dass eine DSFA für Postfach-Scanning zwingend ist (DSK-Muss-Liste nicht abschließend; keine Aufsichtsbehörde hat entschieden).
> - **Ein früherer Entwurf verankerte alle drei Segmente bei €9 pro Organisation** und wandte damit WEG-Preise pro Einheit falsch an. Dieser Fehler ließ das Urteil weit sicherer wirken, als die Belege trugen. Hier korrigiert; festgehalten, damit der €9-Anker nicht zurückkehrt.
> - `.sde_docs/config` fehlt — Defaults aktiv.
