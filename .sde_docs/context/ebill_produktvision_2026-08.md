# Context: Produktvision "Einfache Belegverwaltung für die E-Rechnungspflicht"

> **Source material — verbatim founder document, not an SDE artifact.**
> Origin: `produktvision.pdf`, uploaded 2026-08-27. Self-described as *"Interne Diskussionsgrundlage — Stand August 2026"*, footer: *"Erstellt mit Claude (Cowork)"*.
> Text extracted from a vector PDF (no text layer available via standard tooling); line breaks normalised, wording unchanged.
> This supersedes nothing — it is a **pivot** relative to `ebill_idea.md`, which specified a generic inbound e-invoice web app. See `.sde_docs/concept/DRAFT_erechnung_monetization.md` (v3, verdict `NO`) for the assessment of that earlier spec.

---

## Positionierung

**Produktvision: Einfache Belegverwaltung für die E-Rechnungspflicht**

Ein SaaS-Produkt, das Vereine, Wohnungseigentümergemeinschaften und Kleinstbetriebe beim Empfang, der Prüfung, der Zahlung und der GoBD-konformen Archivierung von E-Rechnungen unterstützt — ohne Buchhaltungs-Overhead.

## Ausgangslage — "Die E-Rechnungspflicht schafft einen Markt"

Deutschland führt stufenweise eine Pflicht zur elektronischen Rechnung im B2B-Bereich ein. Seit Januar 2025 müssen alle Unternehmen in der Lage sein, E-Rechnungen zu empfangen. Ab Januar 2027 müssen Kleinstbetriebe (unter 800.000 € Umsatz) E-Rechnungen auch versenden — ab 2028 gilt dies für alle.

Dies zwingt Millionen von Betrieben, Vereinen und Eigentümergemeinschaften, ihre Belegprozesse zu digitalisieren — oft zum ersten Mal. Der Markt ist real, das Timing ist gut.

**Die Lücke:** Bestehende Lösungen wie Lexoffice oder sevDesk sind für Gewerbetreibende mit Buchhaltungsbedarf gebaut. Für Vereine, WEGs und viele Kleinstbetriebe sind sie strukturell das falsche Werkzeug — zu komplex, zu teuer, am Bedarf vorbei.

## Das Produkt

Das Produkt ist kein Buchhaltungsprogramm. Es ist ein zentrales Postfach für Eingangsrechnungen — mit dem Werkzeug, diese zu prüfen, zu bezahlen, selbst E-Rechnungen zu erstellen und alles GoBD-konform zu archivieren.

**Kern-Differenzierungsmerkmal gegenüber Wettbewerbern wie Lexoffice:** Das System überwacht das bestehende Postfach des Kunden via IMAP oder OAuth. Keine neue E-Mail-Adresse, keine Verhaltensänderung — Rechnungen landen wie bisher im Eingang und werden automatisch erkannt, extrahiert und importiert.

## MVP-Funktionsumfang — vier Kernfunktionen

| Funktion | Beschreibung |
|---|---|
| **Empfang & Import** | Überwachung bestehender Postfächer oder dedizierte Eingangsadresse. Automatische Erkennung und Extraktion von XRechnung und ZUGFeRD via KI/OCR. |
| **Prüfung & Freigabe** | Übersichtliches Portal zur Sichtung und Freigabe eingehender Belege. Validierung gegen XRechnung/ZUGFeRD-Standard. |
| **E-Rechnungen erstellen** | Einfache Erstellung ausgehender Rechnungen im XRechnung- und ZUGFeRD-Format — ohne Buchhaltungskenntnisse erforderlich. |
| **GoBD-Archivierung** | Revisionssichere, GoBD-konforme Aufbewahrung aller Belege. Langzeitarchiv mit Exportfunktion für Steuerberater oder Kassenprüfer. |

## Zielgruppen

**Strategie:** Zwei Kernsegmente adressieren, für die keine bestehende Lösung strukturell passt. Freelancer und Ein-Mann-Betriebe kommen organisch als natürliche Erweiterung — ohne eigenes Marketing dagegen zu kämpfen.

### PRIMÄR — Eingetragene Vereine & Kassenwarte
Ca. 600.000 eingetragene Vereine in Deutschland. Der Kassenwart ist meist ein Ehrenamtlicher ohne Buchhaltungswissen. Lexoffice ist für ihn das falsche Produkt — er braucht keine USt-Voranmeldung, keinen Jahresabschluss. Er braucht: Rechnungen sammeln, bezahlen, archivieren, Kassenprüfung vorbereiten.

> *Besonderer Hebel:* SEPA-Lastschrift für Mitgliedsbeiträge wäre ein starkes Alleinstellungsmerkmal für dieses Segment, das aktuell von keiner Standardlösung sauber bedient wird. Vereine kommunizieren in Verbänden — gute Word-of-Mouth-Dynamik.

### PRIMÄR — Wohnungseigentümergemeinschaften (WEGs)
Mehrere Millionen WEG-Einheiten in Deutschland, davon ein erheblicher Anteil selbstverwaltet. Workflow: Rechnungen von Handwerkern und Versorgern empfangen, Eigentümer zur Prüfung vorlegen, bezahlen, für die Jahresabrechnung archivieren. Das ist exakt der MVP-Workflow dieses Produkts.

> *Besonderer Hebel:* Ein einfacher Export für die WEG-Jahresabrechnung (strukturierte Übersicht aller Belege nach Kategorie und Zeitraum) würde die Lösung für selbstverwaltete WEGs unverzichtbar machen.

### PRIMÄR — Kleinstbetriebe mit Steuerberater
Handwerker, kleine Dienstleister, lokale Händler — sie führen keine eigene Buchhaltung, sondern übergeben Belege an den Steuerberater. Das Problem ist die Übergabe: chaotisch, per Schuhkarton oder unstrukturierte E-Mails. Ein strukturierter Beleg-Flow als Zwischenschicht zum Steuerberater löst ein echtes Problem.

> *Besonderer Hebel:* DATEV-Integration als Exportkanal zum Steuerberater. Dieser kann aktiv als Multiplikator dienen — ein Steuerberater empfiehlt die Lösung seinen 50+ Mandanten.

### SEKUNDÄR — Freelancer & Ein-Mann-Betriebe
Kommen organisch, weil der Kernworkflow identisch ist. Brauchen zusätzlich ausgehende XRechnung-Erstellung für B2B-Kunden. Dieses Segment wird nicht primär beworben — sie finden das Produkt über Content, Empfehlungen oder E-Rechnungs-Suchanfragen.

> *Hinweis:* Dieses Segment direkt zu bewerben bedeutet direkter Wettbewerb mit Lexoffice und sevDesk auf deren Kernkeywords. Besser: sie über die Nischenpositionierung mitziehen lassen.

## Wettbewerb — Positionierung im Markt

Der Markt ist besetzt, aber nicht für diese Segmente. Die entscheidende Positionierung ist: **kein Buchhaltungsprogramm** — sondern strukturierte Belegverwaltung für Menschen, die keine Buchhalter sind.

| Wettbewerber | Einschätzung im Vision-Dokument |
|---|---|
| **Lexoffice / sevDesk** | Vollständige Buchhaltungslösungen mit E-Rechnungs-Features. Hat ebenfalls einen Email-Posteingang (dedizierte Adresse). Für Gewerbetreibende mit Buchhaltungsbedarf gebaut — strukturell falsches Produkt für Vereine und WEGs. Starker CAC-Vorteil durch Marktstellung. |
| **Tabula** | KI-Plattform für Steuerkanzleien und deren Mandanten. Primäre Zielgruppe ist der Steuerberater, nicht der Unternehmer selbst. Kein Konkurrent für Vereine und WEGs — eher komplementär. |
| **BuchhaltungsButler** | Nächster struktureller Vergleichspunkt: Belegverwaltung für KMU ohne vollständige Buchhaltung. Primär Freelancer und kleine GmbHs — kaum Fokus auf Vereine/WEGs. |
| **GetMyInvoices** | Fokus auf automatisierten Belegabruf aus Portalen (Amazon, Telekom etc.) — anderer Ansatz, anderes Segment (Mittelstand). Kein direkter Wettbewerber in den Zielsegmenten. |

**Kern-Differenzierung (laut Vision):** IMAP-Überwachung bestehender Postfächer (keine neue E-Mail-Adresse nötig) + radikale Einfachheit ohne Kontenrahmen und Jahresabschluss + zielgruppenspezifische Features (Kassenprüfung-Export, WEG-Jahresabrechnung, SEPA für Mitgliedsbeiträge), die kein anderer Anbieter heute sauber löst.

## Roadmap — geplante Ausbaustufen

- QR-Code-Generierung (EPC) für schnelle mobile Überweisung direkt aus dem Portal
- Teilen von Belegen und Rechnungen via Link (für Freigabeprozesse in Vereinen / WEGs)
- DATEV Unternehmen Online – Export für Steuerberater-Übergabe
- Open Banking / Bankkonto-Anbindung zur automatischen Zuordnung von Zahlungsvorgängen zu Belegen
- SEPA-Lastschrift für wiederkehrende Zahlungen (Mitgliedsbeiträge)
- Einfaches PDF-Editing: Markierungen und Anmerkungen auf Belegen
- Mehrbenutzer & Freigabe-Workflows (z. B. Vorstand muss Zahlung freigeben)

## Offene Fragen des Gründerteams (aus dem Dokument)

1. **Zahlungsinitiierung:** Wollen wir tatsächlich Überweisungen im Portal anstoßen (PSD2-Compliance, finAPI/Salt Edge-Integration nötig) oder erstmal nur auf Banking-Apps verlinken?
2. **Distribution:** Wie erreichen wir Kassenwarte und WEG-Verwalter konkret? Direkt über SEO/Content, über Verbände und Dachorganisationen, oder über Steuerberater als Multiplikatoren?
3. **Preismodell:** Monatspauschale pro Organisation, pro Beleg, oder Freemium mit Volumen-Schwelle? Was ist die Zahlungsbereitschaft eines Sportvereins vs. eines Kleinstbetriebs?
4. **Zielgruppenpriorisierung:** Mit welchem der drei primären Segmente starten wir — und warum? Wo ist die kürzeste Zeit von erstem Gespräch bis zahlendem Kunden?
5. **Technologie:** KI-gestützte Belegextraktion ist Markterwartung (Tabula, Lexoffice setzen den Standard). Bauen wir selbst oder integrieren wir einen bestehenden OCR/AI-Belegverarbeitungs-Dienst?
6. **Produktname und Markenidentität:** Wie soll das Produkt heißen, und wie soll es sich anfühlen — eher "professionelles Werkzeug" oder "zugängliche, freundliche App"?
