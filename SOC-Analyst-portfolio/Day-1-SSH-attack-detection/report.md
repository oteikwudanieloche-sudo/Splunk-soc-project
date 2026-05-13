Title:
Failed Login Attempt Analysis Using Splunk

. Objective:
To detect and analyze failed login attempts indicating possible brute-force attacks.

. Data Source:
Linux authentication logs (/var/log/auth.log) ingested into Splunk.

. Findings:
Multiple failed login attempts detected
Source IP identified: 127.0.0.1
Targeted usernames: wronguser
Attack pattern suggests brute-force attempt

. Conclusion:
The system experienced repeated failed login attempts from a single IP, indicating a simulated brute-force attack.

. Recommendation:
Enable account lockout policies
Monitor repeated login failures
Block suspicious IP addresses