# SOC workflow
As we have covered SOC roles and its responsibity, now let se what we'll get in this part

Before talking about some flamboyant details, I genuinely believe that we should take a look to see some basic concepts that follow us throughout this journey

***The very first question is that where we got the data ?***   

## 1. DATA COLLECTION  
This is just simply a process that we collect raw data from various sources across an organization’s IT environment

| Source Type | Machines | Info Provided |
| :--- | :--- | :--- |
| Network Devices | Routers, Switches, Firewalls, WAF, IDS | Traffic flow, allowed/dropped connections, routing anomalies |
| Endpoints (Devices) | PCs, Laptops, Mac | File access, process execution, command-line args, registry chngs |
| Servers & Applications | Web servers, DB servers, Apps | Authentication logs, error codes, HTTP requests, DB queries |
| Identity & Access Mgmt | Active Directory, Okta, LDAP | Login successes/failures, privilege escalations, lockouts |
| Cloud Infrastructure | AWS CloudTrail, Azure Monitor, GCP Audit logs | API calls, resource changes, cloud network connection logs |
| Security Tools | AV, EDR, DLP, SIEM | Malware detections, alerts, policy violations |
| Threat Intel & External Sources | OSINT, VirusTotal, commercial feeds | Known malicious IPs/domains, file hashes |
## 2. Normalization & Correlation
**Normalization is the process of converting various log formats from different sources into a common structured schema**  
<u>***For example:***</u>  
> - A firewall log says “src_ip” 
> - A Linux syslog says “source-address” 
> - A cloud log says “ip.src”  

The point is we cannot remember each different format, therefore we normolize them into a stardard field like "source_ip"

Correlation is the process of linking multiple normalized events across systems to detect suspicious patterns that single events alone would miss  
<u>***For example:***</u>  
* A first even says that user A log in (in this case, it marked as normal action)  
* Then the following even says that this user run a malware in his computer  
⇒ As a result we all know this is not just a logon but a actual attack from hacker ^^