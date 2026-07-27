# Web Attack Investigation Report

## Incident Summary

A web attack simulation was performed from Kali Linux against the Apache web server hosted on Rocky Linux.

---

## Attack Information

### Source IP

192.168.64.12

### Target IP

192.168.64.9

### Target Service

Apache HTTP Server

---

## Observed Requests

Example requests:

```text
GET /
GET /admin
GET /login.php
POST /login.php
```

---

## HTTP Status Codes

| Status | Meaning |
|---------|---------|
| 200 | Request Successful |
| 401 | Unauthorized |
| 404 | Resource Not Found |

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Reconnaissance | Active Scanning | T1595 |
| Initial Access | Exploit Public-Facing Application | T1190 |

---

## Severity

Medium

---

## Recommendations

- Monitor suspicious web requests.
- Review Apache access logs regularly.
- Restrict access to sensitive pages.
- Enable a Web Application Firewall (WAF).
- Continue monitoring using Splunk.

---

## Conclusion

The simulated web attack was successfully detected and investigated using Apache logs and Splunk searches.
