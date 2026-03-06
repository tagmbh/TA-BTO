# TA-BTO – Blue Team Operations Knowledgebase

Kundenportal / Customer Portal für Blue Team Operations & Managed SIEM Plus Service.

## Systeme / Systems

| Abkürzung | System | Produkt |
|---|---|---|
| **SIEM** | Security Information & Event Management | Wazuh |
| **IMS** | Incident Management System | TheHive / IRIS |
| **TIPL** | Threat Intelligence Platform | MISP |
| **SOAR** | Security Orchestration, Automation & Response | Shuffle |
| **Cortex** | Enrichment & Response Engine | Cortex |

## Setup

```bash
# Install dependencies
pip install -r requirements.txt

# Run local development server
mkdocs serve

# Build static site
mkdocs build
```

## Struktur / Structure

```
docs/
├── index.md                  # Landing page (DE)
├── de/                       # Deutsche Inhalte
│   ├── ueberblick.md         # Blue Team Operations Überblick
│   ├── architektur.md        # Systemarchitektur
│   ├── systeme/              # Einzelne Systeme
│   │   ├── siem-wazuh.md
│   │   ├── ims-thehive-iris.md
│   │   ├── tipl-misp.md
│   │   ├── soar-shuffle.md
│   │   └── cortex.md
│   ├── service/              # Managed Service
│   │   ├── siem-plus.md
│   │   └── onboarding.md
│   └── glossar.md
└── en/                       # English content
    ├── overview.md
    ├── architecture.md
    ├── systems/
    ├── service/
    └── glossary.md
```
