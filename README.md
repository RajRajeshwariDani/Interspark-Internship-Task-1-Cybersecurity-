# 🔎 Task 1 – Reconnaissance & Vulnerability Scanning

## 🎯 Objective

Performed reconnaissance and vulnerability scanning on an **authorized local Jenkins test environment** using Nmap and Nikto.

### Target

```text
127.0.0.1:8080

Tools Used
Kali Linux
Nmap
Nikto
Jenkins
Jetty
🔍 1. Nmap Service Enumeration
Command
nmap -sV 127.0.0.1
Result
8080/tcp   open   http   Jetty 12.1.10
Additional Scan
nmap -sV -sC 127.0.0.1
Findings
Port 8080/tcp was open.
HTTP service was detected.
Jetty 12.1.10 was identified.
Jenkins was identified as the web application.
robots.txt was detected.

🌐 2. Nikto Vulnerability Scan
Command
nikto -h http://127.0.0.1:8080
Save Results
nikto -h http://127.0.0.1:8080 -output nikto-report.txt
View Report
cat nikto-report.txt
Scan Result

📊 Findings Summary
Finding
Risk
Mitigation
Missing X-Frame-Options
Medium
Configure anti-framing policy
Missing X-Content-Type-Options
Low/Medium
Add nosniff
Jenkins information disclosure
Low/Medium
Reduce information exposure
Anonymous access information
Medium
Review authentication and permissions
Web resource exposure
Medium
Review access controls
Severity is a preliminary assessment based on the scan observations. Actual impact depends on application configuration and exposure.

🛡️ Recommendations
Keep Jenkins and plugins updated.
Review authentication and authorization.
Disable unnecessary anonymous access.
Configure appropriate HTTP security headers.
Minimize server/application information disclosure.
Restrict administrative services to authorized users/networks.
Perform regular vulnerability assessments.
1 host tested
13 items reported
0 errors

🔄 Assessment Workflow
Authorized Target
       ↓
Nmap Enumeration
       ↓
Open Port & Service Detection
       ↓
Nikto Web Scanning
       ↓
Finding Identification
       ↓
Risk Analysis
       ↓
Security Recommendations
       ↓
Final Report

🧠 Skills Demonstrated
Kali Linux
Nmap
Nikto
Network Reconnaissance
Service Enumeration
Web Server Scanning
Vulnerability Identification
HTTP Security Headers
Information Disclosure Analysis
Security Documentation
Risk Analysis
Security Mitigation
