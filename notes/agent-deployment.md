# Wazuh Agent Deployment

## Objective

Deploy a Wazuh agent on a Kali Linux VM and connect it to the Wazuh server for centralized monitoring.

## Lab Environment

| Component | Description |
|---|---|
| Wazuh Server | Ubuntu VM |
| Monitored Endpoint | Kali Linux VM |
| Network Mode | NAT and Host-only Adapter |
| Agent Name | kali-agent |

## Deployment Summary

The Kali Linux VM was configured as a monitored endpoint using the Wazuh agent. The agent was deployed using the Wazuh dashboard agent deployment workflow and connected to the Wazuh server over the host-only lab network.

## Verification

The Wazuh agent service was started and enabled on the Kali VM.

```bash
sudo systemctl status wazuh-agent
