# 🛡️ Wazuh SOC Lab (SIEM Project)

>>> Overview
This project demonstrates a Security Operations Center (SOC) lab built using Wazuh SIEM. The lab simulates real-world security monitoring by collecting and analyzing logs from a Windows endpoint.

The objective of this project is to understand how SIEM tools detect suspicious activities such as failed login attempts and provide actionable security insights.

---

--> Architecture
The lab consists of three virtual machines:

- **Wazuh Server (Ubuntu)**  
  - Acts as the SIEM platform  
  - Collects, analyzes, and visualizes logs  

- **Windows 10 (Agent)**  
  - Target system being monitored  
  - Sends logs to Wazuh  

- **Kali Linux (Attacker)**  
  - Used to simulate attack scenarios  

---

## ⚙️ Tools & Technologies
- Wazuh SIEM  
- VMware Workstation  
- Ubuntu Server  
- Windows 10  
- Kali Linux  

---

## ⚙️ Configuration

###  Wazuh Server (Ubuntu)
- Installed Wazuh all-in-one deployment  
- Enabled web dashboard for visualization  
- Opened required ports (1514, 1515)  

###  Windows Agent
- Installed Wazuh agent on Windows 10  
- Configured manager IP: **192.168.145.135**  
- Imported authentication key  
- Verified agent is active and connected  

###  Network Setup
- All VMs connected via NAT network  
- Ubuntu IP: **192.168.145.135**  
- Windows IP: **192.168.145.134**  
- Verified connectivity using ping  

###  Logging & Monitoring
- Collected Windows event logs:
  - Logon success and failure  
  - System activity  
- Alerts generated in Wazuh dashboard  

---

--> Attack Simulation

### Failed Login Attack
- Multiple incorrect login attempts were performed on the Windows system  
- This simulates a brute force or unauthorized access attempt  

---

--> Detection & Alerts

Wazuh successfully detected:

- Logon failures  
- Authentication errors  
- Suspicious login activity  

### Sample Alert

>> Failed Login

- **Description:** Logon failure – unknown user or bad password  
- **Severity Level:** 5 (Medium)  
- **MITRE ATT&CK:** T1078 (Valid Accounts), T1531  

---

--> Event Analysis

 Summary
A failed login attempt was detected on the Windows endpoint, indicating an authentication request with invalid credentials.

--> Network Information
- **Source IP:** 127.0.0.1 (Localhost)  
- Indicates the activity originated locally  

--> Process Details
- **Process:** `svchost.exe`  
- **Logon Process:** User32  
- **Authentication:** Negotiate  

--> Interpretation
- Local authentication failure  
- Could indicate:
  - User error  
  - Brute force attempt (if repeated)

---

>> Event Details

---

--> Dashboard

>> Dashboard

The dashboard provides an overview of:
- Security events  
- Alert severity  
- System activity  

---

--> Agent Status

>> Agent

- Confirms Windows endpoint is actively monitored  
- Ensures log collection is functioning correctly  

---

--> Key Learnings
- Understanding SIEM architecture  
- Log collection and analysis  
- Detecting authentication-based attacks  
- Working with MITRE ATT&CK framework  
- Real-time monitoring of security events  

---

--> Limitations
- Network-based attacks (e.g., Nmap scans) are not detected by default  
- Requires additional tools like Sysmon or IDS for advanced detection  

---

--> Conclusion
This project demonstrates how Wazuh SIEM can be used to monitor endpoints, detect suspicious activities, and assist security analysts in identifying potential threats.

---

--> Future Improvements
- Integrate Sysmon for advanced logging  
- Add network intrusion detection (Snort/Suricata)  
- Implement automated alert responses  

---
