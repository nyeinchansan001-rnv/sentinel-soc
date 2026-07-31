# HTTP Status Codes
index=* sourcetype=acccess_combined
| rex field=_raw "\"\w+ [^\"]+ HTTP/\d\.\d\" (?<status>\d{3})"
| stats count by status

# Web Requests Over Time
index=* sourcetype=acccess_combined
| timechart count

# Top Attacker IPs
index=* sourcetype=acccess_combined
| rex field=_raw "\"\w+ [^\"]+ HTTP/\d\.\d\" (?<status>\d{3})"
| stats count by status

# Top Requested URLs
index=* sourcetype=acccess_combined
| rex field=_raw "\"(?<method>\S+)\s(?<uri>\S+)\sHTTP/\S+\""
| stats count by uri
| sort -count

# Recent Security Events
index=* sourcetype=acccess_combined
| table _time clientip method uri status useragent
| sort -_time

# Top User Agents
index=* sourcetype=acccess_combined
| rex field=_raw "\"(?<useragent>[^\"]+)\"$"
| stats count by useragent
| sort -count
