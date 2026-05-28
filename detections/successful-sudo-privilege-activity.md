# Successful Sudo Privilege Activity Detection

## Objective

Detect and document successful sudo activity from a monitored Kali Linux endpoint using Wazuh.

## Environment

| Component | Description |
|---|---|
| SIEM Platform | Wazuh |
| Wazuh Server | Ubuntu VM |
| Monitored Endpoint | Kali Linux VM |
| Agent Name | kali-agent |
| Detection Type | Privilege activity |
| Event Source | sudo / syslog |

## Test Activity

Privilege-related activity was generated on the Kali Linux endpoint by running sudo commands during controlled lab testing.

```bash
sudo -l
sudo auditctl -w /etc/passwd -p r -k passwd_read
```

## Detection Summary

| Field | Value |
|---|---|
| Source Endpoint | kali-agent |
| Event Category | Privilege activity |
| Event Type | Successful sudo execution |
| Rule Description | Successful sudo to ROOT executed |
| Rule Group | sudo |
| Status | Detected |

## The Wazuh dashboard showed events related to:

```bash
Successful sudo to ROOT executed
sudo
syslog
audit
audit_configuration
```

## Security Relevance

Successful sudo activity is important in SOC monitoring because it indicates that a user executed commands with elevated privileges. While sudo activity can be legitimate, analysts should review privilege use to determine whether it was expected, authorized, and consistent with normal administrative behavior.

## Analyst Notes

Confirm whether the sudo activity was authorized.
Review the user account and endpoint involved.
Check which privileged commands were executed.
Correlate sudo activity with authentication, file changes, and audit events.
Escalate if privilege use is unexpected or followed by suspicious activity.

## Recommended Response

Identify the endpoint and user account involved.
Determine whether the sudo activity was expected.
Review related authentication and command activity.
Check for suspicious follow-up actions.
Document the event as authorized testing or escalate if unexpected.
Evidence

## Conclusion

The Wazuh agent successfully detected sudo-related privilege activity from the Kali Linux endpoint. This demonstrates how SOC analysts can monitor and review privilege usage on Linux systems.
