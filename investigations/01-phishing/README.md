# Phishing Investigation

## Overview

A suspicious email was investigated using a structured SOC investigation workflow.

The investigation included evidence preservation, email-header analysis, IOC extraction, infrastructure reputation analysis, SIEM investigation, incident timeline development, and MITRE ATT&CK mapping.

The objective was to determine the nature of the email, assess potential impact, identify associated indicators, and document an evidence-based analyst finding.

---

## 1. Evidence Preservation

The original investigation evidence was preserved before analysis and a SHA-256 hash was generated to provide a reference for evidence integrity.

![Evidence Preservation](evidence/01-evidence-preservation-sha256.png)

This established a repeatable evidence-handling process before further analysis was performed.

---

## 2. Email Header Analysis

The email headers were examined to identify relevant sender, routing, and delivery information.

![Email Header Analysis](evidence/02-email-header-analysis.png)

Header analysis was used to identify information requiring further investigation and to support extraction of relevant indicators.

---

## 3. IOC Extraction

URLs and other relevant indicators were extracted from the suspicious email for further analysis.

![IOC URL Extraction](evidence/03-ioc-url-extraction.png)

Extracting indicators separately allowed each component of the email infrastructure to be investigated and correlated.

---

## 4. Originating IP Analysis

The identified originating IP address was investigated using reputation information and available threat-intelligence sources.

![Originating IP Reputation](evidence/04-originating-ip-reputation.png)

The reputation results were considered alongside the remaining investigation evidence rather than being treated as a standalone verdict.

---

## 5. Sender Domain Analysis

The sender domain was investigated to identify reputation information and potentially suspicious characteristics.

![Sender Domain Reputation](evidence/05-sender-domain-reputation.png)

Domain findings were compared with the email-header information and other extracted indicators.

---

## 6. Phishing URL Analysis

The URL extracted from the email was investigated using multiple analysis sources.

### VirusTotal Analysis

![Phishing URL VirusTotal Analysis](evidence/06-phishing-url-virustotal.png)

### URLScan Analysis

![Phishing URL URLScan Analysis](evidence/06-phishing-url-urlscan.png)

Using multiple sources provided additional context around the URL rather than relying on a single reputation result.

---

## 7. Redirect Domain Analysis

Redirect infrastructure associated with the investigated URL was also reviewed.

![Redirect Domain Reputation](evidence/07-redirect-domain-reputation.png)

This helped identify additional infrastructure associated with the suspicious activity.

---

## 8. IOC Summary

The indicators identified during the investigation were consolidated to provide a single view of the evidence.

![IOC Summary](evidence/08-ioc-summary.png)

The IOC summary was then used to support SIEM searches and the final analyst assessment.

---

## 9. Splunk Investigation

The identified indicators were searched in Splunk to determine whether monitored systems had contacted or interacted with the investigated infrastructure.

![Splunk IOC Search](evidence/09-splunk-no-ioc-contact.png)

The SIEM search provided environment-specific context that could be correlated with the external indicator analysis.

---

## 10. Investigation Findings

The collected evidence was correlated to produce the final investigation findings.

![Investigation Findings](evidence/10-investigation-findings.png)

The assessment considered the email evidence, extracted indicators, reputation analysis, URL analysis, and internal SIEM telemetry together rather than relying on any individual indicator.

---

## 11. Incident Timeline

A timeline was created to organize the investigation activity and relevant events chronologically.

![Incident Timeline](evidence/11-incident-timeline.png)

The timeline provides a concise view of how the investigation progressed from initial evidence collection through analysis and final assessment.

---

## 12. MITRE ATT&CK Mapping

Observed activity was mapped to relevant MITRE ATT&CK techniques where supported by the investigation evidence.

![MITRE ATT&CK Mapping](evidence/12-mitre-attack-mapping.png)

This provides a standardized framework for describing the attacker behaviors identified during the investigation.

---

## SOC Skills Demonstrated

- Phishing investigation
- Email-header analysis
- Evidence preservation and hashing
- IOC extraction
- IP and domain reputation analysis
- URL analysis
- Threat-intelligence research
- SIEM investigation with Splunk
- Evidence correlation
- Incident timeline development
- MITRE ATT&CK mapping
- Analyst documentation

## Investigation Outcome

The final verdict and impact assessment were based on correlation of the collected evidence, external indicator analysis, and internal Splunk telemetry.

The investigation demonstrates a structured workflow from **initial evidence preservation → indicator analysis → threat-intelligence enrichment → SIEM validation → evidence correlation → analyst assessment**.
