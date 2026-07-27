# Day 5 Summary – Web Attack Detection

## Objective

Learn how to detect and investigate web attacks using Apache access logs and Splunk.

---

## Environment

- Attacker: Kali Linux (192.168.64.12)
- Target: Rocky Linux Web Server (192.168.64.9)
- SIEM: Splunk Enterprise

---

## Tasks Completed

- Verified Apache access logs
- Simulated web requests from Kali Linux
- Collected Apache logs in Splunk
- Investigated HTTP requests
- Identified attacker IP
- Reviewed HTTP status codes

---

## Splunk Search

```spl
index=* sourcetype=access_combined
```

---

## Investigation

Observed:

- Source IP: 192.168.64.12
- Target: Apache Web Server
- HTTP Methods:
  - GET
  - POST
- Status Codes:
  - 200 OK
  - 401 Unauthorized
  - 404 Not Found

---

## Skills Learned

- Apache Access Log Analysis
- HTTP Request Investigation
- Splunk Web Search
- Web Attack Analysis

---

## Result

Successfully detected web requests and investigated attacker activity using Splunk.
