# 🧰 EMD Custom Skills

Sammlung individueller AI-Skills für Business-Workflows.
Optimiert für **LibreChat**, **MIA**, ChatGPT, Claude und Gemini.

---

## 📦 Verfügbare Skills

### 🗂️ [`transkript-zusammenfassung`](./transkript-zusammenfassung/) (v3.1.0)

Strukturierte Zusammenfassungen von **Mitarbeiter- und Führungskräfte-Gesprächen**,
1:1s, Team-Meetings und Strategie-Sessions — angereichert durch automatische
Kontext-Recherche in **Qlik** (Wissensdatenbank) und dem gesamten
**Microsoft-365**-Ökosystem (Outlook, Teams, OneDrive, SharePoint, Excel,
Planner, OneNote) über die jeweiligen MCP-Server (Read-Only).

**Features:**
- 🇩🇪 Deutsch, XML-strukturierter System-Prompt (robust über Claude/GPT/Gemini)
- 🧠 Selbstgesteuerte Tool-Auswahl (Agent entscheidet, wann Lookup sinnvoll ist)
- 📋 Expliziter 6-Schritt-Workflow mit mentalem Budget-Tracking
- 🔍 Multi-MCP: Qlik + Microsoft 365 gleichzeitig
- 🛡️ Read-Only, DSGVO-konform
- 📊 Lookup-Budget: max. 8 Tool-Calls pro Transkript (12 mit „Tief recherchieren")
- 🎯 Glossar-First-Prinzip für KPIs/Begriffe
- 🗑️ Filtert ASR-Müll & Smalltalk automatisch
- 🧩 Entscheidungsbaum: welcher MCP für welche Frage
- ✅ Self-Check-Checkliste vor jeder Ausgabe
- 🔍 Few-Shot-Beispiele inline (ASR-Müll, Lookup, Disambiguation)
- 🏭 Pöppelmann-Kontext eingebaut (KAPSTO / K-TECH / FAMAC / TEKU + Initiativen)
- 🎚️ Spezial-Modi: HR-Akte / Konflikt-Analyse / Nur To-dos / Entwicklungsplan / …

**Dateien:**
- [`SKILL.md`](./transkript-zusammenfassung/SKILL.md) — Hauptdatei mit System-Prompt
- [`MCP-TOOLS-REFERENCE.md`](./transkript-zusammenfassung/MCP-TOOLS-REFERENCE.md) — Komplette Tool-Liste
- [`examples/beispiel-teams-meeting.txt`](./transkript-zusammenfassung/examples/beispiel-teams-meeting.txt) — Beispiel zum Testen

---

## 🚀 Verwendung

1. `SKILL.md` öffnen
2. **System-Prompt-Block** (im Codeblock unter „👤 System-Prompt") kopieren
3. In LibreChat / MIA als Custom-Agent einfügen
4. Modell-Einstellungen aus der Tabelle übernehmen
5. **Qlik-MCP + Microsoft-365-MCP** im Agent aktivieren (Read-Only)
6. Transkript in den Chat packen → fertig

---

## 📄 Lizenz

MIT — frei nutzbar, Anpassungen erwünscht.

## 🙏 Credits

- [BrassTranscripts AI Prompts](https://github.com/CopperSunDev/brasstranscripts-ai-prompts) — Inspiration für Transkript-Skills
- [AI-meeting-assistant](https://github.com/ajanm007/AI-meeting-assistant) — Map-Reduce-Pattern
