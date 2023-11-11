# Postmortem: Unplanned Downtime in Gourmet Delights Online Ordering Platform  
Issue Summary:

Duration:
Start Time: November 10, 2023, 15:30 UTC
End Time: November 11, 2023, 02:45 UTC
Impact:
Online ordering service experienced a complete outage.
85% of users were affected, resulting in frustration and customer complaints.
Root Cause:
Database connection pool exhaustion due to a sudden spike in user traffic.
Timeline:

Issue Detection:
Detected on November 10, 2023, 15:30 UTC through a surge in error rates and customer complaints.
Detection Method:
Automated monitoring system triggered alerts for increased error rates and latency.
Customer complaints via social media and support channels.
Actions Taken:
Investigated backend services, suspecting server misconfigurations initially.
Assumed a potential DDoS attack and deployed mitigation measures.
Expanded server capacity to handle the increased load.
Misleading Paths:
Focused on network-related issues instead of database performance initially.
Investigated codebase for potential bugs, leading to wasted time on a false trail.
Escalation:
Escalated to the DevOps and Database teams as the issue persisted.
Involved senior engineers to expedite the resolution process.
Resolution:
Identified the root cause as database connection pool exhaustion.
Optimized connection pooling configurations to handle higher loads.
Implemented a temporary fix by restarting the database server to clear connections.
Communicated with users regarding the downtime and expected resolution time.
Root Cause and Resolution:

Root Cause:
The surge in user traffic exceeded the configured database connection pool limits.
Inefficient connection handling and long query times exacerbated the issue.
Resolution:
Optimized database connection pool settings for improved efficiency.
Implemented query optimizations to reduce database load.
Deployed a rolling restart of the system to apply configuration changes.
Monitored closely post-restart to ensure stability.
Corrective and Preventative Measures:

Improvements/Fixes:
Enhance monitoring to detect gradual traffic spikes and proactively scale resources.
Implement automated scaling policies for critical services.
Conduct regular load testing to identify potential bottlenecks.
Review and optimize database queries for efficiency.
Tasks to Address the Issue:
Update and document connection pool configurations for better scalability.
Develop and implement automated testing scripts for load testing.
Conduct a thorough review of the codebase for any potential bottlenecks.
Schedule regular training sessions for the support team on handling outage communication.
In conclusion, the unplanned downtime was a result of unforeseen traffic spikes overwhelming the database connection pool. Swift identification and resolution were achieved through collaborative efforts across multiple teams. Moving forward, the implementation of automated scaling, proactive monitoring, and codebase optimizations will fortify the system against similar incidents. Continuous vigilance and improvement remain crucial to providing a seamless online ordering experience for our valued customers.
