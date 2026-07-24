# Day 4 Summary

## Objective

Create and test a Splunk alert for SSH brute force detection.

## Tasks Completed

- Created SSH Brute Force Detection alert
- Configured cron schedule
- Configured trigger condition
- Simulated SSH brute force attack
- Verified alert triggering
- Investigated alert results

## Alert Configuration

Alert Name:
SSH Brute Force Detection

Search:
index=* sourcetype=syslog "Failed password"

Schedule:
Every 1 minute (Cron)

Trigger:
Number of Results > 15

## Results

Alert successfully triggered.

Events Detected:
34

## Skills Learned

- Splunk Alert Creation
- Cron Scheduling
- Alert Trigger Conditions
- SOC Alert Investigation
