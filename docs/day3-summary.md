# Day 3 – Attack Simulation Summary

## Objective

The objective of Day 3 was to simulate an SSH brute force attack, detect the activity using Splunk, identify the attacker IP address, and perform a basic security investigation.

---

# Severity Assessment

**Incident:** SSH Brute Force Attack

**Severity:** High

### Reason

- Multiple failed SSH login attempts were detected.
- The attack originated from a single source IP.
- Continuous password guessing indicates a brute force attack.
- If successful, the attacker could gain unauthorized access.

**Attacker IP**

```
192.168.64.12
```

**Target Server**

```
192.168.64.9
```

---

# MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|--------|-----------|----|
| Credential Access | Brute Force | T1110 |
| Initial Access *(if login succeeds)* | Valid Accounts | T1078 |

### Description

The attacker attempted multiple SSH logins using different passwords. Splunk detected repeated failed authentication events, indicating a brute force attack.

---

# Investigation Summary

## Detection Method

Splunk Search:

```spl
index=* "Failed password"
| rex "from (?<attacker_ip>\d+\.\d+\.\d+\.\d+)"
| stats count by attacker_ip
| sort -count
```

## Investigation Findings

- SSH authentication failures were detected.
- Source IP extraction identified the attacker.
- The attacker IP was **192.168.64.12**.
- The target server was **192.168.64.9**.
- No successful login was confirmed during this investigation (unless your lab included one).

## Evidence

- Splunk search results
- SSH authentication logs
- Extracted attacker IP
- Screenshots stored in `screenshots/day3/`

## Recommended Actions

- Block the attacker IP using the firewall.
- Disable password-based SSH authentication.
- Enable SSH key authentication.
- Monitor future authentication attempts.
- Configure Splunk alerts for repeated failed logins.

---

# Conclusion

Day 3 successfully demonstrated how Splunk can detect SSH brute force attacks, identify the attacker IP address, and support a basic SOC investigation using log analysis and SPL queries.
