Hier ist eine strukturierte Spezifikation (Spec) basierend auf euren Anforderungen. Ich habe das Gespräch in funktionale und nicht-funktionale Anforderungen übersetzt, damit es direkt als Grundlage für die Entwicklung genutzt werden kann.

# Spezifikation: Web-App für E-Rechnungsmanagement (MVP)

## 1. Zielsetzung

Entwicklung einer cloudbasierten Web-Applikation zur zentralen Verwaltung, Visualisierung und Freigabe von E-Rechnungen. Die Plattform soll den Rechnungseingang sowohl über manuellen Upload als auch über automatisierte E-Mail-Postfächer bündeln, Workflows vereinfachen und eine direkte Schnittstelle zu Banking-Apps sowie der Buchhaltung (DATEV) bieten.

---

## 2. Funktionale Anforderungen (Features)

### 2.1 Benutzerverwaltung & Onboarding

* *Registrierung & Login:* Nutzer müssen sich auf der Plattform registrieren und ein eigenes Profil/Konto anlegen können.
* *Kundenspezifischer Posteingang:* Bei der Kontoerstellung wird automatisch eine individuelle, kundenspezifische E-Mail-Adresse (z. B. firma@rechnung.euer-tool.de) generiert.

### 2.2 Rechnungs-Import

* *Manueller Upload:* Benutzer können E-Rechnungen manuell über die Weboberfläche hochladen.
* *E-Mail-Import:* Eingehende E-Mails an die kundenspezifische Adresse werden automatisch geparst, und die angehängten E-Rechnungen erscheinen direkt im Tool-Posteingang.
* *Formatunterstützung:* Das System verarbeitet alle gängigen E-Rechnungs-Formate (insbesondere ZUGFeRD und XRechnung).

### 2.3 Visualisierung & Export

* *Darstellung:* Rechnungen in maschinenlesbaren Formaten (z. B. reine XML-Dateien bei XRechnung), die keine eigene PDF-Darstellung mitbringen, werden vom Tool in ein visuell lesbares Format übersetzt und angezeigt.
* *Download:* Nutzer können die Originaldateien sowie ggf. die visualisierten PDFs jederzeit herunterladen.

### 2.4 Verwaltung & Workflow

* *Dashboard / Listenansicht:* Zentrale Übersicht aller eingegangenen Rechnungen.
* *Suchfunktion:* Durchsuchbarkeit der Rechnungen anhand ausgelesener Metadaten (Absender, Datum, Betrag, Rechnungsnummer).
* *Freigabeprozess:* Ein integrierter, schlanker Freigabemechanismus (z. B. Status-Wechsel von "Eingegangen" zu "Freigegeben" oder "Abgelehnt").
* *Weiterleitung:* Möglichkeit, Rechnungen aus dem Tool heraus an andere Personen (z. B. intern zur Prüfung) weiterzuleiten.

### 2.5 Zahlungsabwicklung

* *QR-Code-Generierung:* Das Tool liest die Zahlungsdaten (IBAN, BIC, Betrag, Verwendungszweck) aus der E-Rechnung aus und generiert daraus automatisch einen standardisierten Bezahl-QR-Code (GiroCode/EPC-QR-Code).
* *Scan to Pay:* Nutzer können diesen QR-Code vom Bildschirm mit ihrer Smartphone-Banking-App einscannen, um die Überweisung in Sekunden fehlerfrei auszuführen.

---

## 3. Nicht-funktionale Anforderungen (Infrastruktur & Compliance)

* *GoBD-Konformität:* Die Systemarchitektur und Datenspeicherung müssen so gestaltet sein, dass sie den Grundsätzen zur ordnungsmäßigen Führung und Aufbewahrung von Büchern, Aufzeichnungen und Unterlagen in elektronischer Form (GoBD) entsprechen (z. B. Unveränderbarkeit, Historisierung, sicheres Archiv).
* *Datenschutz (DSGVO):* Die gesamte Plattform muss den geltenden Datenschutzrichtlinien entsprechen (sicheres Hosting, Verschlüsselung bei Übertragung und Speicherung, sicheres Session-Management).
* *Schnittstellen / Integrationen:*
* *DATEV-Schnittstelle (Optional/Erweiterung):* Eine Anbindung zur strukturierten Übergabe der freigegebenen Rechnungsdaten und Belegbilder an die DATEV-Systeme der Steuerberater.