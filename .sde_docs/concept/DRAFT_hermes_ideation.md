📌 **Status:** DRAFT

## 🎯 Problem Statement
Der Prozess, profitable Business-Ideen, Trends und Marktlücken zu finden, ist extrem zeitaufwändig. 
Die Zielsetzung ist es, einen "Always-On" Agenten (Hermes) zu bauen, der kontinuierlich das Web (Reddit, HackerNews, ProductHunt) nach neuen Problemen und Trends durchsucht, daraus Business-Ideen generiert und diese **in der Tiefe bewertet**.
Da das bestehende SDE-Framework bereits mächtige Workflows für Deep-Research und Konzept-Entwicklung (`sde-concept`, `sde-research`) bietet, soll Hermes diese nutzen, anstatt eine eigene komplexe Analyse-Logik (inkl. Error-Handling und Subagenten) von Grund auf neu zu implementieren. Am Ende soll ein täglicher "Daily Digest" mit den vielversprechendsten Ideen präsentiert werden.

## 💡 Proposed Solution: Hermes als Orchestrator + SDE als Backend

Das System wird nach dem Prinzip der **Separation of Concerns** in zwei Schichten geteilt:

### 1. Der Orchestrator (Hermes)
Hermes ist ein leichtgewichtiges Python-Skript (idealerweise orchestriert via `cron` oder als Systemd Daemon), das primär für **Breite und Rhythmus** zuständig ist.
* **Trend-Scraping:** Hermes nutzt Aggregator-APIs (wie SocialCrawl oder Apify Actors), um täglich Top-Posts von Reddit (z.B. r/SaaS, r/Entrepreneur), HackerNews und ProductHunt abzurufen.
* **Filter & Ideation (LLM-Pass 1):** Hermes nutzt ein schnelles Modell (z.B. Gemini Flash), um aus den hunderten Posts die 3-5 stärksten "Pain Points" zu extrahieren und in rohe Business-Ideen zu übersetzen.
* **Delegation:** Hermes nutzt das **Antigravity Python SDK** (oder einfache `subprocess.run` CLI Calls), um für jede der Top-Ideen einen isolierten SDE-Workflow zu triggern.

### 2. Die Ausführungs-Maschine (SDE)
Für jede Idee ruft Hermes den SDE-Agenten auf:
`agy --mode plan --print "Führe sde-concept aus: Erstelle ein Konzept zur Business-Idee X. Bewerte explizit: 1. Monetarisierbarkeit, 2. Technische Machbarkeit (Solo-Dev), 3. Konkurrenzdichte."`
* **Deep Work:** SDE übernimmt. Es nutzt seine eigenen Subagenten (`sde-research`), um das Web nach Konkurrenten zu scannen, Pricing-Modelle zu prüfen und ein tiefes, standardisiertes Markdown-Dokument (`.sde_docs/concept/DRAFT_[Idee].md`) zu generieren.

### 3. Synthese & Daily Digest
* Hermes wartet, bis die SDE-Prozesse abgeschlossen sind.
* Da SDE deterministische, strukturierte Markdown-Dateien liefert, liest Hermes diese Dateien aus dem Dateisystem ein.
* Hermes vergleicht die Ergebnisse, wählt den Gewinner aus und generiert den **Daily Digest** (Versand via Telegram/Mail/Terminal).

## ⚖️ Trade-offs & Alternatives

* **Verworfener Ansatz:** *Monolithischer In-Memory Agent.* Ein einziger endlos laufender Agenten-Loop, der scrapt, denkt, googelt und am Ende ausgibt.
  * *Rationale für Verwerfung:* Zu hohes Risiko für Context Window Bloat und Halluzinationen. Wenn ein Agent in einem Prompt 50 Reddit-Posts liest und gleichzeitig eine tiefe Konkurrenzanalyse machen soll, sinkt die Präzision drastisch. Das SDE-Framework (`sde-concept`) erzwingt durch seinen iterativen Generate→Critique→Synthesize-Loop und den Subagenten-Einsatz eine viel höhere Qualität.

* **Trade-off:** *Latenz und Token-Kosten.* Da für jede Idee ein kompletter SDE-Prozess inkl. Research-Subagenten gestartet wird, dauert die Analyse länger und verbraucht mehr API-Kosten als ein oberflächlicher Prompt.
  * *Mitigation:* Hermes muss als rigoroser Filter agieren (Phase 1) und darf maximal die Top 2-3 Ideen pro Tag an das SDE-Backend übergeben.

## 📋 Open Questions

1. **APIs für Hermes:** Sollen wir für das initiale Scraping offizielle APIs (Algolia für HackerNews) oder Managed Scraper (wie Apify) nutzen?
2. **Integration:** Willst du Hermes als pures Bash-Skript bauen, das `agy` aufruft, oder lieber das `antigravity-sdk-python` nutzen, um die SDE-Agenten programmatisch zu steuern?
3. **Review-Prozess:** Sollen die erstellten SDE-Konzepte als `DRAFT` im System liegen bleiben, bis du sie manuell überprüfst, oder soll Hermes sie nach dem Daily Digest automatisch archivieren, wenn sie durchfallen?
