# Alert Report

## Alert Name

SSH Brute Force Detection

## Severity

High

## Description

The alert detects multiple failed SSH authentication attempts that may indicate a brute force attack.

## Search Query

index=* sourcetype=syslog "Failed password"

## Trigger Condition

Number of Results > 15

## Detection Results

Events:
34

Status:
Triggered Successfully

## Recommended Actions

- Block attacker IP
- Review SSH logs
- Check authentication attempts
- Monitor further activity
