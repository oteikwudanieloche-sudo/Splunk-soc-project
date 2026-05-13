Dashboard Visualization Using Splunk

This phase of the project focuses on transforming raw log analysis into visual insights using a Splunk dashboard. The dashboard was created to provide a centralized and real-time view of web server activity, making it easier to monitor traffic patterns and detect anomalies.

The dashboard was built using data from Apache web server logs indexed in Splunk under the web_logs index. Various visual panels were created to represent different aspects of web activity.

The Traffic Over Time panel displays the volume of web requests over a selected time range. This visualization helps identify spikes in traffic, which may indicate abnormal activity such as automated requests or potential attacks.
The Top IP Addresses panel highlights the most active IP sources accessing the web server. This is useful for identifying users or systems generating high traffic. In a real-world scenario, unusually high activity from a single IP address may indicate suspicious behavior such as scanning or brute-force attempts.

The Top Pages panel shows the most frequently accessed web pages. This provides insight into user behavior and helps identify commonly targeted endpoints. Attackers often focus on sensitive paths such as login or admin pages, making this panel important for threat detection.

The HTTP Status Distribution panel visualizes the different response codes returned by the server, such as 200 (successful requests), 404 (not found), and 500 (server errors). A high number of error responses, particularly 404 errors, may indicate probing or scanning activity by attackers attempting to discover valid resources.

Overall, the dashboard provides a clear and interactive representation of web traffic and system behavior. It enhances situational awareness and allows faster identification of anomalies compared to raw log analysis.

This demonstrates the importance of visualization in a Security Operations Center (SOC), where analysts rely on dashboards to monitor systems, detect threats, and respond quickly to incidents.