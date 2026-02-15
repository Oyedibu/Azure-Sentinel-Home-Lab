# Azure-Sentinel-Home-Lab
A hybrid cloud SOC lab utilizing Microsoft Sentinel, Azure Arc and KQL to monitor on premises endpoints
# Hybrid SOC Lab: Microsoft Sentinel & Azure Arc

## Objective
This lab aims to establish a cloud-native SIEM (Microsoft Sentinel) to monitor a hybrid environment. By connecting a physical Windows 11 endpoint via Azure Arc, I simulate real-world security operations including log ingestion, threat hunting with KQL, and incident response.

## Technologies Used
* **SIEM:** Microsoft Sentinel
* **Hybrid Management:** Azure Arc (Connected Machine Agent)
* **Log Analytics:** Kusto Query Language (KQL)
* **Cloud Platform:** Microsoft Azure
* **Endpoint:** Windows 10 (Physical Laptop)

## Lab Steps
1. **Infrastructure Deployment:** Provisioned a Log Analytics Workspace and enabled Microsoft Sentinel.
2. **Hybrid Connection:** Onboarded a local Windows machine using Azure Arc to bridge the gap between on-premise hardware and cloud monitoring.
3. **Telemetry Configuration:** Created Data Collection Rules (DCR) to stream Security Events into the SIEM.
4. ### Phase 2: Threat Detection & KQL Hunting
* **Scenario:** Simulated an unauthorized local login attempt (Brute Force) on the Windows 11 endpoint.
* **Detection:** Utilized Kusto Query Language (KQL) in Microsoft Sentinel to filter for Event ID 4625 (Failed Logon).
* **KQL Query Used:**
  SecurityEvent
  | where EventID == 4625
  | where Computer has "jayeola"
  | project TimeGenerated, Computer, Account, IpAddress, LogonType

* **Observation:** The SIEM successfully ingested telemetry via the Azure Monitor Agent (AMA), revealing four failed interactive logon attempts (Logon Type 2) from the local host.
* ### Phase 3: Incident Management & Automation
* **Automation:** Created a **Scheduled Analytics Rule** to monitor for brute-force patterns.
* **Alert Logic:** Configured the rule to trigger an Incident when more than 2 failed attempts occur within a 5-minute window.
* **Entity Mapping:** Mapped `Account`, `Host`, and `IPAddress` entities to enable deep-dive investigations.
* **Incident Response:** Successfully triggered the alert by simulating failed logins. Used the **Sentinel Investigation Graph** to visualize the relationship between the target host and the failed account.
* 
