# SOC Tools

ok now let's see what we actually got  
<img src="assets/image.png" alt="alt text" width="127"/>
## 1. SIEM
![stuff](assets/SIEM.png)
The question is what is this hmm....
> Central system that collects, aggregates, correlates, and analyzes logs from across your environment  
![stuff](assets/splunk.jpg)  

This is exactly where we work every single day. This called splunk - one of SIEM tools that we use within triage phase. without this, we probably miss some important event that correlated to malicious activities 😎  
## 2. SOAR
>SOAR platforms automate incident response using playbooks, reducing manual work and response time  

It's just like a "brain" that connects other security tools together and controls them using available rules (playbooks)

## 3. TIP (Threat Intelligence Platform)
This is absolutely what we use to save our time  
> TIP provides security teams with information on known malware and other threats

<u>***For example:***</u>
Just imagine that attacker send us a malware, basically we have to analyze it but in this case let's see this is an old malware which means that there's someone else did so now we just bring this file (its IOCs like hash) to TIP and then if it tells that "this file is marked as malicious since other people analyzed it" at a result we don't need to spend time on it at all

