# Lab Architecture

## 1. Project Overview
This project is a virtualized Security Operations Center (SOC) home lab built to explore security monitoring, centralized log collection, endpoint visibility, and security event analysis using Wazuh.
The environment is designed to simulate a basic enterprise security monitoring infrastructure. It combines a Linux-based Wazuh server with Windows endpoints to collect, process, and investigate security-related events.
The primary objective is to gain practical experience with SIEM operations, endpoint monitoring, log analysis, and security event investigation.

## 2. Infrastructure Components
The lab environment consists of the following components:

| Component | Description |
| :--- | :--- |
| **Oracle VirtualBox** | Virtualization platform used to host the lab environment. |
| **Linux Server (Ubuntu)** | Hosts the Wazuh server infrastructure (16 GB RAM). |
| **Wazuh Manager** | Collects and analyzes security events received from monitored endpoints. |
| **Wazuh Indexer** | Stores and indexes security event data. |
| **Wazuh Dashboard** | Provides a web-based interface for monitoring and investigating security events. |
| **Windows Server 2025 (DC001)** | Windows endpoint and Active Directory domain controller monitored within the lab environment. |
| **Wazuh Agent** | Installed on Windows endpoints to collect and forward security data (Active). |
| **Microsoft Sysmon** | Provides detailed system activity and process-related event logging (Default configuration). |

## 3. System Architecture
The lab uses a centralized monitoring architecture.
The Linux server hosts the Wazuh infrastructure, while Windows endpoints generate security-related events.
Wazuh Agents collect configured endpoint logs and forward them to the Wazuh Manager for processing and analysis.
The Wazuh Indexer stores the processed event data, which can then be accessed and investigated through the Wazuh Dashboard.

### Architecture Diagram

```text
           ORACLE VIRTUALBOX
                  |
       -----------------------
       |                     |
  UBUNTU SERVER         WINDOWS SERVER 2025
       |                     |
  Wazuh Manager          Wazuh Agent
       |                     |
  Wazuh Indexer          Windows Event Logs
       |                     |
  Wazuh Dashboard        Microsoft Sysmon
       |                     |
       <--- Event Collection

*Security Event Flow*
```

## 4. Log Collection and Data Flow
The monitoring process follows these main stages:
1. **Event Generation:** Windows endpoints generate system, authentication, and security-related events.
2. **Log Collection:** Wazuh Agents collect configured log sources from monitored endpoints.
3. **Event Forwarding:** Collected events are forwarded to the Wazuh Manager.
4. **Event Analysis:** Wazuh processes incoming events and evaluates them against its detection rules.
5. **Data Storage:** Event data is indexed and stored by the Wazuh Indexer.
6. **Security Monitoring:** Analysts use the Wazuh Dashboard to search, monitor, and investigate security events.

## 5. Monitoring Scope
The initial monitoring scope includes the following event categories:
- Windows authentication events.
- Successful logon events (Event ID 4624).
- Failed logon events (Event ID 4625).
- Process creation events (Sysmon Event ID 1).
- General Windows security and system events.

Additional monitoring capabilities and detection scenarios will be introduced as the lab develops.

## 6. Network Architecture
The lab uses VirtualBox networking (Bridged Adapter) to enable communication between the Linux server and Windows endpoints.
The Wazuh Agent communicates with the Wazuh Manager through the configured network connection.
Network addressing, adapter configuration, and communication ports are documented separately in the environment setup and agent deployment documentation.

## 7. Project Scope and Development
This home lab is an ongoing practical learning project.
Future development activities include:
- Expanding Windows event collection.
- Integrating and validating Sysmon event forwarding.
- Developing security detection scenarios.
- Investigating authentication-related events.
- Analyzing suspicious process activity.
- Documenting troubleshooting procedures.
- Improving detection and monitoring capabilities.

---
* **Project:** Wazuh SOC Home Lab
* **Platform:** Oracle VirtualBox
* **SIEM:** Wazuh
* **Operating Systems:** Linux (Ubuntu) and Windows Server 2025
* **Status:** In Development

