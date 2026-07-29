# Cloud-Based SOC with Wazuh on Azure

A scalable Security Operations Center built on Microsoft Azure using Wazuh SIEM for cross-platform log collection and real-time threat detection.  

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE) [![GitHub stars](https://img.shields.io/github/stars/Swarup0809/Azure-Wazuh-SOC.svg)](https://github.com/Swarup0809/Azure-Wazuh-SOC/stargazers) [![Last Commit](https://img.shields.io/github/last-commit/Swarup0809/Azure-Wazuh-SOC.svg)](https://github.com/Swarup0809/Azure-Wazuh-SOC/commits) [![Made with Markdown](https://img.shields.io/badge/Made%20with-Markdown-blue.svg)](https://www.markdownguide.org/) [![Wazuh](https://img.shields.io/badge/Wazuh-SIEM-orange.svg)](https://wazuh.com/) [![Azure](https://img.shields.io/badge/Microsoft-Azure-007FFF.svg)](https://azure.microsoft.com)

## Table of Contents

- [Project Overview](#project-overview)  
- [Architecture Diagram](#architecture-diagram)  
- [Features](#features)  
- [Project Workflow](#project-workflow)  
- [Technologies Used](#technologies-used)  
- [Project Directory Structure](#project-directory-structure)  
- [Documentation](#documentation)  
- [Results](#results)  
- [Detection Summary](#detection-summary)  
- [Screenshots](#screenshots)  
- [Skills Demonstrated](#skills-demonstrated)  
- [Challenges Faced](#challenges-faced)  
- [Future Improvements](#future-improvements)  
- [Key Learnings](#key-learnings)  
- [Conclusion](#conclusion)  
- [Author](#author)  

## Project Overview

I built this project to demonstrate a fully functional cloud-hosted Security Operations Center (SOC) using open-source tools. The goal was to monitor both Linux and Windows endpoints from a central platform on Azure, enabling real-time threat detection and log analysis. It solves the challenge of collecting, analyzing, and correlating security events across platforms in a unified way.  

This SOC environment benefits **students, security analysts, and IT teams** learning about SIEMs and cloud security. By using Wazuh on Azure, I leverage a powerful, scalable solution. Wazuh was chosen for its rich feature set (FIM, log analysis, dashboards) and strong community support. It integrates natively with Azure VMs and provides MITRE ATT&CK mapping out of the box, making it ideal for a hands-on security project.  

## Architecture Diagram

A simplified architecture of the deployment is shown below:

```mermaid
flowchart TB
    Internet --> Azure["Azure Cloud"]
    Azure --> Wazuh["Ubuntu Wazuh Manager"]
    Wazuh --> UbuntuAgent["Ubuntu Endpoint"]
    Wazuh --> WindowsAgent["Windows Endpoint"]
    UbuntuAgent --> Dashboard["Wazuh Dashboard"]
    WindowsAgent --> Dashboard
    Dashboard --> Analyst["Security Analyst"]
