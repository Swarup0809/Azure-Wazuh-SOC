# Detection Summary

## Overview

This document summarizes the security events generated throughout the implementation of the Cloud-Based Security Operations Center (SOC) using Wazuh SIEM. During testing, I performed multiple security-related activities across Ubuntu and Windows agents to verify that the Wazuh Manager could successfully detect, analyze, and report different types of events.

The objective was not only to generate alerts but also to validate that each security component worked as expected and produced meaningful information for security monitoring and incident investigation.

---

# Detection Workflow

The overall detection process followed the sequence below:

```
System Activity
       │
       ▼
Wazuh Agent Collects Logs
       │
       ▼
Wazuh Manager Processes Events
       │
       ▼
Rules Engine Matches Signatures
       │
       ▼
Alert Generated
       │
       ▼
Dashboard Visualization
       │
       ▼
Security Analyst Investigation
```

Every monitored activity passed through this pipeline before appearing on the Wazuh Dashboard.

---

# Detection Categories

The project successfully detected multiple categories of security events.

| Detection Module | Platform | Status |
|------------------|----------|--------|
| File Integrity Monitoring | Ubuntu | ✅ Successful |
| File Integrity Monitoring | Windows | ✅ Successful |
| Sysmon Event Monitoring | Windows | ✅ Successful |
| VirusTotal Integration | Ubuntu | ✅ Successful |
| Agent Health Monitoring | Ubuntu & Windows | ✅ Successful |

---

# Alert Severity Levels

Wazuh classifies alerts based on severity. Higher severity values indicate events that require greater attention from the security team.

| Severity | Meaning | Typical Action |
|----------|---------|----------------|
| 0–2 | Informational | Ignore or monitor |
| 3–5 | Low | Review when necessary |
| 6–9 | Medium | Investigate |
| 10–12 | High | Immediate attention |
| 13–15 | Critical | Incident response required |

During this project, alerts ranging from informational to high severity were successfully generated depending on the activity performed.

---

# Test Case Summary

## Test 1 – Ubuntu Agent Registration

### Objective

Verify successful communication between the Ubuntu agent and the Wazuh Manager.

### Activity

- Installed Wazuh Agent
- Registered the agent
- Started Wazuh service

### Expected Result

Agent appears as **Active**.

### Outcome

✅ Successful

The Ubuntu system registered successfully and continuously transmitted security events to the Wazuh Manager.

---

## Test 2 – Windows Agent Registration

### Objective

Validate Windows agent connectivity.

### Activity

- Installed Windows Wazuh Agent
- Registered with Manager
- Started Wazuh Service

### Expected Result

Windows agent appears online.

### Outcome

✅ Successful

The Windows endpoint successfully communicated with the manager and began forwarding Windows event logs.

---

## Test 3 – Ubuntu File Integrity Monitoring

### Objective

Detect file creation, deletion, and modification.

### Activity

Files inside the monitored directory were:

- Created
- Modified
- Deleted

### Expected Result

Wazuh generates FIM alerts.

### Outcome

✅ Successful

Every file operation produced a corresponding security event in the dashboard.

Typical events included:

- File Created
- File Modified
- File Deleted
- Checksum Changed

---

## Test 4 – Windows File Integrity Monitoring

### Objective

Verify real-time monitoring on Windows.

### Activity

Text files were edited and deleted within monitored folders.

### Expected Result

Dashboard records Windows file activity.

### Outcome

✅ Successful

Windows FIM detected all monitored file operations with accurate timestamps.

---

## Test 5 – Sysmon Monitoring

### Objective

Capture detailed Windows process activity.

### Activity

- Installed Sysmon
- Generated process events
- Executed PowerShell
- Opened Notepad
- Created files

### Expected Result

Process creation events appear inside Wazuh.

### Outcome

✅ Successful

Sysmon generated detailed telemetry including:

- Process creation
- Parent process
- Command line
- User information
- Process ID
- Executable path

These events greatly improved visibility compared to standard Windows logs.

---

## Test 6 – VirusTotal Integration

### Objective

Validate malware hash reputation lookup.

### Activity

Downloaded the EICAR anti-malware test file inside Ubuntu.

### Expected Result

VirusTotal scans the file hash and returns a malware reputation.

### Outcome

✅ Successful

The integration detected the EICAR test file and generated a high-severity security alert indicating that multiple antivirus engines recognized the file.

---

# MITRE ATT&CK Mapping

Several alerts were automatically mapped to MITRE ATT&CK techniques.

| Technique | Description |
|-----------|-------------|
| T1105 | Ingress Tool Transfer |
| T1203 | Exploitation for Client Execution |
| File Integrity | Persistence / Defense Evasion Indicators |
| Process Monitoring | Execution |
| Malware Detection | Command and Control / Execution |

The MITRE mapping provided additional context for understanding attacker behavior.

---

# Detection Accuracy

The implemented SOC successfully detected all intended security events.

| Test | Detection |
|------|-----------|
| Ubuntu Agent | ✅ |
| Windows Agent | ✅ |
| Ubuntu FIM | ✅ |
| Windows FIM | ✅ |
| Sysmon Events | ✅ |
| VirusTotal Alerts | ✅ |

No false negatives were observed during testing.

---

# Dashboard Visibility

Throughout the project, the Wazuh Dashboard provided centralized visibility into all monitored endpoints.

The dashboard enabled me to:

- Monitor active agents
- Review security alerts
- Investigate event details
- Filter alerts by severity
- Analyze event timelines
- View MITRE ATT&CK mappings
- Inspect raw event data
- Validate detection results in real time

This centralized monitoring significantly simplified security analysis.

---

# Key Findings

The implementation demonstrated that Wazuh is capable of monitoring both Linux and Windows environments from a single management server.

Some important observations include:

- Agent communication remained stable throughout testing.
- File modifications were detected almost immediately.
- Sysmon significantly enhanced Windows event visibility.
- VirusTotal integration enriched alerts with external threat intelligence.
- MITRE ATT&CK mapping helped classify attacker behavior.
- The dashboard provided a single interface for monitoring multiple endpoints.

---

# Overall Result

All planned security monitoring objectives were successfully achieved.

The deployed Cloud-Based SOC successfully detected endpoint activities, generated meaningful alerts, enriched events with threat intelligence, and presented all findings through a centralized Wazuh Dashboard. The project demonstrates how open-source security tools can be integrated to build an effective and scalable Security Operations Center capable of monitoring both Linux and Windows environments.