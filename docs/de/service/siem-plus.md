# Managed Service – SIEM Plus

## Überblick

**SIEM Plus** ist unser umfassender Managed Security Service, der auf der Open-Source-Plattform **Wazuh** basiert und durch die Integration von TheHive/IRIS, MISP, Shuffle und Cortex einen vollständigen Blue Team Operations Stack bietet.

!!! success "Der Vorteil für Sie"
    Mit SIEM Plus erhalten Sie ein **vollwertiges Security Operations Center (SOC)** – ohne die Komplexität und Kosten eines eigenen Aufbaus. Wir betreiben die Technik, Sie behalten den Überblick.

---

## Was ist im Service enthalten?

### Plattform-Komponenten

| Komponente | System | Im Service enthalten |
|---|---|---|
| **SIEM** | [Wazuh](../systeme/siem-wazuh.md) | ✅ Vollständig verwaltet |
| **Incident Management** | [TheHive / IRIS](../systeme/ims-thehive-iris.md) | ✅ Vollständig verwaltet |
| **Threat Intelligence** | [MISP](../systeme/tipl-misp.md) | ✅ Vollständig verwaltet |
| **Automatisierung** | [Shuffle](../systeme/soar-shuffle.md) | ✅ Vollständig verwaltet |
| **Enrichment** | [Cortex](../systeme/cortex.md) | ✅ Vollständig verwaltet |

### Service-Leistungen

```mermaid
graph TB
    subgraph service ["SIEM Plus Managed Service"]
        subgraph tech ["Technische Leistungen"]
            T1[Plattform-Betrieb<br/>24/7 Verfügbarkeit]
            T2[Agent-Management<br/>Rollout & Updates]
            T3[Rule-Tuning<br/>Kundenspezifische Regeln]
            T4[Threat Feed Management<br/>Aktuelle IoCs]
        end

        subgraph ops ["Operative Leistungen"]
            O1[Alert-Monitoring<br/>Überwachung & Triage]
            O2[Incident Response<br/>Vorfallbearbeitung]
            O3[Playbook-Entwicklung<br/>Automatisierung]
            O4[Reporting<br/>Regelmäßige Berichte]
        end

        subgraph advisory ["Beratungsleistungen"]
            A1[Security Consulting<br/>Strategische Beratung]
            A2[Compliance Support<br/>NIS2, ISO 27001]
            A3[Onboarding<br/>Einführung & Schulung]
        end
    end
```

---

## Service-Level

| Merkmal | Details |
|---|---|
| **Verfügbarkeit** | Plattform 24/7 verfügbar |
| **Monitoring** | Kontinuierliche Überwachung der Alerts |
| **Incident Response** | Reaktion gemäß vereinbartem SLA |
| **Updates** | Regelmäßige Plattform- und Regel-Updates |
| **Reporting** | Monatlicher Sicherheitsbericht |

---

## Was Sie bereitstellen

Für den SIEM Plus Service benötigen wir von Ihrer Seite:

| Aufgabe | Details |
|---|---|
| **Agent-Installation** | Wazuh Agents auf Ihren Systemen (wir unterstützen beim Rollout) |
| **Netzwerk-Freigaben** | Ausgehende Verbindung zum Wazuh Manager (TCP 1514) |
| **Ansprechpartner** | Technischer Kontakt für Rückfragen bei Vorfällen |
| **Log-Quellen** | Definition der zu überwachenden Systeme und Quellen |

---

## Ablauf eines typischen Sicherheitsvorfalls

```mermaid
sequenceDiagram
    participant K as Ihr System
    participant W as Wazuh SIEM
    participant SH as Shuffle SOAR
    participant CX as Cortex
    participant TH as TheHive IMS
    participant SOC as SOC-Analyst
    participant AN as Ihr Ansprechpartner

    K->>W: Log-Daten senden
    W->>W: Regeln anwenden
    W->>SH: Alert weiterleiten
    SH->>CX: Enrichment anfordern
    CX-->>SH: Analyse-Ergebnis
    SH->>SH: Playbook ausführen
    SH->>TH: Case erstellen
    TH->>SOC: Case zuweisen
    SOC->>SOC: Analyse & Bewertung
    SOC->>AN: Benachrichtigung & Empfehlung
    AN-->>SOC: Rückmeldung
    SOC->>TH: Case abschließen
    TH->>AN: Incident Report
```

---

## Mehrwert gegenüber Eigenbetrieb

| Aspekt | Eigenbetrieb | SIEM Plus |
|---|---|---|
| **Personalaufwand** | 3–5 SOC-Analysten nötig | Im Service enthalten |
| **Aufbauzeit** | 6–12 Monate | Wochen (Onboarding) |
| **Lizenzkosten** | Kommerzielle SIEM-Lizenzen | Open Source – keine Lizenzkosten |
| **Threat Intelligence** | Eigene Feeds beschaffen | Kuratierte Feeds inklusive |
| **Automatisierung** | Eigene Playbooks entwickeln | Bewährte Playbooks inklusive |
| **Know-how** | Eigenes Team aufbauen | Erfahrenes SOC-Team |
| **Skalierung** | Hardware & Lizenzen beschaffen | Flexibel skalierbar |

---

## Nächste Schritte

Interessiert an SIEM Plus? So geht es weiter:

1. **Erstgespräch** – Wir analysieren Ihre Anforderungen und IT-Landschaft
2. **Angebot** – Individuelles Angebot basierend auf Ihrem Scope
3. **[Onboarding](onboarding.md)** – Strukturierte Einführung in wenigen Wochen
4. **Betrieb** – Kontinuierlicher Managed Service

---

## Weiterführende Links

- [Onboarding-Prozess](onboarding.md) – So läuft die Einführung ab
- [Systemarchitektur](../architektur.md) – Technische Gesamtübersicht
- [Glossar](../glossar.md) – Fachbegriffe einfach erklärt
