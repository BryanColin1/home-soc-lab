# SOC Investigation Report

## Executive Summary

This report documents a controlled SOC investigation using Wazuh alerts from a monitored Kali Linux endpoint. The investigation reviewed authentication activity, file integrity monitoring events, and privilege-related sudo activity generated during lab testing.

## Enviroment

| Component | Description |
|---|---|
| SIEM Platform | Wazuh |
| Wazuh Server | Ubuntu VM |
| Monitored Endpoint | Kali Linux VM |
| Agent Name | kali-agent |
| Lab Type | Controlled local SOC lab |

## Investigation Scope

The investigation focused on three alert categories:

| Detection | Category | Status |
|---|---|---|
| Failed Sudo Authentication | Authentication | Reviewed |
| File Integrity Monitoring | File activity | Reviewed |
| Successful Sudo Privilege Activity | Privilege activity | Reviewed |

## Timeline of Activity

| Step | Activity | Description |
|---|---|---|
| 1 | Failed sudo authentication | Incorrect sudo password attempts were generated and detected |
| 2 | File integrity monitoring | A test file was created, modified, and deleted |
| 3 | Successful sudo activity | Privileged sudo activity was detected from the endpoint |

## Findings

### Finding 1: Failed Sudo Authentication

Wazuh detected failed sudo authentication attempts from the Kali Linux endpoint. This activity may indicate user error, unauthorized privilege escalation attempts, or suspicious local access attempts.

### Finding 2: File Integrity Monitoring Activity

Wazuh detected file creation, modification, and deletion activity from the monitored endpoint. File integrity monitoring is useful for identifying unauthorized changes, system tampering, or suspicious file activity.

### Finding 3: Successful Sudo Privilege Activity

Wazuh detected successful sudo activity, indicating that privileged commands were executed on the endpoint. Successful sudo activity should be reviewed to confirm whether the action was authorized.

## Analyst Assessment

The observed activity was generated intentionally in a controlled lab environment. No real compromise occurred. However, the alerts represent common SOC investigation areas:

- Authentication failures
- File changes
- Privileged command execution

In a real environment, these events should be correlated to determine whether they are benign administrative activity or part of a suspicious sequence.

## Recommended Response

1. Confirm whether the activity was authorized.
2. Review the affected endpoint and user account.
3. Correlate authentication, file integrity, and privilege events.
4. Check whether failed attempts were followed by successful privileged access.
5. Investigate unexpected file changes or sensitive path modifications.
6. Escalate if activity is unauthorized or suspicious.

## Lessons Learned

- Wazuh can collect and display endpoint security events from a Linux agent.
- Authentication and sudo activity are useful indicators for SOC investigations.
- File integrity monitoring helps identify file creation, modification, and deletion events.
- Correlating multiple alert types provides stronger investigation context than reviewing alerts individually.

## Conclusion

This investigation demonstrated a basic SOC workflow using Wazuh. The lab successfully collected endpoint events, identified relevant alert categories, and documented analyst observations and response recommendations.
