# Suricata Custom Detection Validation

## Overview

A custom Suricata detection rule was created and tested within the lab to validate network detection and SIEM integration.

The objective was to confirm that controlled network traffic could be inspected by Suricata, matched against custom detection logic, generate an alert, and become visible in Splunk for centralized investigation.

**Final Verdict:** True Positive — Controlled Custom Detection Test  
**Result:** Custom detection successfully triggered  
**SID:** `1000001`

---

## 1. Custom Suricata Rule

A custom Suricata rule was created to detect ICMP Echo Request traffic.

![Suricata Custom Rule](01-suricata-custom-rule.png)

The rule generated the following alert when matching traffic was observed:

**`LAB DETECTION - ICMP Ping Detected`**

The locally assigned signature ID was:

**SID:** `1000001`

---

## 2. Detection Validation

Controlled ICMP traffic was generated within the authorized lab environment.

Suricata inspected the traffic, matched the custom rule, and generated the expected security alert.

![Suricata Custom Rule Alert](02-suricata-custom-rule-alert.png)

This confirmed that the custom detection logic was operating as expected.

---

## 3. Splunk SIEM Validation

The resulting Suricata security event was forwarded to Splunk for centralized monitoring and investigation.

![Suricata Detection in Splunk](03-splunk-suricata-detection.png)

The same custom detection message and SID could be identified in Splunk, validating the integration between Suricata and the SIEM.

---

## 4. Investigation Findings

The collected evidence was reviewed to validate the complete detection pipeline.

![Suricata Detection Findings](04-suricata-detection-findings.png)

The test confirmed:

- Controlled ICMP traffic reached the monitoring environment.
- Suricata inspected the network traffic.
- The custom detection rule matched the traffic.
- Suricata generated the expected security alert.
- The resulting event was available in Splunk for investigation.

---

## Analyst Assessment

The test successfully validated the custom Suricata detection rule and the associated SIEM monitoring workflow.

The observed alert was generated as a result of an authorized security-control validation test.

### Verdict

**True Positive — Controlled Custom Detection Test**

### Result

**Custom Rule Triggered Successfully**

### SIEM Validation

**Suricata alert successfully identified in Splunk.**

No MITRE ATT&CK technique was assigned because the test was designed to validate **custom detection logic and SIEM integration**, rather than simulate a specific adversary technique.

---

## Security Controls Validated

- Suricata network inspection
- Custom detection-rule development
- Signature-based alerting
- Security-event logging
- Splunk SIEM ingestion
- Centralized detection investigation

## SOC Skills Demonstrated

- Suricata rule development
- Network detection engineering
- Controlled detection testing
- IDS alert analysis
- Splunk SIEM investigation
- Detection validation
- Security-event correlation
- Analyst documentation

## Detection Workflow

**Controlled ICMP Traffic → Suricata Inspection → Custom Rule Match → Alert Generation → Splunk SIEM → Analyst Validation**
