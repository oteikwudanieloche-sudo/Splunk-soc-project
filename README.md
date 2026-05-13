Enterprise SOC Analyst Portfolio: End-to-End Splunk SIEM Engineering

Project Objective
This project demonstrates hands-on experience in SIEM engineering, log analysis, threat detection, and alert optimization using Splunk.

Over a multi-phase lifecycle, security logs were ingested, normalized, and analyzed to detect suspicious activities. Custom field extraction was implemented using regular expressions (Regex), followed by the development of analytical dashboards and automated alerting mechanisms designed to reduce false positives and alert fatigue.

. Phase 1: Dashboard Visualization & Security Monitoring

Raw log data was transformed into actionable security insights through structured dashboards designed for SOC visibility and rapid decision-making.

- HTTP Status Code Analysis:** Implemented pie chart visualizations to monitor web server response distribution.
- Security Insight: Identified abnormal spikes in `4xx` (client-side errors) and `5xx` (server-side errors), enabling differentiation between benign issues (e.g., broken links) and potential threats such as directory brute-force attacks or service disruption attempts.

. Phase 2 (Day 1): SSH Attack Detection & Failed Login Analysis

Focused on authentication logs to detect credential-stuffing and brute-force login attempts targeting Linux systems.

. Capabilities Demonstrated:
- Boolean search filtering
- Field extraction using Regex (`rex`)
- Multi-field aggregation
- Threshold-based detection logic

. Production SPL Query:
- spl
index=main "Failed password"
| rex field=_raw "for\s(?<user>\S+)\sfrom\s(?<src_ip>\d{1,3}(\.\d{1,3}){3})"
| stats count as Failures by src_ip, user
| where Failures > 5
| sort - Failures
Analytical Intent:
This detection logic distinguishes between normal user behavior (e.g., mistyped passwords) and malicious activity such as automated password spraying targeting privileged accounts (e.g., root).

. Phase 3 (Day 2): Web Log Analysis & High Traffic Detection
Developed detection mechanisms to identify abnormal traffic patterns, reconnaissance activity, and potential denial-of-service (DoS) behavior.
Capabilities Demonstrated:
Advanced field extraction using Regex
Data filtering and noise reduction
False-positive mitigation techniques
Production SPL Query:
Spl
index=web_logs
| rex field=_raw "(?<src_ip>\d{1,3}(\.\d{1,3}){3})"
| search src_ip!="127.0.0.1" AND src_ip!="::1"
| stats count as "Total Requests" by src_ip
| where 'Total Requests' > 5
| sort - "Total Requests"

Analytical Intent:
Filters out internal loopback traffic (127.0.0.1, ::1) to eliminate noise and isolate external sources, enabling accurate identification of suspicious or high-volume traffic patterns.

. Phase 4: Alert Automation & SOC Triage Optimization
Converted manual detection queries into automated alerting mechanisms aligned with real-world SOC operations.

Key Implementations:
Scheduled Alerts: Configured periodic execution of detection queries for continuous monitoring.
Alert Throttling: Implemented per-value throttling based on src_ip with a defined suppression window.

Operational Impact:
This approach ensures that repeated malicious activity from a single source generates only one alert within a defined timeframe, significantly reducing alert fatigue. At the same time, new threats from different IP addresses are still detected and escalated in real time.

Key Skills Demonstrated
SIEM Engineering (Splunk)
Log Analysis (Linux & Apache)
Threat Detection & Correlation
Regex-Based Field Extraction
Dashboard Visualization
Alert Engineering & Optimization
Incident Simulation & Validation

. Project Structure

splunk-soc-project/
│
├── README.md
├── LICENSE
│
├── phase-1-dashboard/
│   ├── screenshots/
│   └── report.md
│
├── phase-2-ssh-detection/
│   ├── screenshots/
│   ├── queries.txt
│   └── report.md
│
├── phase-3-web-analysis/
│   ├── screenshots/
│   ├── queries.txt
│   └── report.md
│
├── phase-4-alerting/
│   ├── screenshots/
│   └── report.md

. Project Status
✔ Completed

Author
Name: Oteikwu Daniel Oche
Role: Cybersecurity SOC Analyst (SOC Track) | Penetration Tester
Focus: SIEM, Threat Detection, and Incident Response
✔ Detection rules validated through simulation
✔ Dashboard and alerts fully operational
