# Swarm PageSpeed Insights and Reporting

 This project leverages the Swarm framework to analyze website performance using Google's PageSpeed Insights API. It automates the collection of performance metrics, generates a concise report, and sends it via email.

 ## Features

1. PageSpeed Analysis: Fetches performance metrics such as First Contentful Paint (FCP), First Input Delay (FID), and Cumulative Layout Shift (CLS) for given URLs.
2. Report Generation: Compiles a detailed report based on the metrics collected.
3. Email Notification: Sends the generated report to a specified email address.

## How it Works?

 Initialize Swarm Client: The Swarm client is initialized to manage the workflow.


### Define Agents: (Two Swarms)
1. PageSpeed Agent: This agent fetches performance metrics (FCP, FID, CLS) for specified URLs using the PageSpeed Insights API. (Swarm 1)
2. Report Agent: This agent compiles a report based on the collected metrics.(Swarm 1)
3. Triage Agent: Manages the sequence of operations, ensuring that metrics are collected before the report is generated.(Swarm 1)
4. Email Agent : uses SMTP to send the generated report to a specified recipient.(Swarm 2)

### Run Workflow:
The triage agent executes the pagespeed function to collect metrics.
It then calls generate_report to create a concise performance report.
Then uses response to send email with email Agent
