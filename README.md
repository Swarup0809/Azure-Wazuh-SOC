# Cloud-Based SOC with Wazuh on Azure

A scalable Security Operations Center built on Microsoft Azure using Wazuh SIEM for cross-platform log collection and real-time threat detection.  

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE) [![GitHub stars](https://img.shields.io/github/stars/Swarup0809/Azure-Wazuh-SOC.svg)](https://github.com/Swarup0809/Azure-Wazuh-SOC/stargazers) [![Last Commit](https://img.shields.io/github/last-commit/Swarup0809/Azure-Wazuh-SOC.svg)](https://github.com/Swarup0809/Azure-Wazuh-SOC/commits) [![Made with Markdown](https://img.shields.io/badge/Made%20with-Markdown-blue.svg)](https://www.markdownguide.org/) [![Wazuh](https://img.shields.io/badge/Wazuh-SIEM-orange.svg)](https://wazuh.com/) [![Azure](https://img.shields.io/badge/Microsoft-Azure-007FFF.svg)](https://azure.microsoft.com)

## 📖 Project Overview

This project demonstrates the design and implementation of a cloud-hosted Security Operations Center (SOC) using **Wazuh SIEM** deployed on **Microsoft Azure**.

The objective was to build a centralized security monitoring environment capable of collecting, analyzing, and visualizing security events from both Linux and Windows systems. The solution combines endpoint monitoring, File Integrity Monitoring (FIM), Windows Sysmon telemetry, VirusTotal threat intelligence, and Active Response into a single security platform.

The project was implemented using open-source technologies while following real-world SOC deployment practices.

---

# 🏗 Architecture

<p align="center">
  <img src="images/01-soc_architecure.png" width="850">
</p>

### Architecture Components

- Microsoft Azure Virtual Machine
- Ubuntu Server 22.04 LTS
- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard
- Ubuntu Agent
- Windows Agent
- Sysmon
- VirusTotal API

---

# 🚀 Features

- Centralized SIEM deployed on Microsoft Azure
- Cross-platform endpoint monitoring
- Ubuntu Agent integration
- Windows Agent integration
- Linux File Integrity Monitoring (FIM)
- Windows File Integrity Monitoring (FIM)
- Microsoft Sysmon integration
- VirusTotal threat intelligence enrichment
- Centralized log collection and visualization
- Real-time security alert generation

---

# ⚙ Technology Stack

| Component | Technology |
|------------|------------|
| Cloud Platform | Microsoft Azure |
| Operating System | Ubuntu Server 22.04 LTS |
| SIEM | Wazuh 4.x |
| Dashboard | Wazuh Dashboard |
| Indexer | Wazuh Indexer |
| Linux Endpoint | Ubuntu Agent |
| Windows Endpoint | Windows Agent |
| Endpoint Monitoring | Sysmon |
| Threat Intelligence | VirusTotal API |

---

# 📂 Repository Structure

```
Cloud-Based-SOC-with-Wazuh/

├── 01_documentation/
│   ├── Azure Setup and Configuration
│   ├── Wazuh Installation
│   ├── Ubuntu Agent Configuration
│   ├── Windows Agent Configuration
│   ├── File Integrity Monitoring
│   ├── Sysmon Configuration
│   ├── VirusTotal Integration
│   └── Validation & Testing
│
├── 02_images/
│   ├── SOC-Architecture.png
│   ├── Dashboard Screenshots
│   └── Alert Screenshots
│
├── README.md
└── LICENSE
```

---

# 🔄 Project Workflow

```
Endpoint Activity
        │
        ▼
Wazuh Agent Collects Logs
        │
        ▼
Wazuh Manager
        │
        ▼
Rule Analysis
        │
        ▼
VirusTotal Lookup (if applicable)
        │
        ▼
Wazuh Dashboard
        │
        ▼
Security Analyst Investigation
```

---

# 🔍 Security Use Cases

## Linux File Integrity Monitoring

- File Creation
- File Modification
- File Deletion

---

## Windows File Integrity Monitoring

- File Creation
- File Modification
- File Deletion

---

## Windows Sysmon Monitoring

- Process Creation
- Process Termination
- Registry Events
- Network Connections

---

## VirusTotal Integration

- Automatic File Hash Lookup
- Malware Reputation Analysis
- Threat Intelligence Enrichment

---

# ✅ Validation Performed

The following scenarios were successfully tested during the project:

- Ubuntu Agent successfully connected
- Windows Agent successfully connected
- Linux FIM alerts generated
- Windows FIM alerts generated
- Sysmon logs collected successfully
- VirusTotal alerts generated
- Security events visible in Wazuh Dashboard

---

# 📸 Project Screenshots

The repository includes screenshots demonstrating:

- Azure Infrastructure
- Wazuh Dashboard
- Connected Agents
- Linux FIM Alerts
- Windows FIM Alerts
- Sysmon Events
- VirusTotal Detection
---

# 💡 Skills Demonstrated

- Security Operations Center (SOC)
- Security Information and Event Management (SIEM)
- Cloud Security
- Microsoft Azure
- Linux Administration
- Windows Administration
- Endpoint Monitoring
- Threat Detection
- Threat Intelligence
- Incident Response
- Log Analysis
- Network Security
- Security Documentation

---

# 📚 Key Learnings

This project provided practical experience in:

- Deploying a production-style SIEM environment
- Building cloud-based security infrastructure
- Monitoring Linux and Windows endpoints
- Detecting file integrity violations
- Integrating Sysmon with Wazuh
- Using VirusTotal for threat intelligence
- Implementing automated security response
- Troubleshooting endpoint connectivity and alert generation

---

# 🔮 Future Enhancements

Potential future improvements include:

- Suricata IDS Integration
- Email Alerting
- Slack Notifications
- Docker Monitoring
- Kubernetes Monitoring
- Azure Security Log Integration
- Custom Wazuh Detection Rules
- Threat Hunting Dashboards

---

# 📝 Conclusion

This project demonstrates the deployment of a centralized cloud-based Security Operations Center using Wazuh on Microsoft Azure. By integrating Linux and Windows endpoint monitoring, File Integrity Monitoring, Sysmon, VirusTotal, and Active Response, the solution provides real-time visibility into endpoint security events while showcasing practical blue-team skills and modern SOC operations.

---

## 👨‍💻 Author

**T.R.J.Swarup Reddy**

Cybersecurity Student | SOC | Cloud Security | Blue Team Security | SIEM | Azure | Wazuh

---

## ⭐ Support

If you found this project useful, consider giving the repository a **Star ⭐**.
