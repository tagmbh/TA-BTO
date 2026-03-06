# Glossar

Dieses Glossar erklärt die wichtigsten Fachbegriffe rund um Blue Team Operations und unseren SIEM Plus Managed Service.

---

## A

**Alert**
:   Eine Benachrichtigung, die vom SIEM-System erzeugt wird, wenn ein sicherheitsrelevantes Ereignis erkannt wird. Alerts haben Schweregrade von informativ bis kritisch.

**Analyzer**
:   Ein Modul in Cortex, das einen bestimmten Observable-Typ gegen eine externe Datenquelle prüft (z.B. VirusTotal-Analyzer prüft Datei-Hashes).

---

## B

**Blue Team**
:   Die defensive Seite der Cybersicherheit. Das Blue Team ist verantwortlich für Erkennung, Analyse und Abwehr von Cyberangriffen. Gegenstück: Red Team (offensive Sicherheit).

---

## C

**Case**
:   Ein dokumentierter Sicherheitsvorfall im Incident Management System (TheHive/IRIS). Enthält alle relevanten Informationen, Observables, Tasks und Maßnahmen.

**C2-Server (Command & Control)**
:   Ein Server, der von Angreifern genutzt wird, um Schadsoftware auf kompromittierten Systemen fernzusteuern.

**Cortex**
:   Enrichment & Response Engine. Analysiert verdächtige Indikatoren automatisch gegen externe Datenquellen und liefert Bewertungen. → [Cortex im Detail](systeme/cortex.md)

**CVE (Common Vulnerabilities and Exposures)**
:   Ein standardisiertes Verzeichnis bekannter Sicherheitslücken in Software. Jede Schwachstelle erhält eine eindeutige CVE-Nummer (z.B. CVE-2024-12345).

---

## D

**Decoder**
:   Eine Wazuh-Komponente, die rohe Log-Daten in strukturierte Felder umwandelt, damit Regeln darauf angewendet werden können.

**DSGVO / GDPR**
:   Datenschutz-Grundverordnung der EU. Regelt den Umgang mit personenbezogenen Daten. SIEM-Systeme unterstützen die Compliance-Nachweisführung.

---

## E

**Enrichment**
:   Anreicherung von Sicherheitsdaten mit zusätzlichem Kontext. Beispiel: Eine verdächtige IP-Adresse wird automatisch gegen Reputationsdatenbanken geprüft.

**Endpoint**
:   Ein Endgerät im Netzwerk (PC, Laptop, Server, Mobilgerät), das mit einem Wazuh Agent überwacht werden kann.

---

## F

**False Positive**
:   Ein Fehlalarm – ein Alert, der fälschlicherweise auf eine Bedrohung hinweist, obwohl keine vorliegt. Rule-Tuning reduziert False Positives.

**FIM (File Integrity Monitoring)**
:   Überwachung kritischer Dateien auf Änderungen. Eine Kernfunktion von Wazuh zur Erkennung unerlaubter Modifikationen.

---

## I

**IDS / IPS (Intrusion Detection / Prevention System)**
:   Systeme zur Erkennung (IDS) bzw. aktiven Verhinderung (IPS) von Netzwerkangriffen.

**IMS (Incident Management System)**
:   System zur strukturierten Bearbeitung von Sicherheitsvorfällen. In unserem Stack: TheHive oder IRIS. → [IMS im Detail](systeme/ims-thehive-iris.md)

**Incident**
:   Ein bestätigter Sicherheitsvorfall, der untersucht und bearbeitet werden muss.

**IoC (Indicator of Compromise)**
:   Ein Hinweis auf eine potenzielle Kompromittierung. Beispiele: Bösartige IP-Adressen, Malware-Hashes, Phishing-Domains. IoCs werden über MISP verwaltet.

**IRIS**
:   Incident Response Investigation System. Eine Open-Source-Plattform für detaillierte Incident Response Untersuchungen.

**ISAC (Information Sharing and Analysis Center)**
:   Branchenspezifische Organisationen für den Austausch von Cyber-Bedrohungsinformationen (z.B. Finanz-ISAC, Energie-ISAC).

---

## M

**MISP**
:   Malware Information Sharing Platform & Threat Sharing. Open-Source-Plattform für den Austausch von Bedrohungsinformationen. → [MISP im Detail](systeme/tipl-misp.md)

**MITRE ATT&CK**
:   Ein Framework, das Angriffstechniken und -taktiken katalogisiert. Wird für die Klassifizierung von Bedrohungen und die Bewertung der Erkennungsabdeckung genutzt.

**MTTR (Mean Time to Respond)**
:   Durchschnittliche Zeit von der Erkennung eines Vorfalls bis zur Reaktion. Eine Schlüsselmetrik für die SOC-Leistung.

**MTTD (Mean Time to Detect)**
:   Durchschnittliche Zeit von einem Sicherheitsvorfall bis zu dessen Erkennung.

---

## N

**NIS2**
:   EU-Richtlinie für Netz- und Informationssicherheit. Erweitert die Anforderungen an Cybersicherheit für viele Unternehmen und Branchen.

---

## O

**Observable**
:   Ein beobachtbarer Indikator innerhalb eines Cases (z.B. eine IP-Adresse, ein Datei-Hash, eine Domain). Observables können zur Analyse an Cortex gesendet werden.

**OpenSearch**
:   Die Datenbank-Engine hinter dem Wazuh Indexer. Speichert und indiziert alle Sicherheitsereignisse für schnelle Suche und Analyse.

---

## P

**Playbook**
:   Ein automatisierter Workflow in Shuffle (SOAR), der eine definierte Abfolge von Aktionen bei bestimmten Events ausführt.

---

## R

**Responder**
:   Ein Cortex-Modul, das aktive Reaktionsmaßnahmen durchführt (z.B. IP blockieren, Account sperren).

**Rule (Regel)**
:   Eine Erkennungsregel in Wazuh, die definiert, unter welchen Bedingungen ein Alert ausgelöst wird.

---

## S

**SIEM (Security Information and Event Management)**
:   System zur zentralen Sammlung, Korrelation und Analyse sicherheitsrelevanter Daten. In unserem Stack: Wazuh. → [Wazuh im Detail](systeme/siem-wazuh.md)

**Shuffle**
:   Open-Source SOAR-Plattform für Security Orchestration, Automation & Response. → [Shuffle im Detail](systeme/soar-shuffle.md)

**SLA (Service Level Agreement)**
:   Vereinbarung über die zugesicherten Service-Level (z.B. Reaktionszeiten, Verfügbarkeit).

**SOAR (Security Orchestration, Automation and Response)**
:   Plattform zur Automatisierung und Orchestrierung von Sicherheitsprozessen. In unserem Stack: Shuffle. → [Shuffle im Detail](systeme/soar-shuffle.md)

**SOC (Security Operations Center)**
:   Ein Team (und dessen Infrastruktur), das für die kontinuierliche Überwachung und Reaktion auf Sicherheitsvorfälle verantwortlich ist.

---

## T

**TheHive**
:   Open-Source Security Incident Response Platform für kollaboratives Case Management. → [TheHive im Detail](systeme/ims-thehive-iris.md)

**Threat Intelligence**
:   Aufbereitete Informationen über aktuelle Cyberbedrohungen (Akteure, Taktiken, Indikatoren). Wird über MISP bereitgestellt.

**TIPL (Threat Intelligence Platform)**
:   Plattform zum Sammeln, Verarbeiten und Teilen von Bedrohungsinformationen. In unserem Stack: MISP. → [MISP im Detail](systeme/tipl-misp.md)

**TLP (Traffic Light Protocol)**
:   Klassifizierung für die Weitergabe von Informationen:

    | Farbe | Weitergabe |
    |---|---|
    | **TLP:RED** | Nur für benannte Empfänger |
    | **TLP:AMBER** | Nur innerhalb der Organisation |
    | **TLP:AMBER+STRICT** | Nur innerhalb der Organisation, kein Sharing |
    | **TLP:GREEN** | Innerhalb der Community |
    | **TLP:CLEAR** | Öffentlich teilbar |

---

## W

**Wazuh**
:   Open-Source SIEM- und XDR-Plattform. Kern unseres SIEM Plus Managed Service. → [Wazuh im Detail](systeme/siem-wazuh.md)

**Wazuh Agent**
:   Software, die auf zu überwachenden Systemen installiert wird und Daten an den Wazuh Manager sendet.

**Webhook**
:   Ein HTTP-basierter Mechanismus, über den Systeme automatisch Benachrichtigungen an andere Systeme senden (z.B. Wazuh Alert → Shuffle).

---

## Y

**YARA**
:   Eine Sprache zur Beschreibung von Malware-Mustern. YARA-Regeln werden in Cortex und MISP zur Erkennung eingesetzt.
