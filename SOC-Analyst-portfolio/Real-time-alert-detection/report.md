Title: Alerting and Detection

To enhance monitoring capabilities, alerts were configured in Splunk to automatically detect suspicious activities in real time.

Three alert rules were created:

1. Failed Login Detection
This alert identifies multiple failed SSH login attempts from a single IP address, which may indicate a brute-force attack.

2. 404 Error Detection
This alert monitors excessive 404 HTTP responses, which may suggest scanning or probing of web resources.

3. High Traffic Detection
This alert detects unusually high numbers of requests from a single IP address, potentially indicating bot activity or denial-of-service attempts.

These alerts enable proactive monitoring and reduce the need for manual log analysis by automatically identifying potential threats.