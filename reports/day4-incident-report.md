# Incident Report - SSH Brute Force

Alert: SSH Brute Force Attempt

Attacker IP: 192.168.64.12

Target IP: 192.168.64.9

Failed Login Attempts: 31

Successful Login: None

Severity: High

MITRE ATT&CK:
- T1110 - Brute Force

Containment:
- Review SSH logs
- Check services
- Block attacker IP
- Review SSH configuration

Conclusion:
True Positive

# Incident Report

## Incident Name

SSH Brute Force Attempt

## Summary

An attacker attempted to gain unauthorized SSH access to the Rocky Linux server using repeated password guessing.

## Investigation

Attacker IP:
192.168.64.12

Target IP:
192.168.64.9

Failed Login Attempts:
31

Successful Login:
None

## Evidence

- SSH authentication failure logs
- Multiple failed login attempts
- No successful authentication

## Severity

High

## Containment

- Block attacker IP using firewall
- Review SSH configuration
- Verify active SSH sessions
- Check authentication logs
- Continue monitoring

## Conclusion

True Positive

The attacker attempted multiple SSH logins but did not successfully access the server.
