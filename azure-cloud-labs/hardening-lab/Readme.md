This lab simulates a real-world security detection scenario by hardening an Azure VM and detecting SSH brute-force attacks using Azure-native tools.

---

## 🎯 Objectives

- Deploy a secure Ubuntu VM in Azure
- Apply network security best practices (NSG + Just-In-Time Access)
- Ingest logs via Log Analytics
- Detect failed SSH login attempts using KQL
- Trigger alerts with Azure Monitor
- Control costs with alert rule optimization

---

## 🧰 Tools & Services Used

- Azure Virtual Machine (Ubuntu)
- Network Security Group (NSG)
- Just-In-Time (JIT) VM Access
- Log Analytics Workspace
- Azure Monitor & Alert Rules
- Azure Monitor Agent + Data Collection Rule (DCR)

---

## 📊 Detection Query (KQL)

Syslog
| where Facility == "auth"
| where SyslogMessage contains "Failed password"
| summarize FailedAttempts = count() by bin(TimeGenerated, 5m)
| where FailedAttempts > 5
