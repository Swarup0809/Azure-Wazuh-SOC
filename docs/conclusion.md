# Conclusion

## Project Summary

This project helped me build a practical **Cloud-Based Security Operations Center (SOC)** using **Wazuh SIEM** deployed on **Microsoft Azure**. Instead of simply installing different security tools, I focused on creating a complete monitoring environment where Linux and Windows endpoints could securely send logs to a centralized SIEM for analysis.

Throughout the implementation, I configured Azure infrastructure, deployed the Wazuh Manager, connected multiple agents, enabled File Integrity Monitoring (FIM), integrated Microsoft Sysmon for advanced Windows telemetry, and connected VirusTotal to enrich alerts with external threat intelligence. Each component was tested individually before validating the complete monitoring workflow.

The final environment successfully demonstrated how open-source security tools can work together to provide centralized visibility, endpoint monitoring, and real-time threat detection.

---

# What I Achieved

During this project, I successfully implemented the following:

- Deployed a cloud-hosted Wazuh Manager on Microsoft Azure.
- Connected both Ubuntu and Windows endpoints using Wazuh Agents.
- Configured secure communication between the manager and agents.
- Implemented File Integrity Monitoring on Linux and Windows.
- Integrated Microsoft Sysmon to collect detailed Windows endpoint telemetry.
- Connected VirusTotal to enrich security alerts with malware intelligence.
- Validated detections using file modification events, Sysmon logs, and the EICAR malware test file.
- Verified that all generated alerts were correctly displayed in the Wazuh Dashboard.

Together, these components formed a functional SOC environment capable of continuously monitoring endpoint activity from a centralized dashboard.

---

# Challenges I Faced

Like any real-world deployment, this project involved several technical challenges.

One of the first challenges was configuring the Azure networking correctly. The required Network Security Group (NSG) rules had to be configured carefully to allow secure HTTPS access to the Wazuh Dashboard while also permitting agent communication.

Another challenge was establishing stable communication between the Wazuh Manager and both endpoint agents. This required verifying manager IP addresses, confirming agent configurations, and ensuring that all required Wazuh services were running properly.

Configuring File Integrity Monitoring also required careful tuning. I had to modify the agent configuration files to monitor the required directories in real time and restart the services before file events appeared in the dashboard.

On the Windows endpoint, integrating Microsoft Sysmon required additional configuration to forward Sysmon Operational logs into Wazuh. Once configured correctly, detailed process creation and system activity events became available inside the SIEM.

Each challenge strengthened my understanding of troubleshooting, log collection, endpoint configuration, and SIEM deployment rather than simply following installation guides.

---

# Key Learnings

This project provided practical experience beyond learning individual tools.

Some of the most valuable concepts I learned include:

- Designing a cloud-based SOC architecture.
- Deploying and managing Azure Virtual Machines.
- Configuring Wazuh Manager and endpoint agents.
- Understanding centralized log collection.
- Implementing File Integrity Monitoring.
- Integrating external threat intelligence using VirusTotal.
- Monitoring Windows telemetry with Sysmon.
- Validating detections using real-world security testing techniques.
- Troubleshooting communication and configuration issues across distributed systems.

Overall, the project improved both my Linux administration and defensive cybersecurity skills while giving me hands-on experience with SIEM technologies.

---

# Future Improvements

Although the implemented SOC is fully functional, there are several enhancements that could make it more powerful in the future.

Some possible improvements include:

- Implementing **Active Response** to automatically isolate compromised systems or remove malicious files.
- Integrating **TheHive** for incident management and case tracking.
- Using **Shuffle SOAR** to automate repetitive security workflows.
- Creating custom Wazuh detection rules for organization-specific use cases.
- Adding more endpoint systems to simulate a larger enterprise environment.
- Integrating additional threat intelligence sources for richer alert context.
- Building custom dashboards and visualizations for different SOC roles.

These enhancements would transform the current implementation from a monitoring platform into a more mature Security Operations Center with automated response and incident handling capabilities.

---

# Final Thoughts

Building this Cloud-Based SOC was much more than a deployment exercise.It gave me practical exposure to the complete lifecycle of designing, configuring, validating, and troubleshooting a SIEM environment.

Working through real configuration challenges helped me understand how different security components interact in real. By combining Azure infrastructure, Wazuh SIEM, endpoint monitoring, File Integrity Monitoring, Sysmon telemetry, and VirusTotal threat intelligence, I was able to build a centralized monitoring platform capable of detecting and investigating security events across multiple operating systems.

This project has strengthened my understanding of defensive security concepts and provided a solid foundation for exploring advanced SOC technologies such as SOAR, incident response, and threat hunting in future projects.