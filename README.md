wazuh-soc-lab
SOC Lab using Wazuh SIEM for monitoring and detecting security events on a Windows endpoint.
Wazuh SOC Lab (SIEM Project)

Overview
This project demonstrates a basic Security Operations Center (SOC) lab using Wazuh SIEM. The lab simulates real-world monitoring and detection of security events on a Windows endpoint.


Architecture
- Wazuh Server (Ubuntu)** → SIEM for log collection and analysis  
- Windows 10 → Target machine (agent installed)  
- Kali Linux → Attacker machine  


Tools Used
- Wazuh SIEM  
- Virtualization (VMware)  
- Kali Linux  
- Windows 10  


Use Case: Failed Login Detection

Attack Simulation
Multiple failed login attempts were generated on the Windows system.

Detection
Wazuh successfully detected:
- Logon failures  
- Authentication errors  
- Suspicious login activity  

---

Sample Alert

![Failed Login](images/failed-login.png)

- Description: Logon failure - unknown user or bad password  
- Severity Level: 5  
- MITRE ATT&CK: T1078 (Valid Accounts), T1531  


Dashboard

![Dashboard](images/dashboard.png)

Agent Status

![Agent](images/agent.png)


Event Details

![Event Details](images/event-details.png)

Key Learnings
- Understanding SIEM architecture  
- Log analysis and monitoring  
- Detecting authentication-based attacks  
- Working with MITRE ATT&CK mapping  

Conclusion
This lab demonstrates how SIEM tools like Wazuh can detect suspicious activities and help security analysts monitor systems effectively.

