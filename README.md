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
4. **Threat Detection:** (Coming Soon)
