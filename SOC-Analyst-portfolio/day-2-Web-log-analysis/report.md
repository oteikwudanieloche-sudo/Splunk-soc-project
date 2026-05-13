FINAL REPORT (DAY 2)
Title: Web Log Analysis Using Splunk (Apache Logs Monitoring)

Objective:
To analyze Apache web server logs using Splunk in order to detect traffic patterns, identify suspicious behavior, and understand web activity.
Data Source:
Log file:
/var/log/apache2/access.log
Index used:
web_logs
Key Findings:
. Traffic Overview
Total events successfully ingested
Confirms proper Splunk configuration
. Top IP Addresses
Some IPs generated higher traffic
Could indicate:
Normal users
Bots or scanners
. Most Accessed Pages
Certain endpoints received more requests
Helps understand:
Popular content
Attack targets
. HTTP Errors (404)
Multiple 404 errors detected
Possible causes:
Broken links
Directory scanning attempts
. Suspicious Behavior
High request count from specific IPs
Potential:
Brute force
DoS-like activity
. Field Extraction
Successfully extracted:
IP addresses
Status codes
Enabled structured analysis

Conclusion:
The analysis demonstrated how Splunk can be used to monitor web server logs, detect anomalies, and identify potential security threats. High traffic IPs and repeated errors indicate possible suspicious activity that should be further investigated.

Tools Used:
Splunk Enterprise
Ubuntu (Apache Server)
Terminal (for log generation)