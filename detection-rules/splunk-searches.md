# SSH Brute Force Detection

## Search Failed Password
</>spl
index=* sourcetype=syslog "Failed password"

## Count Failed Logins
</>spl
index=* sourcetype=syslog "Failed password"
| stats count by host

## Find Attacker IP
</>spl
index=* "Failed password"
| rex "from (?<attacker_ip>\d+\.\d+\.\d+\.\d+)"
| stats count by attacker_ip
| sort -count
