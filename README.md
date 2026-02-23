# 🔐 Active Directory SOC Monitoring Lab

## 📌 Project Overview

This project simulates a real-world **enterprise Active Directory environment** monitored from a **Security Operations Center (SOC)** perspective.

The lab is designed to understand:

- Active Directory infrastructure setup  
- Centralized log collection  
- SIEM integration  
- Attack simulation  
- Threat detection & analysis  

The environment replicates common enterprise attack scenarios such as brute-force attempts, unauthorized logins, privilege escalation, and lateral movement within a domain network.

---

## 🏗️ Lab Architecture

### 🌐 Domain Information

- **Domain Name:** MyDFIR  
- **Network:** 192.168.10.0/24  

### 🖥️ Machines in the Lab

| Machine | Role | IP Address |
|----------|------|------------|
| Splunk Server | SIEM | 192.168.10.10 |
| Active Directory Server | Domain Controller | 192.168.10.7 |
| Windows 10 | Domain Client | DHCP |
| Kali Linux | Attacker Machine | 192.168.10.250 |

---

## 🛠️ Technologies Used

- Windows Server (Active Directory Domain Services)
- Windows 10 Client
- Splunk Enterprise
- Splunk Universal Forwarder
- Sysmon
- Kali Linux
- VirtualBox (Hypervisor)

---

## 🔄 Project Workflow

### 1️⃣ Active Directory Setup
- Installed and configured **Active Directory Domain Services (AD DS)**.
- Created domain: `MyDFIR.local`
- Added users, groups, and applied basic domain policies.
- Joined Windows 10 client to the domain.

### 2️⃣ Log Collection Configuration
- Installed **Sysmon** on:
  - Active Directory Server
  - Windows 10 Client
- Installed **Splunk Universal Forwarder** on both systems.
- Configured log forwarding to Splunk Server (192.168.10.10).

### 3️⃣ SIEM Configuration (Splunk)
- Configured receiving port for forwarders.
- Created indexes for Windows and Sysmon logs.
- Built dashboards for:
  - Failed login attempts
  - Successful logins
  - Account lockouts
  - Suspicious PowerShell execution
  - Privilege escalation activity

### 4️⃣ Attack Simulation (Kali Linux)
Simulated common attack techniques such as:

- Brute-force login attempts
- Password spraying
- Enumeration of domain users
- Suspicious authentication attempts
- Lateral movement testing

### 5️⃣ Detection & Monitoring
- Monitored Event IDs (4624, 4625, 4672, etc.)
- Correlated Sysmon logs with Windows Security logs
- Identified suspicious IP activity (192.168.10.250)
- Analyzed attack patterns in Splunk dashboards

---

## 📊 Key Detection Use Cases

- Multiple failed logins from single IP
- Account lockout detection
- Admin privilege logins
- Suspicious PowerShell execution
- Unusual logon hours
- New user account creation
- Remote logon monitoring (RDP events)

---

## 🎯 Learning Outcomes

- Practical understanding of Active Directory security
- Hands-on SIEM log ingestion and analysis
- Real-world attack simulation and detection
- SOC-level monitoring and investigation workflow
- Event log analysis and threat correlation

---

## 👩‍💻 Author
Tanushka Kumbhar
Final Year B.Tech Computer Science Student  
Aspiring SOC Analyst | Blue Team Enthusiast  
