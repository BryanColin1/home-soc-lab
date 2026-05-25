# Home SOC Lab

## Overview

This project demonstrates a basic Security Operations Center lab using Wazuh, Kali Linux, and a monitored Windows endpoint. The objective is to collect security logs, generate test activity, detect suspicious behavior, and document investigations in a clear SOC-style format.

## Objectives

- Build a basic home SOC lab environment
- Collect logs from a monitored endpoint
- Generate controlled security events
- Detect failed logins, scanning activity, and suspicious commands
- Document findings using SOC-style investigation reports

## Planned Lab Environment

| Component | Purpose |
|---|---|
| Wazuh Server | SIEM and security monitoring platform |
| Windows VM | Monitored endpoint |
| Kali Linux VM | Test attacker/scanner machine |
| VirtualBox | Virtual lab platform |

## Planned Detections

- Failed Windows login attempts
- Nmap scan activity
- Suspicious PowerShell activity

## Skills Demonstrated

- SIEM setup
- Log collection
- Endpoint monitoring
- Alert investigation
- Detection engineering basics
- Incident documentation
- Security operations workflow

## Disclaimer

This project is performed in a controlled lab environment for educational and defensive security purposes only.
