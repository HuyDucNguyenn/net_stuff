# SOC workflow
As we have covered SOC roles and its responsibity, now let se what we'll get in this part

Before talking about some flamboyant details, I genuinely believe that we should take a look to see some basic concepts that follow us throughout this journey

***The very first question is that where we got the data ?***   

## 1. Data Collection  
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
⇒ As a result we all know this is not just a logon but an actual attack from hacker ^^  

## 3. Alert Triage
> Let's see a case as a prime instance to see what tier 1    analyst will do ^^  
- As covered, alerts can come from many sources like endpoint. The thing is that we cannot identify whether they are true or false positive cases as the system just follow the rules that we set at first and let some 'weird' things go through !!! It turns out that there's still some positions for tier 1 analysts as they have to check all the cases to prevent there is no false positive cases from slipping through the cracks  
- Additionally, tier 1 have to give a verdict to each alert (decide escalation to higher level if needed)
- Finally, close alert if benign or trigger containment if confirmed

> So now just take a look to see the while picter after then =)))

- Incident Investigation: Tier 2/3 analysts perform deep dives using threat intel, MITRE, and forensic tools 
- Incident Response: Containment, eradication, and evidence preservation actions are executed
- Recovery & Reporting: Systems are restored, reports are filed, and lessons are used to improve defenses

By the way, I hope this is interesting enough to trigger your curiosity to click ⇒ ***[(SOC_tools.md)](./SOC_tools.md)***  😁😁😁