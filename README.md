# 🔐 Active Directory SOC Monitoring Lab

## 📌 Project Overview

This project simulates a real-world enterprise **Active Directory environment** monitored from a Security Operations Center (SOC) perspective.

The lab demonstrates domain setup, centralized log collection, SIEM integration, attack simulation, and threat detection within a controlled environment.

---

## 🌐 Network & Domain Information

- **Domain Name:** MyDomain  
- **Network Range:** 192.168.10.0/24  

### 🖥️ Lab Machines

| System | Role | IP Address |
|--------|------|------------|
| Splunk Server | SIEM Server | 192.168.10.10 |
| Active Directory Server | Domain Controller | 192.168.10.7 |
| Windows 10 | Domain Client | DHCP |
| Kali Linux | Attacker Machine | 192.168.10.250 |

---

## 🏗️ Architecture Overview

- Active Directory Server acts as the **Domain Controller**.
- Windows 10 machine is joined to the domain.
- Splunk Server collects and analyzes logs.
- Kali Linux is used to simulate attacks.
- Sysmon and Splunk Universal Forwarder are installed on endpoints.
- All machines are connected within the subnet `192.168.10.0/24`.

---

## 🛠️ Technologies Used

- Windows Server (Active Directory Domain Services)
- Windows 10
- Splunk Enterprise
- Splunk Universal Forwarder
- Sysmon
- Kali Linux
- VirtualBox

---

## 🔄 Project Workflow

### 1️⃣ Active Directory Setup

- Installed and configured Active Directory Domain Services.
- Created domain: `MyDomain.local`
- Created users and groups.
- Joined Windows 10 client to the domain.
- Configured basic Group Policies.

---

### 2️⃣ Log Collection Configuration

- Installed Sysmon on:
  - Active Directory Server
  - Windows 10 Client
- Installed Splunk Universal Forwarder on both systems.
- Configured log forwarding to Splunk Server (192.168.10.10).
- Forwarded:
  - Windows Security Logs
  - System Logs
  - Sysmon Logs

---

### 3️⃣ SIEM Configuration (Splunk)

- Enabled receiving port for forwarders.
- Created indexes for Windows and Sysmon logs.
- Built dashboards for:
  - Failed logins (Event ID 4625)
  - Successful logins (Event ID 4624)
  - Special privileges assigned (Event ID 4672)
  - Account lockouts
  - Suspicious PowerShell execution

---

### 4️⃣ Attack Simulation (Kali Linux – 192.168.10.250)

Simulated attack scenarios such as:

- Brute-force login attempts
- Password spraying
- User enumeration
- Unauthorized authentication attempts
- Lateral movement testing

---

### 5️⃣ Detection & Monitoring

- Monitored authentication events.
- Correlated Sysmon process logs with Security logs.
- Detected suspicious login patterns from attacker IP.
- Analyzed privileged account usage.
- Investigated abnormal behavior using Splunk dashboards.

---

## 📊 Key Detection Use Cases

- Multiple failed logins from single IP
- Account lockout detection
- Admin privilege monitoring
- Suspicious process creation (Sysmon Event ID 1)
- Remote logon monitoring (RDP)
- New user account creation tracking

---

## 🎯 Skills Demonstrated

- Active Directory Administration
- SIEM Log Analysis
- Windows Event Log Investigation
- Threat Detection & Correlation
- SOC Monitoring Workflow
- Attack Simulation & Blue Team Analysis

---

## 👩‍💻 Author
Tanushka Kumbhar
Final Year B.Tech Computer Engineering Student  
Aspiring SOC Analyst
