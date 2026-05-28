# Home SOC Lab

## Overview

This project demonstrates a basic home Security Operations Center lab using Wazuh, Ubuntu, and a monitored Kali Linux endpoint. The objective is to collect endpoint security events, generate controlled test activity, investigate alerts, and document findings in a SOC-style format.

## Lab Environment

| Component | Description |
|---|---|
| SIEM Platform | Wazuh |
| Wazuh Server | Ubuntu VM |
| Monitored Endpoint | Kali Linux VM |
| Agent Name | kali-agent |
| Virtualization | Oracle VirtualBox |
| Network Modes | NAT and Host-only Adapter |

## Objectives

- Build a basic Wazuh-based SOC lab
- Deploy a Wazuh agent to a monitored endpoint
- Generate controlled security events
- Detect authentication, file integrity, and privilege activity
- Document detections in a clear SOC-style format
- Create a basic investigation report

## Project Structure

```text
home-soc-lab/
├── detections/
│   ├── failed-sudo-authentication.md
│   ├── file-integrity-monitoring.md
│   └── successful-sudo-privilege-activity.md
├── incidents/
│   └── soc-investigation-report.md
├── notes/
│   ├── agent-deployment.md
│   ├── lab-scope.md
│   └── setup-progress.md
├── screenshots/
└── README.md
```

## Detections Completed

| Detection | Category | Description |
|---|---|---|
| [Failed Sudo Authentication](detections/failed-sudo-authentication.md) | Authentication | Detects failed sudo authentication attempts from the Kali endpoint |
| [File Integrity Monitoring](detections/file-integrity-monitoring.md) | File Activity | Detects file creation, modification, and deletion activity |
| [Successful Sudo Privilege Activity](detections/successful-sudo-privilege-activity.md) | Privilege Activity | Detects successful sudo activity and privileged command execution |

## Investigation Report

| Report | Description |
|---|---|
| [SOC Investigation Report](incidents/soc-investigation-report.md) | Summarizes the authentication, file integrity, and privilege activity reviewed during the lab |

## Skills Demonstrated

- Wazuh SIEM setup
- Linux endpoint monitoring
- Wazuh agent deployment
- Authentication event analysis
- File integrity monitoring
- Privilege activity review
- Alert triage
- SOC-style investigation reporting
- GitHub security documentation

## Disclaimer

This project was performed in a controlled local lab environment for educational and defensive security purposes only. No testing was performed against public IP addresses, third-party systems, or production environments. Sensitive credentials and private keys are not stored in this repository.
