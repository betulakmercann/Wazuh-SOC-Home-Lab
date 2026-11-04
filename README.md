# Wazuh SOC Home Lab

A hands-on **SOC (Security Operations Center) Home Lab** built to explore centralized security monitoring, Windows event collection, and security event analysis using Wazuh.

## Project Overview

This project focuses on building a virtualized security monitoring environment using VirtualBox, Linux, Windows Server 2025, Wazuh, and Sysmon.

The main objective was to integrate a Windows Server endpoint into a centralized monitoring infrastructure, collect security events, and investigate them through the Wazuh Dashboard.

## Lab Architecture

**Environment Components:**

- **Virtualization:** Oracle VirtualBox
- **SIEM Platform:** Wazuh
- **Operating System (Manager):** Linux
- **Endpoint:** Windows Server 2025 (DC001)
- **Endpoint Monitoring:** Wazuh Agent
- **System Monitoring:** Sysmon

## Implemented Features

- Wazuh Manager, Indexer, and Dashboard deployment.
- Windows Server endpoint integration using Wazuh Agent.
- Sysmon integration for process monitoring.
- Centralized Windows event collection.
- Security event monitoring and investigation.
- Event analysis through Wazuh Dashboard.

## Event Monitoring and Analysis

The following Windows event types were collected and examined:

| Event ID | Description |
|---|---|
| 1 | Sysmon - Process Creation |
| 4624 | Windows - Successful Logon |
| 4625 | Windows - Failed Logon |

Controlled authentication tests were performed to generate security events and verify their collection in Wazuh.

## Screenshots

Screenshots of the lab environment, agent status, and collected security events will be available in the `screenshots/` directory.

## Project Scope

This repository documents the initial setup and practical implementation of a personal SOC Home Lab.

The project demonstrates hands-on experience with SIEM deployment, endpoint integration, Windows event collection, and basic security event investigation.

## Disclaimer

This lab was created for educational and cybersecurity learning purposes. All testing was performed in a controlled virtual environment.

---

**Project Type:** Blue Team / SOC Home Lab  
**Status:** Initial implementation completed
