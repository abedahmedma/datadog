├── **Infrastructure Monitoring**
│   ├── CPU Usage
│   │   ├── Monitor the percentage of CPU resources utilized by the system or processes.
│   │   └── Example: 80% CPU Usage
│   ├── Memory Usage
│   │   ├── Track the amount of RAM being used by the system or applications.
│   │   └── Example: 4 GB Memory Usage
│   ├── Disk Usage
│   │   ├── Monitor the amount of disk space being used by the system or specific drives.
│   │   └── Example: 60% Disk Usage on C Drive
│   ├── Network Traffic
│   │   ├── Measure the data transmitted and received by the system or network interfaces.
│   │   └── Example: 100 Mbps Network Traffic
│   ├── Server Uptime
│   │   ├── Track the duration the server has been running without interruptions.
│   │   └── Example: 30 days Server Uptime
│   └── System Load
│       ├── Monitor the system's workload, indicating its capacity and potential issues.
│       └── Example: System Load Average 2.5



├── **Application Performance Monitoring (APM)**
│   ├── Response Time
│   │   ├── Measure the time taken for an application to respond to a request.
│   │   └── Example: 250 ms Response Time
│   ├── Error Rate
│   │   ├── Track the percentage of requests that result in errors or failures.
│   │   └── Example: 5% Error Rate
│   ├── Database Query Performance
│   │   ├── Monitor the speed and efficiency of database queries within the application.
│   │   └── Example: 10 ms Database Query Performance
│   ├── API Latency
│   │   ├── Measure the time it takes for API calls to be processed.
│   │   └── Example: 50 ms API Latency
│   ├── User Session Duration
│   │   ├── Track the length of time users spend interacting with the application.
│   │   └── Example: 15 minutes User Session Duration
│   └── Code Execution Time
│       ├── Monitor the time taken for specific code segments or functions to execute.
│       └── Example: 20 ms Code Execution Time



├── **Log Management**
│   ├── Log Volume
│   │   ├── Measure the amount of log data generated over a specific period.
│   │   └── Example: 100 GB Log Volume
│   ├── Log Error Rate
│   │   ├── Track the percentage of log entries that contain errors or anomalies.
│   │   └── Example: 2% Log Error Rate
│   ├── Log Sources Integration
│   │   ├── Integrate and monitor logs from various sources within the system.
│   │   └── Example: Integration with Apache Logs
│   ├── Log Message Types
│   │   ├── Categorize and analyze different types of log messages for insights.
│   │   └── Example: Application Events, System Logs
│   ├── Log Retention Policy
│   │   ├── Define policies for retaining log data based on compliance or operational needs.
│   │   └── Example: 90-day Log Retention Policy
│   └── Log Parsing Accuracy
│       ├── Evaluate the accuracy of parsing log messages for meaningful information.
│       └── Example: 95% Log Parsing Accuracy


├── **Real User Monitoring (RUM)**
│   ├── Page Load Time
│   │   ├── Measure the time it takes for a web page to load completely for end-users.
│   │   └── Example: 3 seconds Page Load Time
│   ├── Time to First Byte (TTFB)
│   │   ├── Measure the time it takes for the first byte of a web page to be received by the browser.
│   │   └── Example: 150 ms Time to First Byte
│   ├── First Contentful Paint (FCP)
│   │   ├── Measure the time it takes for the first content to be painted on a web page.
│   │   └── Example: 1.5 seconds First Contentful Paint
│   ├── User Interactions per Session
│   │   ├── Track the number of interactions users have within a single session.
│   │   └── Example: 10 User Interactions per Session
│   └── Browser Error Rate
│       ├── Monitor the percentage of errors encountered by users in their browser.
│       └── Example: 1% Browser Error Rate


├── **Synthetics**
│   ├── Response Time
│   │   ├── Measure the time it takes for a synthetic test to complete.
│   │   └── Example: 500 ms Response Time
│   ├── Error Rate
│   │   ├── Track the percentage of synthetic tests that result in errors.
│   │   └── Example: 2% Error Rate
│   ├── Synthetic Test Success Rate
│   │   ├── Monitor the overall success rate of synthetic tests.
│   │   └── Example: 98% Test Success Rate
│   ├── Page Element Load Time
│   │   ├── Measure the time it takes for specific elements on a web page to load.
│   │   └── Example: 50 ms Page Element Load Time
│   ├── API Endpoint Availability
│   │   ├── Ensure the availability of API endpoints during synthetic tests.
│   │   └── Example: 100% API Endpoint Availability
│   └── Geographical Test Distribution
│       ├── Distribute synthetic tests across different geographical locations.
│       └── Example: Geographical Test Distribution (US, Europe, Asia)



├── **Security Monitoring**
│   ├── Number of Security Events
│   │   ├── Measure the total count of security events occurring in a given time period.
│   │   └── Example: 500 Security Events
│   ├── Severity of Security Events
│   │   ├── Assess the severity level of security events, indicating their criticality.
│   │   └── Example: High Severity Security Events
│   ├── Firewall Rule Violations
│   │   ├── Monitor instances where firewall rules are violated or breached.
│   │   └── Example: 10 Firewall Rule Violations
│   ├── Anomaly Detection in User Behavior
│   │   ├── Identify unusual patterns or deviations in user behavior for potential threats.
│   │   └── Example: Anomaly Detected in User Behavior
│   └── Authentication Failures
│       ├── Track the number of failed authentication attempts.
│       └── Example: 3 Authentication Failures


├── **Tracing**
│   ├── Trace Duration
│   │   ├── Measure the time it takes for a trace, representing a complete request journey.
│   │   └── Example: 50 ms Trace Duration
│   ├── Number of Spans
│   │   ├── Count the number of spans, representing individual operations, in a trace.
│   │   └── Example: 15 Spans in a Trace
│   ├── Database Query Traces
│   │   ├── Monitor traces specifically related to database queries.
│   │   └── Example: Database Query Trace Found
│   ├── Service Dependencies Mapping
│   │   ├── Visualize and understand dependencies between different services.
│   │   └── Example: Service A depends on Service B
│   ├── Error Rate of Traced Requests
│   │   ├── Track the percentage of traced requests that result in errors.
│   │   └── Example: 3% Error Rate in Traced Requests
│   └── Code Execution Traces
│       ├── Monitor traces specifically related to the execution of code.
│       └── Example: Code Execution Trace Identified



├── **Distributed Tracing**
│   ├── Latency Between Services
│   │   ├── Measure the time it takes for requests to travel between different services.
│   │   └── Example: 10 ms Latency Between Services
│   ├── Number of Retries
│   │   ├── Count the instances where requests are retried due to errors.
│   │   └── Example: 5 Retries in Requests
│   ├── Service Error Rate
│   │   ├── Track the percentage of errors occurring in a specific service.
│   │   └── Example: 2% Service Error Rate
│   ├── Cross-Service Communication Time
│   │   ├── Monitor the time taken for communication between different services.
│   │   └── Example: 20 ms Cross-Service Communication Time
│   ├── Distributed Transaction Success Rate
│   │   ├── Measure the success rate of transactions across distributed services.
│   │   └── Example: 98% Distributed Transaction Success Rate
│   └── Service Saturation Level
│       ├── Evaluate the percentage of time a service operates at or above capacity.
│       └── Example: 90% Service Saturation Level


├── **Container Monitoring**
│   ├── CPU Usage of Containers
│   │   ├── Measure the percentage of CPU resources used by individual containers.
│   │   └── Example: 70% CPU Usage of Container A
│   ├── Memory Usage of Containers
│   │   ├── Track the amount of memory used by individual containers.
│   │   └── Example: 300 MB Memory Usage of Container B
│   ├── Network Traffic of Containers
│   │   ├── Measure the amount of data transmitted and received by containers.
│   │   └── Example: 1 GB Network Traffic of Container C
│   ├── Container Health Checks
│   │   ├── Verify the health and status of containers through defined health checks.
│   │   └── Example: Container D is Healthy
│   ├── Orchestration System Metrics
│   │   ├── Monitor metrics related to the container orchestration system (e.g., Kubernetes).
│   │   └── Example: Kubernetes Pod Scaling Metrics
│   └── Container Restarts
│       ├── Count the number of times containers are restarted.
│       └── Example: Container E Restarted 3 Times



├── **Serverless Monitoring**
│   ├── Invocation Count of Serverless Functions
│   │   ├── Measure the number of times serverless functions are invoked.
│   │   └── Example: 1,000 Invocation Count of Function X
│   ├── Execution Time of Serverless Functions
│   │   ├── Monitor the time it takes for serverless functions to execute.
│   │   └── Example: 100 ms Execution Time of Function Y
│   ├── Cost of Serverless Functions
│   │   ├── Track the monetary cost associated with running serverless functions.
│   │   └── Example: $5 Cost of Serverless Functions in the Last Hour
│   ├── Cold Start Time
│   │   ├── Measure the time it takes for a serverless function to start from a cold state.
│   │   └── Example: 500 ms Cold Start Time for Function Z
│   ├── Serverless Function Errors
│   │   ├── Monitor the number of errors encountered by serverless functions.
│   │   └── Example: 5 Errors in Serverless Function W
│   └── Function Concurrency
│       ├── Track the number of concurrent executions of serverless functions.
│       └── Example: 20 Concurrent Executions of Function V



├── **Dashboards and Alerts**
│   ├── Key Metrics
│   │   ├── Highlight metrics that are crucial for monitoring the health and performance.
│   │   └── Example: CPU, Memory, and Network Usage
│   ├── Alert Thresholds
│   │   ├── Define values that, when exceeded, trigger alerts for specific metrics.
│   │   └── Example: Alert if CPU Usage exceeds 90%
│   ├── Alert Notifications
│   │   ├── Specify methods for notifying users when alerts are triggered (e.g., email, SMS).
│   │   └── Example: Email Notification for Critical Alerts
│   ├── Dashboard Widgets
│   │   ├── Components and visualizations on a dashboard providing a holistic view.
│   │   └── Example: Line Chart Showing Network Traffic Over Time
│   ├── Custom Alerting Rules
│   │   ├── Define specific rules for triggering alerts based on complex conditions.
│   │   └── Example: Alert if Both CPU and Memory Usage are High
│   └── Anomaly-Based Alerts
│       ├── Set up alerts triggered by unusual patterns detected through anomaly detection.
│       └── Example: Alert for Anomalous Spike in Request Response Time




├── **Integrations**
│   ├── Integrations with Other Tools and Platforms
│   │   ├── Connect Datadog to external tools/platforms for data exchange.
│   │   └── Example: Integration with AWS CloudWatch
│   ├── Streamlined Workflows
│   │   ├── Ensure Datadog is seamlessly integrated into existing operational workflows.
│   │   └── Example: Automated Incident Response Workflow
│   └── Enhanced Observability
│       ├── Provide a more comprehensive view of system or application health.
│       └── Example: Combined Metrics, Logs, and Traces for Improved Observability



├── **Anomaly Detection**
│   ├── Unusual Patterns in Metrics and Logs
│   │   ├── Identify uncommon patterns in metrics and log data.
│   │   └── Example: Sudden Spike in CPU Usage
│   ├── Alerts for Anomalies
│   │   ├── Trigger alerts when anomalies in metrics or logs are detected.
│   │   └── Example: Immediate Alert for Unusual Network Traffic
│   └── Improved Observability
│       ├── Enhance overall system visibility through proactive anomaly detection.
│       └── Example: Early Detection of Issues for Improved Observability



├── **Change Data Capture (CDC)**
│   ├── Real-Time Capture of Changes to Data
│   │   ├── Capture and track changes to data as they occur in real-time.
│   │   └── Example: Real-Time Changes in Database Records
│   ├── Monitoring of Data Integrity
│   │   ├── Monitor the consistency and accuracy of data to ensure integrity.
│   │   └── Example: Data Integrity Check Passed
│   └── Triggering of Alerts
│       ├── Set up alerts to notify users when unexpected changes to data are detected.
│       └── Example: Immediate Alert for Unusual Data Modifications


├── **Distributed Systems Monitoring**
│   ├── Health of Distributed Nodes
│   │   ├── Monitor the overall health and status of individual nodes in a distributed system.
│   │   └── Example: All Nodes Healthy in the Cluster
│   ├── Performance of Distributed Services
│   │   ├── Measure the performance metrics of services within a distributed system.
│   │   └── Example: 99% Availability of Service A
│   └── Interactions Between Distributed Components
│       ├── Track and analyze interactions and dependencies between components.
│       └── Example: Communication Flow Between Microservices



│   └── **Machine Learning for Observability**
│       └── Detection of Anomalies
│           ├── Utilize machine learning algorithms to identify unusual patterns in metrics and logs.
│           └── Example: ML Detected Anomaly in User Login Patterns



