# Splunk Searches

## Day 4 – SSH Brute Force Detection Alert

### Purpose

Detect multiple failed SSH login attempts that may indicate a brute force attack.

---

## Search Query

```spl
index=* sourcetype=syslog "Failed password"
```

---

## Alert Configuration

**Alert Name**

```
SSH Brute Force Detection
```

**Schedule**

```
Cron: * * * * *
```

(Runs every minute)

**Time Range**

```
Last 5 minutes
```

**Trigger Condition**

```
Number of Results > 15
```

**Trigger**

```
Once
```

---

## Expected Output

Example:

```
Failed password for invalid user admin
Failed password for root
Failed password for test
```

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Credential Access | Brute Force | T1110 |

---

## Severity

High

---

## Recommended Actions

- Identify attacker IP
- Identify target host
- Review SSH authentication logs
- Block attacker IP
- Review SSH configuration
- Continue monitoring for repeated attempts
