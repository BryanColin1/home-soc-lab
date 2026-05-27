# File Integrity Monitoring Detection

## Objective

Detect file creation, modification, and deletion activity on a monitored Kali Linux endpoint using Wazuh File Integrity Monitoring.

## Environment

| Component | Description |
|---|---|
| SIEM Platform | Wazuh |
| Wazuh Server | Ubuntu VM |
| Monitored Endpoint | Kali Linux VM |
| Agent Name | kali-agent |
| Detection Type | File Integrity Monitoring |
| Test Directory | `/home/kali/soc-test` |

## Test Activity

A test file was created, modified, and deleted on the Kali Linux endpoint to generate file integrity monitoring events.

```bash
mkdir -p /home/kali/soc-test
echo "SOC test file created" > /home/kali/soc-test/test-file.txt
echo "Modified during Wazuh FIM test" >> /home/kali/soc-test/test-file.txt
rm /home/kali/soc-test/test-file.txt
```

## Detection Summary

| Field | Value |
|---|---|
| Source Endpoint | kali-agent |
| Event Category | File Integrity Monitoring |
| Event Type | File creation, modification, deletion |
| Target Path | `/home/kali/soc-test/test-file.txt` |
| Alert Count | 3 |
| Status | Detected |

## Observed Alert Groups

| Alert Group | Purpose |
|---|---|
| syscheck | Wazuh file integrity monitoring event group |
| syscheck_file | File-related integrity monitoring event |
| syscheck_entry_added | File creation event |
| syscheck_entry_deleted | File deletion event |

## Observed Alert Types

The Wazuh dashboard showed alerts related to:
```bash
File added to the system
File deleted
Integrity checksum changed
```
Security Relevance

File integrity monitoring is important because unexpected file changes may indicate system tampering, malware activity, unauthorized configuration changes, or persistence attempts. SOC analysts use file change events to identify suspicious activity on monitored endpoints.

## Analyst Notes

Confirm whether the file activity was expected or authorized.
Review the affected file path and endpoint.
Check whether the changed file is located in a sensitive directory.
Correlate file changes with authentication, command execution, or privilege escalation events.
Determine whether the activity is benign testing or unauthorized modification.

## Recommended Response

Identify the affected endpoint and file path.
Confirm whether the file change was expected.
Review related events around the same timeframe.
Investigate suspicious file changes in sensitive directories.
Escalate if the activity appears unauthorized.

## Evidence



## Conclusion

The Wazuh agent successfully detected file creation, modification, and deletion activity on the Kali Linux endpoint. This demonstrates basic file integrity monitoring and shows how SOC analysts can identify file changes during endpoint monitoring.
