# 🔌 MCP-Tools-Referenz

Vollständige Liste der **Read-Only**-Tools, die der Agent nutzen darf.

---

## 📊 Qlik-MCP (Wissensdatenbank)

### 🔍 Suche & Entdeckung
| Tool | Beschreibung |
|---|---|
| `qlik_search` | Allgemeine Suche nach Ressourcen (Apps, Spaces, Datasets, Glossare) |
| `qlik_search_knowledgebase_chunks` | Semantische Suche in einer Wissensdatenbank |
| `qlik_search_field_values` | Feldwerte durchsuchen |

### 📊 Apps & Sheets
| Tool | Beschreibung |
|---|---|
| `qlik_describe_app` | Metadaten & Struktur einer App |
| `qlik_list_sheets` | Sheets/Dashboards einer App |
| `qlik_get_sheet_details` | Sheet-Details inkl. Charts |

### 📈 Charts
| Tool | Beschreibung |
|---|---|
| `qlik_get_chart_info` | Chart-Metadaten |
| `qlik_get_chart_data` | Chart-Daten (paginiert) |

### 📐 Master Items
| Tool | Beschreibung |
|---|---|
| `qlik_list_dimensions` | Library-Dimensionen |
| `qlik_list_measures` | Library-Measures |

### 🗂️ Felder & Daten
| Tool | Beschreibung |
|---|---|
| `qlik_get_fields` | Datenfelder einer App |
| `qlik_get_field_values` | Distinkte Werte eines Feldes |

### 🎯 Selections & Bookmarks (nur lesend)
| Tool | Beschreibung |
|---|---|
| `qlik_get_current_selections` | Aktive Filter |
| `qlik_list_bookmarks` | Bookmarks |

### 📦 Datasets
| Tool | Beschreibung |
|---|---|
| `qlik_get_dataset` | Dataset-Info |
| `qlik_get_dataset_schema` | Schema |
| `qlik_get_dataset_profile` | Profil |
| `qlik_get_dataset_sample` | Beispieldaten |
| `qlik_get_dataset_trust_score` | Trust Score |
| `qlik_get_dataset_freshness` | Aktualität |
| `qlik_get_dataset_memberships` | Zugehörigkeit |
| `qlik_get_lineage` | Datenherkunft |

### 📦 Datenprodukte
| Tool | Beschreibung |
|---|---|
| `qlik_get_data_product` | Datenprodukt |
| `qlik_get_data_product_documentation` | Markdown-Doku |

### 📖 Glossare
| Tool | Beschreibung |
|---|---|
| `qlik_get_full_glossary_export` | Komplett-Export |
| `qlik_search_glossary_terms` | Begriffe suchen |
| `qlik_get_glossary_term` | Einzelnen Begriff |
| `qlik_get_glossary_categories` | Kategorien |
| `qlik_get_glossary_term_links` | Verlinkungen |

### ❌ Verboten (Write-Tools)
`qlik_create_*`, `qlik_update_*`, `qlik_delete_*`, `qlik_add_*`,
`qlik_select_values`, `qlik_clear_selections`, `qlik_update_term_status`, etc.

---

## 📨 Microsoft-365-MCP (Outlook + Teams + OneDrive + SharePoint + Office + Planner + OneNote)

### 🔍 Universal-Suche & User
| Tool | Beschreibung |
|---|---|
| `search-query` | Universelle KQL-Suche (Docs, Mails, Files, Events, Chats) |
| `get-current-user` | Eigenes Benutzerprofil |
| `list-users` | Personen im Verzeichnis suchen (KQL) |

### ✉️ E-Mail & Outlook
| Tool | Beschreibung |
|---|---|
| `list-mail-folders` | Mail-Ordner |
| `list-mail-messages` | Nachrichten durchsuchen (KQL) |
| `get-mail-message` | Einzelne Mail öffnen |
| `list-mail-attachments` | Anhänge einer Mail |
| `list-outlook-contacts` | Kontakte |
| `list-shared-mailbox-messages` | Geteilte Postfächer |

### 📅 Kalender
| Tool | Beschreibung |
|---|---|
| `list-calendars` | Alle Kalender |
| `list-calendar-events` | Alle Termine |
| `get-calendar-view` | Termine in einem Zeitraum |
| `get-calendar-event` | Termin-Details |

### 💬 Teams & Chats
| Tool | Beschreibung |
|---|---|
| `list-chats` | Deine Chats (1:1, Gruppen) |
| `list-chat-messages` | Nachrichten in einem Chat |
| `list-joined-teams` | Deine Teams |
| `get-team` | Bestimmtes Team |
| `list-team-channels` | Kanäle eines Teams |
| `list-channel-messages` | Nachrichten in einem Kanal |
| `list-team-members` | Mitglieder eines Teams |

### 📁 OneDrive & SharePoint
| Tool | Beschreibung |
|---|---|
| `list-drives` | OneDrive- + SharePoint-Drives |
| `list-folder-files` | Dateien in einem Ordner |
| `download-onedrive-file-content` | Datei-Inhalt laden ⚠️ sparsam! |
| `search-sharepoint-sites` | SharePoint-Sites suchen |
| `list-sharepoint-site-lists` | Listen einer Site |
| `list-sharepoint-site-list-items` | Items in einer Liste |

### 📊 Excel
| Tool | Beschreibung |
|---|---|
| `list-excel-worksheets` | Worksheets einer Datei |
| `get-excel-range` | Daten aus einem Zellbereich |

### ✅ Planner & To-Do
| Tool | Beschreibung |
|---|---|
| `list-planner-tasks` | Planner-Aufgaben |
| `list-todo-task-lists` | To-Do-Listen |
| `list-todo-tasks` | Aufgaben einer Liste |
| `get-planner-task` | Planner-Task-Details |
| `get-todo-task` | To-Do-Task-Details |

### 📓 OneNote
| Tool | Beschreibung |
|---|---|
| `list-onenote-notebooks` | Notebooks |
| `list-onenote-notebook-sections` | Sektionen |
| `list-onenote-section-pages` | Seiten |
| `get-onenote-page-content` | Seiteninhalt |

### ❌ Verboten (Write-Tools)
Alle Tools zum Senden, Erstellen, Ändern, Löschen, Verschieben.

---

## 🧭 KQL-Spickzettel (Microsoft Graph Search)

```
# Mail von Person
from:julia@firma.de subject:"Content Surf"

# Zeitraum + Stichwort
received>=2026-05-01 received<=2026-05-26 "Integration"

# Termin mit Person
attendees:carsten.wehri@firma.de

# Anhänge filtern
hasattachment:true filetype:pdf

# Dateien in OneDrive/SharePoint
filename:Kampagnen-Review filetype:pptx

# Chat-/Channel-Nachrichten via search-query
"Content Surf" type:chatMessage

# Wichtige Mails
importance:high
```

📖 Microsoft Graph KQL-Referenz:
https://learn.microsoft.com/en-us/graph/search-query-parameter
