# 🔌 MCP-Tools-Referenz

Vollständige Liste der **Read-Only**-Tools, die der Agent nutzen darf.

---

## 📊 Qlik-MCP (Wissensdatenbank)

### 🔍 Suche & Entdeckung
| Tool | Beschreibung |
|---|---|
| `qlik_search` | Allgemeine Suche nach Ressourcen (Apps, Spaces, Datasets, Glossare) |
| `qlik_search_knowledgebase_chunks` | Semantische Suche in einer Wissensdatenbank |
| `qlik_search_field_values` | Feldwerte durchsuchen (z. B. vor Filtern prüfen) |

### 📊 Apps & Sheets
| Tool | Beschreibung |
|---|---|
| `qlik_describe_app` | Metadaten & Struktur einer App anzeigen |
| `qlik_list_sheets` | Alle Sheets (Dashboards) einer App auflisten |
| `qlik_get_sheet_details` | Details eines Sheets inkl. Charts anzeigen |

### 📈 Charts & Visualisierungen
| Tool | Beschreibung |
|---|---|
| `qlik_get_chart_info` | Metadaten eines Charts abrufen |
| `qlik_get_chart_data` | Daten aus einem Chart auslesen (paginiert) |

### 📐 Master Items (Dimensionen & Measures)
| Tool | Beschreibung |
|---|---|
| `qlik_list_dimensions` | Library-Dimensionen auflisten |
| `qlik_list_measures` | Library-Measures auflisten |

### 🗂️ Felder & Daten
| Tool | Beschreibung |
|---|---|
| `qlik_get_fields` | Alle verfügbaren Datenfelder einer App anzeigen |
| `qlik_get_field_values` | Distinkte Werte eines Feldes abrufen |

### 🎯 Selections & Bookmarks (nur lesend)
| Tool | Beschreibung |
|---|---|
| `qlik_get_current_selections` | Aktive Filter anzeigen |
| `qlik_list_bookmarks` | Bookmarks auflisten |

### 📦 Datasets
| Tool | Beschreibung |
|---|---|
| `qlik_get_dataset` | Dataset-Info |
| `qlik_get_dataset_schema` | Schema |
| `qlik_get_dataset_profile` | Profil |
| `qlik_get_dataset_sample` | Beispieldaten |
| `qlik_get_dataset_trust_score` | Trust Score |
| `qlik_get_dataset_freshness` | Aktualität |
| `qlik_get_dataset_memberships` | Zugehörigkeit zu Datenprodukten |
| `qlik_get_lineage` | Datenherkunft (Lineage) |

### 📦 Datenprodukte
| Tool | Beschreibung |
|---|---|
| `qlik_get_data_product` | Datenprodukt abrufen |
| `qlik_get_data_product_documentation` | Markdown-Doku eines Datenprodukts |

### 📖 Glossare
| Tool | Beschreibung |
|---|---|
| `qlik_get_full_glossary_export` | Komplett-Export |
| `qlik_search_glossary_terms` | Begriffe suchen |
| `qlik_get_glossary_term` | Einzelnen Begriff abrufen |
| `qlik_get_glossary_categories` | Kategorien |
| `qlik_get_glossary_term_links` | Verlinkungen zu Ressourcen |

### ❌ Verboten (Write-Tools)
`qlik_create_*`, `qlik_update_*`, `qlik_delete_*`, `qlik_add_chart`,
`qlik_add_filter`, `qlik_select_values`, `qlik_clear_selections`,
`qlik_create_data_object`, `qlik_update_term_status`, etc.

---

## 📧 Outlook-MCP (Mailbox & Kalender)

### 👤 Benutzer
| Tool | Beschreibung |
|---|---|
| `get-current-user` | Eigenes Benutzerprofil |
| `list-users` | Benutzer im Verzeichnis suchen (KQL) |

### 📅 Kalender & Events
| Tool | Beschreibung |
|---|---|
| `list-calendars` | Alle Kalender |
| `list-calendar-events` | Events Standard-Kalender |
| `get-calendar-event` | Einzelnes Event |
| `get-calendar-view` | Kalenderansicht (inkl. Serien) im Zeitraum |
| `list-specific-calendar-events` | Events bestimmter Kalender |
| `get-specific-calendar-event` | Einzelnes Event aus best. Kalender |
| `get-specific-calendar-view` | Zeitraum-Ansicht best. Kalender |
| `list-calendar-event-instances` | Einzelne Vorkommen einer Serie |

### 📧 E-Mails
| Tool | Beschreibung |
|---|---|
| `list-mail-messages` | Alle Nachrichten (KQL-Suche) |
| `get-mail-message` | Einzelne Nachricht |
| `list-mail-folder-messages` | Nachrichten aus best. Ordner |
| `list-mail-folders` | Ordner Root-Ebene |
| `list-mail-child-folders` | Unterordner |

### 📎 Anhänge
| Tool | Beschreibung |
|---|---|
| `list-mail-attachments` | Anhänge einer Nachricht |
| `get-mail-attachment` | Einzelnen Anhang (inkl. Inhalt) |

### 📬 Shared Mailbox
| Tool | Beschreibung |
|---|---|
| `list-shared-mailbox-messages` | Nachrichten aus geteiltem Postfach |
| `list-shared-mailbox-folder-messages` | Nachrichten aus Ordner im geteilten Postfach |
| `get-shared-mailbox-message` | Einzelne Nachricht aus geteiltem Postfach |

### 👥 Kontakte
| Tool | Beschreibung |
|---|---|
| `list-outlook-contacts` | Kontakte auflisten |
| `get-outlook-contact` | Einzelner Kontakt |

### 🔍 Suche
| Tool | Beschreibung |
|---|---|
| `search-query` | Erweiterte Suche (Events, Nachrichten, DriveItems) mit KQL |
| `search-sharepoint-sites` | SharePoint-Sites suchen |

### ❌ Verboten (Write-Tools)
Alle Tools zum Senden, Erstellen, Ändern, Löschen, Verschieben.

---

## 🧭 KQL-Spickzettel (Outlook)

```
# Mail von Person
from:julia@firma.de subject:"Content Surf"

# Zeitraum + Stichwort
received>=2026-05-01 received<=2026-05-26 "Integration"

# Termin mit Person
attendees:carsten.wehri@firma.de

# Anhänge filtern
hasattachment:true filetype:pdf

# Bestimmter Ordner
folderid:AAMkAGI...

# Wichtige Mails
importance:high
```

📖 Microsoft Graph KQL: https://learn.microsoft.com/en-us/graph/search-query-parameter
