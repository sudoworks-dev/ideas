# Konzept: Hausautomation Einstieg — Bestandsgebäude Bj. 2000, Eltako-Stromstoßschaltung

📌 **Status:** DRAFT — **Version 2** (nach unabhängiger Widerlegung überarbeitet)
📅 **Erstellt:** 2026-09-20
🎯 **Ziel:** Licht, Rollladen, PV und Wärmepumpe in Home Assistant, ohne dass ein HA-Ausfall das Haus lahmlegt

> **Sprache:** Deutsch, abweichend von der SDE-Kernregel „Artefakte in Englisch". Konvention für
> Eigenbau-Projekte des Nutzers (vgl. `concept/garten/`), Ausführung durch den Nutzer selbst.
> Bewusste, sichtbare Abweichung.

> **Version 2 ist eine Korrektur, keine Erweiterung.** Eine unabhängige Prüfung hat v1 mit `REVISE`
> bewertet. Fünf tragende Befunde, davon drei in Baustein 1 — genau dem Teil, den v1 selbst als
> „den einzigen nicht-trivialen" bezeichnet hatte:
>
> | v1 | Warum falsch | v2 |
> |---|---|---|
> | „Weg A (Zentraleingänge) lässt **das Driftproblem an der Wurzel verschwinden**", O1 = „erste Handlung" | **Logikfehler.** Gerichtete Befehle beseitigen Unsicherheit über *HA-eigene* Befehle. Drückt jemand den **Wandtaster** — was A1 ausdrücklich erlauben muss — weiß HA wieder nichts. Weg A liefert Befehlsdeterminismus, **nicht Zustandskenntnis** | Nur **Weg B** (Lastrückmeldung) erfüllt A2. Weg A behalten, aber aus einem **A1**-Grund |
> | Shelly Pro 2 „potentialfrei ⇒ unabhängig von der Phase" | Nur die **Ausgänge** sind potentialfrei. Die **SW-Eingänge sind es nicht** — und Weg B führt genau dort die Lastader auf. Damit war die Phasenkollision, vor der v1 warnte, in v1s eigener Lösung enthalten | Phasengruppierung + Phasenerhebung als **O2** |
> | „**A1 ist strukturell erfüllt**" | Betrachtet nur den Ausfall von *HA*, nicht den des *Shelly im geschlossenen Zustand*. Ein klebender Kontakt hält die Eltako-Spule dauererregt → **der Wandtaster ist wirkungslos**, der Kreis eingefroren | A1 **bedingt** erfüllt, Einzelfehler benannt und abgesichert |
> | Navigator 2.0 = `read_input_register`, 1.7 = `read_holding_register` | **Falsch und in sich widersprüchlich** (v1 nannte 74 zwei Absätze später „Holding"). Die Unterscheidung ist **RO gegen RW**, nicht Generation gegen Generation | Am Original 812170 Rev. 10 korrigiert |
> | „eine HA-Automatisierung", Stufe 1 „null Risiko" | Register 74 muss **zyklisch** geschrieben werden. Ohne Watchdog heizt ein HA-Ausfall bei 4 kW Überschuss die Anlage **die ganze Nacht aus dem Netz** — das ökonomische Gegenteil des Anwendungsfalls | Watchdog, Totmann, 15-s-Totzeit ergänzt |
>
> Weitere Korrekturen: **1 TE statt 2 TE** je Shelly Pro 2 (19 mm) · ESP-NOW-Peers **20 gesamt /
> verschlüsselt max. 17, Default 7** (nicht „20 unverschlüsselt / 10 verschlüsselt") · NAV § 13
> verlangt ein **eingetragenes Installationsunternehmen**, nicht nur eine Elektrofachkraft ·
> die „Smartfox"-Einstellung steht **nicht** in der iDM-Unterlage · „169+ Entities" war unbelegt.
>
> **Zwei Akzeptanzkriterien aus v1 waren erfunden** (A2, A6) — dazu unten „Scope-Korrektur".

---

## 🎯 Problem Statement

Ein Einfamilienhaus Baujahr 2000 soll automatisiert werden. Die Elektroinstallation ist
**sternförmig auf einen Verteiler geführt** und dort mit **Eltako-Stromstoßrelais** für Licht
aufgebaut; Rollläden laufen über einfache Relais. Es gibt **keinen Bus** (kein KNX). PV ist
**Fronius** mit **BYD-Hochvoltspeicher**, im Heim-LAN erreichbar. Die Wärmepumpe ist von **iDM**.

Der Nutzer schreibt selbst Code und kann Hardware und Gehäuse löten.

### Gewünschtes Ergebnis

1. Licht im Haus und Garten schalten
2. Rollläden steuern
3. Daten erfassen: Wärmepumpe, PV, Speicher
4. Erweiterbarkeit für später gekaufte Leuchten

### Scope-Korrektur gegenüber v1

Die Prüfung hat zu Recht beanstandet, dass v1 zwei Kriterien als abgeleitet ausgab, die in
Wahrheit **hinzuerfunden** waren. Das ist bei dir ein wiederkehrendes Muster (vgl.
`constraints-in-concepts-are-assumptions`), deshalb hier explizit:

| Kriterium | Status in v1 | Status in v2 |
|---|---|---|
| **A2** (HA kennt echten Zustand) | als „folgt aus A1" deklariert | **Offene Nutzerentscheidung (O1).** „Schalten" braucht keine Zustandskenntnis. Die brauchen *Automatiken* — und die stehen in keinem deiner vier Anwendungsfälle. A2 ist der teuerste Einzelposten des Projekts und darf keine stille Annahme sein. |
| **A6** (batteriebetriebene Sensorik) | als Akzeptanzkriterium geführt | **Gestrichen.** Hatte keine Entsprechung in den Anwendungsfällen; es war die diplomatische Rückgabe des gestrichenen ESP-Projekts. Die Gartensensorik steht jetzt als **separates, optionales Hobbyprojekt** am Ende, nicht als Lieferumfang. |

### Akzeptanzkriterien

| # | Kriterium | Herkunft |
|---|---|---|
| **A1** | **Licht funktioniert zu 100 % am Wandtaster, auch wenn HA tot ist** | Vom Nutzer ausdrücklich gesetzt |
| A3 | Rollladen positionsgenau | Aus UC2 — mit Einschränkung, siehe Baustein 2 |
| A4 | PV-, Speicher- und WP-Daten lokal, ohne Hersteller-Cloud | Verfügbarkeit und Datenhoheit |
| A5 | Keine Bohrung/Schlitz in Wände, kein Neuverlegen von Leitungen | Bestandsgebäude, bewohnt |
| **(A2)** | HA kennt den echten Schaltzustand jedes Lichtkreises | **nur falls per O1 bestätigt** |

---

## 💡 Proposed Solution

### Die Kernaussage zuerst

> **Für alle vier Anwendungsfälle wird kein einziger selbst geschriebener Mikrocontroller-Code
> benötigt. Die ESP32/ESP-NOW-Ebene löst kein Problem, das du hast.**

Das ist die wichtigste Rückmeldung zu deinem Entwurf. Die unabhängige Prüfung hat gezielt versucht,
sie zu widerlegen, und sie hält. Unten steht, **wo** dein ESP-Know-how dagegen unersetzlich ist.

---

### Baustein 1 — Licht: Eltako bleibt, Shelly wird parallelgeschaltet

Der aufwendigste und einzige riskante Teil. In v1 enthielt er drei Fehler; hier die korrigierte Fassung.

#### Wie deine Anlage funktioniert

Die Wandtaster führen eine **Steuerleitung** in den Verteiler, die bei Tastendruck einen 230-V-Impuls
auf die **Spule (A1/A2)** des Stromstoßrelais gibt. Jeder Impuls **kippt** den Zustand. Alle Taster
eines Kreises liegen parallel auf derselben Steuerleitung.

#### Der Retrofit

Ein potentialfreier Kontakt wird **parallel zu den vorhandenen Tastern** aufgelegt. HA schließt ihn
für ~0,5 s → das Relais kippt. Die Wandtaster funktionieren unverändert weiter.

**Gerätewahl: Shelly Pro 2 — nicht Pro 2PM.** Hutschiene ist zwingend (zentraler Verteiler). Der
**Pro 2 hat potentialfreie Ausgänge, der Pro 2PM nicht** — mit „PM" im Namen braucht die
Leistungsmessung eine Spannungsreferenz
([Shelly KB Pro 2](https://kb.shelly.cloud/knowledge-base/shelly-pro-2-v1):
*„2-channel smart switch with potential-free contacts"*).
Elektrisch passt das zur Eltako-Spule: S12-100-230V zieht 5–6 W (~25 mA) bei **100 % Einschaltdauer**,
der 16-A-Kontakt ist weit überdimensioniert
([Eltako-Datenblatt](https://www.eltako.com/fileadmin/downloads/de/datenblatt/Datenblatt_S12-100-_200-_110-.pdf)).

Konfiguration: Eingang **`detached`**, Ausgang Impuls (Auto-Off ≈ 0,5 s),
**Power-On-State explizit `OFF`** — nicht „restore last", sonst pulst jede Netzwiederkehr alle Kreise.
Je Kanal ein **RC-Snubber**: Die Spule ist eine induktive Last, das Shelly-Handbuch empfiehlt das
ausdrücklich. Kostet Cent, gehört in die Stückliste.

#### ⚠️ Korrektur 1: Die SW-Eingänge sind **nicht** potentialfrei

v1 hat aus „potentialfrei" gefolgert, das Gerät sei phasenunabhängig. Das gilt nur für die **Ausgänge**.
Die **Schaltereingänge SW1/SW2 hängen an der Versorgungsphase des Geräts** — der Shelly schaltet dort
eine intern erzeugte Spannung zwischen SW und L
([Shelly-Forum](https://shelly-forum.com/thread/23394-sind-shelly-eingaenge-wirklich-potentialfrei/)).

Das ist keine Spitzfindigkeit, sondern trifft die Lösung im Kern: **Weg B führt die geschaltete
Lastader auf SW.** Liegt dieser Lichtkreis auf einer anderen Phase als die Shelly-Versorgung, ist das
genau die Phasenkollision, vor der v1 zwei Absätze vorher gewarnt hatte.

**Folge für die Planung:** Ein Pro 2 deckt zwei Lichtkreise nur, wenn **beide auf derselben Phase
liegen wie seine Versorgung**. Bei drei gemischt aufgeteilten Phasen ist das oft nicht gegeben.
Entweder nach Phase gruppieren (mehr Geräte) oder je Rückmeldung ein Koppelrelais/Optokoppler.
**→ Die Phasenzuordnung jedes Lichtkreises muss erhoben werden (O2), bevor die Stückzahl feststeht.**

#### ⚠️ Korrektur 2: A1 ist **bedingt** erfüllt, nicht strukturell

v1 behauptete, A1 sei strukturell erfüllt, weil bei totem HA kein Impuls mehr anliegt. Das betrachtet
nur den Ausfall von HA — nicht den des **Shelly im geschlossenen Zustand**, und der Shelly ist das
Bauteil, das neu in den Pfad kommt.

Bleibt der Kontakt geschlossen (verschweißt, Firmware-Hänger, Auto-Off-Timer nicht ausgeführt), liegt
**Dauerspannung auf der Spule**. Thermisch unkritisch (100 % ED). Aber: Der Wandtaster legt dieselben
230 V auf dieselbe, bereits erregte Spule — **kein neuer Impuls, kein Kippen**. Der Kreis ist
eingefroren, möglicherweise auf „aus". Eltako dokumentiert dieses Verhalten bei den Z-Typen sogar
als Feature: Bei dauerbestromtem Steuereingang ist je nach Drehschalterstellung *„lokales Schalten
wirkungslos"*.

Verschärfend: Der Auto-Off-Impuls ist ein **Software-Timer der Firmware**, keine Hardwareeigenschaft.
Und weil wir bewusst den Pro 2 **ohne** Messung wählen, kann HA einen klebenden Ausgang nicht einmal
erkennen — das ist der Preis der Potentialfreiheit und gehört ehrlich neben ihren Nutzen gestellt.

**Absicherungen:** Power-On-State `OFF` · Auto-Off zusätzlich serverseitig in HA überwachen ·
Plausibilitätsalarm, wenn ein Ausgang > 5 s geschlossen meldet · und vor allem Weg A, siehe unten.

#### ⚠️ Korrektur 3: Weg A löst A2 **nicht** — aber es löst etwas anderes

v1 nannte Weg A (Eltako-Z-Typen mit Zentral-Ein/Aus) die Wurzellösung für A2. Das war falsch.
Gerichtete Befehle beseitigen die Unsicherheit über **HA-eigene** Befehle. Drückt jemand den
**Wandtaster** — was A1 jederzeit erlauben muss — ändert sich der Zustand, ohne dass HA es erfährt.
Ein periodisches „AUS" zur Resynchronisation scheidet aus: Es löscht Licht, das jemand eingeschaltet hat.

**Nur Weg B erfüllt A2** — und zwar unabhängig davon, wie O3 ausgeht.

**Weg A ist trotzdem wertvoll, aber als A1-Absicherung.** Beim ES12Z geht der Shelly auf einen
**separaten Zentraleingang** statt auf die Tasterleitung. In den Drehschalterstellungen, in denen
dauerbestromte **lokale Taster Priorität** haben, killt ein hängender Zentraleingang den Wandtaster
**nicht** ([ES12Z-Bedienungsanleitung](https://www.eltako.com/fileadmin/downloads/de/_bedienung/es12z_4872_internet_dtsch.pdf)).
Das ist echte Einzelfehlersicherheit für A1 — und nur so zu haben.
*Vorbehalt: Die Drehschaltersemantik ist am konkret verbauten Typ im Original-Datenblatt
nachzulesen, bevor darauf gebaut wird.*

#### Die drei Wege, korrigiert

| Weg | Erfüllt A2? | Erfüllt A1 einzelfehlersicher? | Bewertung |
|---|---|---|---|
| **A** — Zentraleingänge (nur Z-Typen) | ❌ **nein** | ✅ ja, bei passender Drehschalterstellung | Nicht Ersatz für B, sondern **Ergänzung** |
| **B** — Rückmeldung über Lastleitung | ✅ **ja, als einziger** | ❌ nein | **Pflicht, falls O1 = ja.** Achtung Phase (O2) |
| C — Relais mit Rückmeldekontakt tauschen | ✅ ja | ❌ nein | Letzte Wahl, widerspricht „Bestand unangetastet" |

#### Kostenrahmen (korrigiert)

Shelly Pro 2 ≈ 45–55 €, **1 TE** je Gerät — 19 mm laut Shelly KB, nicht die in v1 behaupteten 2 TE.
Bei 10–14 Kreisen also ~6–7 TE statt 10–14; **O4 ist damit deutlich entspannter als in v1 dargestellt**.
Gegenläufig treibt die Phasengruppierung (O2) die Stückzahl. Grobrahmen **250–450 €** plus Snubber,
**ohne** Elektrikerlohn und ohne möglichen Zusatzverteiler.

> ⚠️ **Rechtlich, präziser als in v1:** **NAV § 13 Abs. 2** verlangt nicht „eine Elektrofachkraft",
> sondern dass Arbeiten *„nur durch ein in ein Installateurverzeichnis eines Netzbetreibers
> eingetragenes Installationsunternehmen"* ausgeführt werden. Eine Elektrofachkraft nach
> DIN VDE 1000-10 ist damit **nicht automatisch berechtigt** — der befreundete Elektriker genügt
> nicht zwingend. Planung, Auswahl, Konfiguration und die gesamte Software sind deine Arbeit.
>
> **Das gilt auch für die Bestandsaufnahme.** Um Typenschilder und freie TE zu erfassen, muss die
> Verteilerabdeckung ab — dahinter liegen berührbare, spannungsführende Klemmen. v1 hatte das als
> „30 Min" Nutzerhandlung geführt; das war die eine Stelle, an der das Dokument stillschweigend
> unqualifizierte 230-V-Nähe eingeladen hat. **Bestandsaufnahme gehört in den Elektrikertermin** —
> dort wird ohnehin die Phasenzuordnung (O2) gebraucht.

---

### Baustein 2 — Rollladen: Shelly 2PM, per WLAN

Hier ist „PM" erwünscht: Die Leistungsmessung erkennt die Endlagen (Motor fällt an den Endschaltern
auf ~0 W), womit der Shelly die Fahrzeit kalibrieren kann.

**Einschränkung zu A3, die v1 verschwiegen hat:** Die Position ist eine **Zeitinterpolation nach
Kalibrierung, keine Messung**. Sie driftet und muss periodisch nachkalibriert werden; Voraussetzung
ist zudem eine Mindestleistung des Rohrmotors (~4 W), sonst schlägt die Kalibrierung fehl. Für
Beschattung reicht das. „Positionsgenau" verspricht mehr, als die Technik liefert.

#### ⚠️ Beim Rollladen gibt es **kein A1-Äquivalent** — das ist eine Entscheidung

v1 hat das verschwiegen, obwohl es dieselbe Eigenschaft beim Licht zum zentralen Verwerfungsgrund
einer Alternative macht. Ehrlich gesagt:

Parallel geht beim Rollladen **nicht**. Lägen Shelly und Bestandsrelais parallel, könnten beide
gleichzeitig Auf und Ab anlegen — Gleichzeitigkeit **über zwei Geräte hinweg**, die die
geräteinterne Verriegelung des Roller-Modus nicht verhindern kann. Der 2PM muss die Bestandsrelais
**ersetzen**, die vorhandenen Schalter kommen auf SW1/SW2.

**Folge: Stirbt der Shelly 2PM, bewegt sich dieser Rollladen gar nicht mehr — auch nicht am
Wandschalter.** Das ist vertretbar (ein stehender Rollladen ist kein dunkles Treppenhaus), aber es
ist eine bewusste Abweichung vom A1-Prinzip und muss als solche entschieden werden.

#### Kein Zigbee für die Rollläden

Der 2PM Gen4 kann Zigbee, aber **nur ein Profil gleichzeitig** (Umschaltung per fünfmaligem
Tastendruck, [Shelly KB](https://kb.shelly.cloud/knowledge-base/shelly-2pm-gen4)). Im Zigbee-Profil
verlierst du die native Shelly-Integration mit lokalem RPC-Zugriff und gewinnst nichts: Das Gerät
sitzt fest im Verteiler und hat Dauerstrom. Zigbees Stärken — Batterie, Repeater-Reichweite — sind
für ein netzgespeistes Hutschienengerät irrelevant.

---

### Baustein 3 — PV, Speicher, Wärmepumpe: hier ist nichts zu bauen

Der Teil mit dem besten Verhältnis aus Wert und Aufwand. **Deshalb steht er in der Reihenfolge vorn.**

| Quelle | Weg | Aufwand |
|---|---|---|
| **Fronius + BYD** | **Native HA-Integration** über die Solar API im LAN ([HA-Doku](https://www.home-assistant.io/integrations/fronius/)). BYD-Daten kommen **über den Wechselrichter**. Bei GEN24 ab FW 1.14.1 „Solar API" im Web-UI aktivieren | **~20 Min** |
| **Fronius Steuerung** (Speicher laden/sperren) | Modbus TCP + Custom Component, u. a. gegen Symo GEN24 + BYD Battery-Box Premium HV verifiziert ([redpomodoro/fronius_modbus](https://github.com/redpomodoro/fronius_modbus)); setzt „Wechselrichtersteuerung über Modbus" voraus | Optional, später |
| **iDM Wärmepumpe** | **Modbus TCP, Port 502, Unit ID 1** | **~1 h**, falls Navigator 2.0 |

#### Freischaltung (korrigiert — v1s „Smartfox"-Angabe war unbelegt)

Die iDM-Unterlage erwähnt **kein** Smartfox. Der dokumentierte Weg ist:
**Hauptmenü „Einstellungen" → „Gebäudeleittechnik" → „Modbus TCP" auf „Ein"** — in der
**Heizungsbauer- bzw. Serviceebene**, also ggf. Sache deines Installateurs.

#### Registerzugriff (korrigiert — v1s Regel war falsch)

v1 behauptete, Navigator 2.0 nutze `read_input_register` und 1.7 `read_holding_register`. Das ist
falsch **und widersprach v1s eigener Angabe**, Register 74 sei ein Holding Register. Die
Unterscheidung ist **RO gegen RW innerhalb derselben Generation**. Aus der Originalunterlage
**812170 Rev. 10** (Stand 20.04.2022, Softwareversion 20.21-101):

| Datentyp | Befehl | Hinweis |
|---|---|---|
| `FLOAT (RO)` | **4 — Read Input Register** | Abfragezyklus 60 s |
| `FLOAT (RW/RO)` | **16 — Preset Multiple Register** | **„Zyklisch senden: 60 Sekunden"** |
| `UCHAR (RW/RO)`, `BOOL` | **6 — Preset Single Register** | |

**Register 74 ist `FLOAT RW/RO`** → also Holding Register, FC 16. Hätte man v1s Regel gefolgt, wäre
der erste Zugriff auf 74 fehlgeschlagen.

#### Der eigentliche Gewinn: PV-Überschuss an die Wärmepumpe

Aus der Unterlage, Abschnitt 4.3.9 — Adresse 74 (`FLOAT RW/RO`, „Aktueller PV-Überschuss" [kW]),
Adresse 4122 (`FLOAT RO`, „Aktuelle Leistungsaufnahme Wärmepumpe"):

> *„Sobald der PV-Überschuss höher ist als die Aufnahmeleistung startet die Wärmepumpe und
> bewirtschaftet das System laut den Einstellungen vom PV-Menü."*

Fronius meldet Überschuss → HA schreibt nach 74 → die Wärmepumpe verheizt ihn, statt ihn für ~8 ct
einzuspeisen. **Reine Software, null Hardware.**

#### Und was v1 dabei übersehen hat — das ist wichtiger als der Rest

**1. Zyklische Schreibpflicht + Watchdog.** RW-FLOATs sind laut Unterlage **alle 60 s zu senden**.
Eine einmalige „bei Änderung schreiben"-Automatisierung reicht nicht. Der gefährliche Fall:

> HA stirbt um 15 Uhr bei 4 kW Überschuss. Der letzte Wert bleibt stehen. Die Wärmepumpe „sieht"
> die ganze Nacht 4 kW Überschuss und heizt Warmwasser und Puffer **aus dem Netz** hoch.

Das ist das exakte ökonomische Gegenteil des Anwendungsfalls, und ohne Watchdog ein Dauerzustand bis
zum Bemerken. **Pflicht:** zyklischer Schreibtask ≤ 60 s · `0` schreiben beim HA-Shutdown ·
Plausibilitätsgrenze · Alarm, wenn 74 länger als X Minuten nicht aktualisiert wurde.
**Stufe 1 ist damit nicht „null Risiko", sondern „null 230-V-Risiko".** Das ist ein Unterschied.

**2. 15 s Totzeit.** Die Unterlage direkt unter dem PV-Block: *„Die Aktualisierung der Parameter
erfolgt zyklisch, dies kann dazu führen, dass sich Änderungen zeitverzögert (ca. 15 sec) auswirken!"*
Ein naiv getakteter Regelkreis schwingt.

**3. Die Rangfolge nicht selbst nachbauen.** v1 nannte „Hausverbrauch → Batterie → Wärmepumpe"
kritisch, ohne ein Mittel zu nennen. Die Unterlage hat es direkt neben Register 74 stehen:

| Adresse | Typ | Bedeutung |
|---|---|---|
| **82** | `FLOAT RW/RO` | Hausverbrauch [kW] |
| **84** | `FLOAT RW/RO` | Batterieentladung [kW] |
| **86** | `WORD RW/RO` | Batteriefüllstand [%] |

Speist man diese drei aus dem Fronius mit, **macht die iDM-eigene PV-Logik die Priorisierung selbst**.
Weniger Code und robuster gegen HA-Ausfall, als sie in einer HA-Automatisierung nachzubilden.

**4. EEPROM — Entwarnung mit Vorbehalt.** Die Unterlage warnt, dass mit `*` markierte Register
*„direkt in den EEPROM-Speicher"* geschrieben werden und permanente Änderungen ihn zerstören können
(**max. 300.000 Schreibzyklen**). **74, 82, 84 und 86 tragen diese Markierung nicht** — zyklisches
Schreiben ist unbedenklich. Relevant wird es, sobald du später Betriebsarten- oder
Solltemperaturregister automatisierst.

#### Integrationswahl (korrigiert)

| Repo | Stand | Eignung |
|---|---|---|
| [**kodebach/hacs-idm-heatpump**](https://github.com/kodebach/hacs-idm-heatpump) | 47 ★, 299 Commits, aktiv | **Erste Wahl.** Setzt Navigator 2.0 voraus |
| [Xerolux/idm-heatpump-hass](https://github.com/Xerolux/idm-heatpump-hass) | 5 ★ | Alternative; Navigator 2.0/10/Pro. README: *„Use at your own risk — especially when writing Modbus registers."* |

v1 hatte die Reihenfolge umgekehrt und „169+ Entities" behauptet — die Zahl steht in keinem README.

**Der Zweig, der in v1 fehlte:** Ist die Anlage ein **Navigator 1.7**, ist **keine** der beiden
Integrationen einsetzbar. Dann bleibt generisches Modbus-YAML in HA. Die Schätzung „~1 h" gilt nur
für den günstigen Ausgang von **O5**.

---

### Baustein 4 — Zukünftige Leuchten: Entscheidung vertagen

v1 wollte hier einen Zigbee-Coordinator kaufen. Die Prüfung hat zu Recht beanstandet, dass das eine
**Protokollfestlegung ist, bevor die erste Leuchte existiert** — sie könnte genauso gut
Matter-over-Thread oder WLAN sein. Gekauft wird, wenn die Leuchte da ist.

**Was heute trotzdem nötig ist: der Kanalplan.** WLAN, Zigbee und (eventuell später) ESP-NOW teilen
sich das 2,4-GHz-Band. Festes WLAN auf Kanal 1 und Zigbee auf 25 (oder 11 / 15) ist die übliche
kollisionsarme Paarung. Wer das erst macht, wenn 20 Geräte hängen, sucht Wochen nach Aussetzern.

---

### Baustein 5 — Die ESP-Ebene: drei Korrekturen und eine Einordnung

Dein Entwurf sieht ESP32 per ESP-NOW als Mesh vor, in MicroPython („Microsoft Python" nehme ich als
Vertipper).

**1. ESP-NOW ist kein Mesh.** Es ist Peer-to-Peer, ein Hop. Grenzen laut
[Espressif-API-Referenz](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/api-reference/network/esp_now.html):
**maximal 20 gepaarte Geräte insgesamt, davon verschlüsselt höchstens 17, Default 7**
(`CONFIG_ESP_WIFI_ESPNOW_MAX_ENCRYPT_NUM`). *v1 schrieb „20 unverschlüsselt / 10 verschlüsselt" —
das stammt aus einer älteren FAQ-Formulierung.* Was du vermutlich meinst, ist ESP-WIFI-MESH oder
painlessMesh — andere Protokolle.

**2. ESP-NOW erreicht HA nie direkt.** Es braucht **immer einen Gateway-Knoten**, der per WLAN
weitergibt. ESPHome hat dafür eine offizielle [`espnow`-Komponente](https://esphome.io/components/espnow/).
Zwei Fallstricke: Sie **implementiert keine Verschlüsselung** (dafür die
[Packet Transport Platform](https://esphome.io/components/packet_transport/espnow/)), und *„Cannot be
set when Wi-Fi is used, as ESP-NOW will use the same channel as the Wi-Fi network"* — der Gateway
hängt auf dem Kanal deines Access Points, nicht auf einem ruhigen.

**3. MicroPython → ESPHome.** Keine Bevormundung, eine Rechnung: Mit MicroPython schreibst du
MQTT-Client, HA-Discovery, OTA, Reconnect und Watchdog selbst — für Geräte, an denen das Licht deiner
Familie hängt. ESPHome liefert das, generiert C++ aus YAML und bindet nativ verschlüsselt an HA an.
Eigenes C++ kannst du per `lambda` und Custom Components jederzeit einhängen; du gibst Boilerplate
auf, keine Tiefe.

**4. Einordnung: In keinem deiner vier Anwendungsfälle brauchst du das.**

| Anwendungsfall | ESP32? | Warum nicht |
|---|---|---|
| Licht Haus + Garten | ❌ | Shelly Pro 2 im Verteiler, netzgespeist, WLAN da |
| Rollladen | ❌ | Shelly 2PM |
| PV + Speicher | ❌ | native Integration, kein Gerät |
| Wärmepumpe | ❌ | Modbus TCP über LAN |

ESP-NOWs Stärken — Batteriebetrieb, Millisekunden-Latenz, Funktion ohne Access Point — zahlen auf
keinen dieser Fälle ein.

---

### Separates, optionales Projekt — nicht Teil dieses Konzepts

In v1 stand das als „Stufe 6" im Lieferumfang und stützte sich auf das erfundene A6. Ehrlicher ist:
**Das hier ist ein eigenständiges Hobbyprojekt**, das mit der Hausautomation nichts zu tun hat außer
dem gemeinsamen HA. Es steht hier, weil es der Ort ist, an dem dein Löteisen tatsächlich gewinnt:

- Bodenfeuchte-, Regen-, Temperatursensoren im Garten, **batteriebetrieben, kein Netzanschluss** —
  genau hier schlägt ESP-NOW WLAN deutlich: Deep-Sleep-Aufwachen und Senden in Millisekunden statt
  Sekunden für WLAN-Assoziation und DHCP, also Laufzeiten von Monaten statt Wochen
- Zisternen-/Füllstandsmessung
- Sensorik am Grundstücksrand außerhalb der WLAN-Abdeckung
- Alles, wofür es kein Fertigprodukt gibt — der eigentliche Grund, selbst zu bauen

---

### Zentrale

HA braucht **Dauerlauf-Hardware mit SSD statt SD-Karte** — sobald PV- und WP-Langzeitdaten
geschrieben werden, läuft die Datenbank permanent, und SD-Karten sterben daran nach 1–2 Jahren.

v1 hat daraus einen **Mini-PC-Kauf** abgeleitet. Die Prüfung hat zu Recht angemerkt: Das Argument
richtet sich gegen **SD-Karten**, nicht gegen vorhandene Hardware. Existiert ein NAS — und v1 setzte
eins voraus („Backup auf ein NAS ab Tag 1") — tut ein Container darauf oder ein Pi mit SSD dasselbe.
**Erst prüfen, was da ist; kaufen nur, wenn nichts passt.** Automatisches Backup ab Tag 1.

---

### Reihenfolge

| Stufe | Inhalt | Aufwand | Warum hier |
|---|---|---|---|
| **0** | HA auf vorhandener Dauerlauf-Hardware, Backup, WLAN-Kanalplan | 1 Abend | Fundament, ohne Kauf |
| **1** | **Fronius + iDM lesend anbinden** | 1 Abend | Null 230-V-Risiko |
| **2** | **PV-Überschuss → Register 74, mit Watchdog** + 82/84/86 mitspeisen | 1 Abend | Höchster Euro-Gegenwert. **Erst lesen und mitprotokollieren, dann schreiben** |
| **3** | **O1 entscheiden:** brauchst du Automatiken, also A2? | Gespräch | Entscheidet, ob Baustein 1 groß oder klein wird |
| **4** | **Elektrikertermin: Bestandsaufnahme** — Eltako-Typen, freie TE, **Phasenzuordnung je Kreis** | mit Fachbetrieb | Liefert O2–O4 |
| **5** | Ein Lichtkreis als Pilot (Pro 2 + Weg B, ggf. Weg A) | 1 Tag | Validieren vor Skalieren |
| **6** | Weitere Lichtkreise — **nur die mit echtem Automatikbedarf** | nach Pilot | s. u. |
| **7** | Rollläden — **nur die mit Beschattungsbedarf** | | |
| **8** | Neue Leuchten: Protokoll entscheiden, dann kaufen | bei Bedarf | |

**Zu Stufe 6/7 — eine Streichung aus der Prüfung, die ich übernehme:** v1 hat „restliche Lichtkreise"
als Default geführt. Bei erfülltem A1 ist der Grenznutzen des neunten Lichtkreises nahe null — der
Wandtaster funktioniert ja. Das ist der teuerste und einzige riskante Teil des Projekts und gehört
**pro Kreis gegen seinen Nutzen gerechnet**, nicht pauschal ausgerollt. Kandidaten mit echtem Nutzen:
Außenlicht (Astro-Timer), Flur, „alles aus" beim Verlassen.

---

## ⚖️ Trade-offs & Alternatives

### Verworfen: KNX nachrüsten

Der „richtige" Weg — Aktoren in den Verteiler, Busleitung zu jedem Taster. Scheitert an A5: Ohne
Leerrohre bedeutet das Schlitzen im bewohnten Haus. Vier- bis fünfstellig, ohne den vier
Anwendungsfällen etwas hinzuzufügen.

### Verworfen: Eltako komplett durch Shelly ersetzen

Technisch sauberer — Status geschenkt, kein Toggle-Problem, keine Phasenfrage bei SW. Scheitert an
**A1**, das du ausdrücklich gesetzt hast. Dass eine Anforderung die elegantere Lösung ausschließt,
macht sie nicht falsch: Eine Lichtsteuerung, die von einem selbst gewarteten Server abhängt, ist im
Familienbetrieb der häufigste Grund für Rückbau.

### Verworfen: Eltako EnOcean-Nachrüstung

Naheliegend wegen des gleichen Herstellers. Verworfen, weil es ein **drittes Funkprotokoll** mit
eigenem Gateway einführt, bei kleinerem Ökosystem und höheren Preisen — ohne A1 oder A2 besser zu
lösen als der Parallelkontakt.

### Beibehalten und begründet: WLAN als Aktor-Transport

Der berechtigte Einwand: 15–20 WLAN-Geräte belasten das 2,4-GHz-Band, und ein Router-Neustart nimmt
die halbe Automation mit. Beides stimmt.

Trotzdem WLAN: Die Geräte sind **netzgespeist und ortsfest** — der Hauptgrund für Zigbee entfällt.
Die native Shelly-Integration arbeitet **lokal über RPC**, nicht über Cloud. Und bei erfülltem A1 ist
ein WLAN-Ausfall **kein Lichtausfall**, sondern ein Automatikausfall. Gegenmaßnahme: eigene SSID auf
festem Kanal, DHCP-Reservierungen, Access Point an der USV.

### Die stärkste Gegenposition zu diesem Konzept

> *„Du redest dem Nutzer sein eigenes Projekt aus. Er wollte eine selbstentwickelte Hausautomation
> mit ESP32 — und bekommt eine Einkaufsliste."*

Ernstzunehmen, teilweise berechtigt. Zwei Teile der Antwort.

**Zum Ziel:** In der Aufgabenstellung stehen vier Anwendungsfälle und die Bitte um kritisches
Feedback. „Selbst entwickelt" steht dort als **Lösungsweg**, nicht als Ziel. Zwischen beidem zu
unterscheiden ist genau das, worum gebeten wurde. Wäre „möglichst viel selbst bauen" das eigentliche
Ziel, sähe dieses Konzept anders aus — siehe **O7**.

**Zur Sache:** Das Konzept streicht den Eigenbau nicht, es verschiebt ihn dorthin, wo er gewinnt.
An der Deckenlampe konkurriert er mit einem zertifizierten 25-€-Modul und verliert. Am
batteriebetriebenen Gartensensor gibt es kein gleichwertiges Fertigprodukt. Und die
Energieautomatisierung aus Baustein 3 — zyklisches Schreiben mit Watchdog, Rangfolge über 82/84/86,
Regelkreis mit 15 s Totzeit — ist **nicht-triviale Software**, die es fertig nicht gibt und die Geld
spart. Da steckt mehr Ingenieursarbeit drin als in einem selbstgeschriebenen MQTT-Client.

Restverlust, ehrlich: Wer **über** das Projekt ESP32 und Funkprotokolle lernen will, lernt beim
Zusammenklicken von HACS-Integrationen weniger. Hat das Lernziel Priorität, zieh das Gartenprojekt
vor — aber am Gartensensor, nicht am Treppenhauslicht.

---

## ❓ Open Questions

| # | Frage | Warum es zählt | Wie zu klären |
|---|---|---|---|
| **O1** | **Willst du Automatiken — also brauchst du A2?** | Entscheidet, ob Baustein 1 ein Rückmeldeprojekt wird oder ein simpler Impulsgeber. Größter Kostenhebel im Konzept | **Deine Entscheidung.** In v1 war das eine stille Annahme |
| **O2** | **Auf welcher Phase liegt jeder Lichtkreis, und auf welcher die Shelly-Versorgung?** | Weg B braucht SW und L auf derselben Phase. Bestimmt Gerätezahl und Kosten. **In v1 komplett übersehen** | Elektrikertermin |
| **O3** | **Haben die Eltako-Relais Zentralsteuereingänge („Z")?** | Nicht für A2 (Korrektur 3), sondern für **A1-Einzelfehlersicherheit** | Typenschilder, im Elektrikertermin |
| **O4** | Wie viele TE sind frei? | 1 TE je Gerät (nicht 2). Reicht es nicht: Zusatzverteiler, relevante Kosten | Elektrikertermin |
| **O5** | **Navigator-Generation (1.7 / 2.0 / 10.0)?** | Bei 1.7 ist **keine** der HACS-Integrationen nutzbar → generisches Modbus-YAML | Web-UI / Serviceebene |
| **O6** | Ist Modbus TCP freigeschaltet? | Einstellungen → Gebäudeleittechnik → Modbus TCP = Ein, in der Serviceebene | ggf. Installateur |
| **O7** | **Ist „selbst entwickeln" Mittel oder Ziel?** | Bei „Ziel" ist dieses Konzept falsch gewichtet | Deine Entscheidung |
| **O8** | Gartenlichter über den Hausverteiler oder separat? | Falls separat, erster echter ESP-Anwendungsfall | Vor Ort |
| **O9** | Wie viele Lichtkreise und Rollläden **mit echtem Automatikbedarf**? | Nicht „wie viele gibt es" — s. Stufe 6/7 | Deine Entscheidung |

### Grenzen der Evidenz

- **Geprüft gegen Primärquelle** (iDM 812170 Rev. 10, Volltext extrahiert): Register 74 / 82 / 84 / 86,
  Funktionscodes je Datentyp, 60-s-Zyklus, 15-s-Totzeit, EEPROM-`*`-Markierung, Freischaltpfad.
  Gültig für **Softwareversion 20.21-101, Stand 20.04.2022** — bei abweichender Version verifizieren.
- **Ungeprüft am konkreten Objekt:** verbaute Eltako-Typen (O3), Drehschaltersemantik am konkreten
  Typ, Phasenzuordnung (O2), freie TE (O4), Navigator-Generation (O5).
- **Schwach belegt:** Ob die native Fronius-Integration bei *deiner* GEN24/BYD-Kombination ein
  SoC-Entity anlegt. Die HA-Doku listet für Storage *current, voltage, state, cycle count, capacity* —
  **SoC wird nicht namentlich genannt**. Wahrscheinlich, aber nicht dokumentarisch belegt.
- **Nicht spezifiziert:** Mindestschaltlast des Shelly-Relais bei ~5,75 VA Spulenlast. Bei
  AgSnO₂-Leistungsrelais unkritisch, aber unbelegt.
- **Offen:** Ob die iDM intern ein undokumentiertes Timeout auf Register 74 hat. Die Unterlage
  schweigt — genau deshalb nicht annehmen, sondern Watchdog bauen.
- Preise sind Größenordnungen, keine Angebote. Elektrikerlohn ist **nicht** enthalten.

---

## 🔍 Review

**Konfiguration:** `.sde_docs/config` nicht vorhanden. Default `adversarial_review: ask` angewendet;
der Nutzer hat die unabhängige Prüfung am 2026-09-20 ausdrücklich bejaht.

**Tatsächlicher Review-Modus:** Separater Subagent mit frischem Kontext (`sde-agent`), eigene
Primärquellenrecherche.

> ⚠️ **`reviewer_model: same-model-fallback`.** Der Reviewer war Claude Opus 5 — **dasselbe Modell wie
> der Autor**. Die Prüfung ist damit **nicht modellunabhängig**. Die gefundenen Fehler sind
> überwiegend solche, die sich gegen Primärdokumente auflösen ließen (Registerzugriffsart, TE-Breite,
> Peer-Zahlen, NAV-Wortlaut) — genau die Klasse, die ein gleiches Modell noch findet. Die Klasse, die
> es systematisch **nicht** findet, sind geteilte Denkgewohnheiten. Dass R1 (Weg A löst A2 nicht)
> gefunden wurde, garantiert nicht, dass es keine weiteren gibt.
>
> **Für Baustein 1 ist vor der Bestellung ein Blick von jemandem mit Elektroinstallationspraxis mehr
> wert als eine zweite LLM-Runde.** Das ist die einzige Stelle, an der dieses Konzept eine
> menschliche Gegenprüfung ausdrücklich empfiehlt.

**Verdikt der Prüfung:** `REVISE`

### Befunde und Disposition

| # | Befund | Disposition |
|---|---|---|
| **SCOPE** | A2 und A6 waren erfundene Akzeptanzkriterien | ✅ **übernommen.** A6 gestrichen, Gartensensorik als separates Projekt ausgelagert. A2 zu **O1** umgewandelt |
| SCOPE | Zigbee-Coordinator ist Vorabfestlegung | ✅ **übernommen** — Kauf vertagt, Kanalplan behalten |
| SCOPE | Mini-PC-Kauf aus SD-Karten-Argument hergeleitet | ✅ **übernommen** — erst vorhandene Hardware prüfen |
| SCOPE | „Restliche Lichtkreise" als Default | ✅ **übernommen** — pro Kreis gegen Nutzen gerechnet (Stufe 6/7, O9) |
| SCOPE | Dreiteiliger A2-Weg ist Scheinauswahl | ✅ **übernommen** — Tabelle zeigt jetzt, dass nur B A2 erfüllt |
| **R1** | Weg A löst A2 nicht | ✅ **übernommen**, Logikfehler. Weg A neu begründet (A1) |
| **R2** | Shelly-SW-Eingänge nicht potentialfrei | ✅ **übernommen**, unabhängig verifiziert. Neue **O2** |
| **R3** | A1 nicht strukturell erfüllt (klebender Kontakt) | ✅ **übernommen**, Anspruch abgeschwächt, Absicherungen ergänzt |
| **R4** | Rollladen ohne A1-Äquivalent; A3 ist Zeitinterpolation | ✅ **übernommen**, beides explizit gemacht |
| **R5** | Registerzugriffsregel falsch | ✅ **übernommen**, gegen Original verifiziert |
| **R6** | Zyklische Schreibpflicht, kein Watchdog, „null Risiko" | ✅ **übernommen** — der wertvollste Befund. Inkl. 82/84/86-Vorschlag |
| **R7** | 1 TE statt 2; RC-Snubber fehlt | ✅ **übernommen** |
| **R8** | HACS-Reihenfolge, „169+" unbelegt, 1.7-Zweig fehlt | ✅ **übernommen** |
| **R9** | ESP-NOW-Peer-Zahlen veraltet | ✅ **übernommen** |
| **R10** | NAV § 13 schärfer; Bestandsaufnahme lädt 230-V-Nähe ein | ✅ **übernommen**, Bestandsaufnahme in den Elektrikertermin verschoben |
| — | „Smartfox"-Einstellung unbelegt | ✅ **übernommen**, durch dokumentierten Pfad ersetzt |

**Vom Reviewer geprüft und bestätigt (keine Änderung nötig):** Kernaussage „kein MCU-Code für UC1–4" ·
Vorziehung von Baustein 3 · kein Zigbee für Hutschienengeräte · Pro 2 dry contacts vs. Pro 2PM ·
elektrische Eignung des Impulses an der Eltako-Spule · Register 74 schreibbar und nicht
EEPROM-markiert · ESPHome-`espnow` ohne Verschlüsselung und kanalgebunden · ESP-NOW ist kein Mesh ·
2PM Gen4 ein Profil zur Zeit · Verwerfung von KNX, Eltako-Ersatz und EnOcean.

**Autorenauflösung, kein reviewer-erteiltes PASS.** Alle `REVISE`-Befunde sind aufgelöst; eine
Nachprüfung der Version 2 hat nicht stattgefunden.

**Verbleibende Unsicherheit:** Baustein 1 hängt an O1–O4, die alle Vor-Ort-Erhebungen sind. Das
Konzept gibt Baustein 1 **nicht zur Bestellung frei**; die Stufen 0–2 sind unabhängig davon
umsetzbar.
