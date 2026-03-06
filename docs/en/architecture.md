# System Architecture

## Overall Architecture

The following diagram shows how all components of our Blue Team Operations stack work together:

```mermaid
graph TB
    subgraph sources ["📊 Log Sources"]
        S1[Windows Servers]
        S2[Linux Servers]
        S3[Firewalls / IDS]
        S4[Cloud Services]
        S5[Endpoints]
    end

    subgraph siem ["🛡️ SIEM – Wazuh"]
        WM[Wazuh Manager]
        WI[Wazuh Indexer<br/>OpenSearch]
        WD[Wazuh Dashboard]
        WM --> WI
        WI --> WD
    end

    subgraph threat_intel ["🔍 Threat Intelligence"]
        MISP_S[MISP Server]
        MISP_F[MISP Feeds]
        MISP_F --> MISP_S
    end

    subgraph automation ["⚙️ Automation"]
        SH[Shuffle<br/>SOAR]
        CX[Cortex<br/>Enrichment]
    end

    subgraph incident_mgmt ["📋 Incident Management"]
        TH[TheHive / IRIS]
        TH_DB[(Case Database)]
        TH --> TH_DB
    end

    S1 & S2 & S3 & S4 & S5 -->|Wazuh Agents| WM
    WM -->|Alerts| SH
    SH -->|IoC queries| MISP_S
    SH -->|Enrichment| CX
    MISP_S -->|Threat Feeds| WM
    SH -->|Create cases| TH
    CX -->|Analysis results| TH
    WD -->|Manual analysis| TH
```

---

## Data Flow

### 1. Data Collection (Ingestion)

```
Log Sources → Wazuh Agents → Wazuh Manager → Wazuh Indexer (OpenSearch)
```

- **Wazuh Agents** are installed on all monitored systems
- Agents send logs encrypted to the **Wazuh Manager**
- The Manager applies **rules and decoders** and stores events in the **Indexer**

### 2. Detection

```
Wazuh Rules + MISP IoCs → Alert Generation → Prioritization
```

- Wazuh evaluates events against thousands of predefined and custom **rules**
- **MISP** provides current Indicators of Compromise (IoCs) for detection
- Alerts are prioritized by **severity** (1–15)

### 3. Orchestration

```
Alert → Shuffle Workflow → Cortex Enrichment → Decision
```

- **Shuffle** receives alerts and starts automated **playbooks**
- **Cortex** enriches suspicious indicators (IPs, hashes, domains) with external data
- Based on results: automatic action or escalation to an analyst

### 4. Incident Management

```
Validated Alert → TheHive/IRIS Case → Analysis → Response → Closure
```

- Confirmed incidents are created as **cases** in TheHive/IRIS
- Analysts document analysis, actions and results
- Completed cases feed back as **learnings** into the system

---

## Network & Communication

| From | To | Protocol | Purpose |
|---|---|---|---|
| Wazuh Agent | Wazuh Manager | TCP 1514 (encrypted) | Log transmission |
| Wazuh Manager | Wazuh Indexer | HTTPS 9200 | Event storage |
| Wazuh Manager | Shuffle | Webhook (HTTPS) | Alert forwarding |
| Shuffle | MISP | REST API (HTTPS) | IoC queries |
| Shuffle | Cortex | REST API (HTTPS) | Enrichment requests |
| Shuffle | TheHive/IRIS | REST API (HTTPS) | Case creation |
| Cortex | TheHive/IRIS | REST API (HTTPS) | Analysis results |
| MISP | Wazuh Manager | REST API (HTTPS) | Threat feed integration |

---

## Deployment Model

!!! note "Managed Service"
    As part of our **SIEM Plus** Managed Service, we operate the entire infrastructure for you. Only the **Wazuh Agents** are installed in your environment.

```mermaid
graph LR
    subgraph customer ["🏢 Customer Environment"]
        A1[Wazuh Agent]
        A2[Wazuh Agent]
        A3[Wazuh Agent]
    end

    subgraph managed ["☁️ Managed SIEM Plus Platform"]
        W[Wazuh Manager & Indexer]
        S[Shuffle SOAR]
        M[MISP]
        C[Cortex]
        T[TheHive / IRIS]
    end

    A1 & A2 & A3 -->|Encrypted Connection| W
    W --> S
    S --> M & C & T
```

---

## Next Steps

Learn more about the individual systems:

- [SIEM – Wazuh](systems/siem-wazuh.md)
- [IMS – TheHive / IRIS](systems/ims-thehive-iris.md)
- [TIPL – MISP](systems/tipl-misp.md)
- [SOAR – Shuffle](systems/soar-shuffle.md)
- [Cortex](systems/cortex.md)
