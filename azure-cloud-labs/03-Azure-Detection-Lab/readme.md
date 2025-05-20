## 📘 Overview
This lab simulates vulnerability management in a hybrid environment by combining local vulnerability scanning with Azure-style risk analysis and reporting workflows.

---

## 🎯 Objective
- Practice vulnerability scanning using Nessus Essentials on a local network.
- Analyze and document vulnerabilities as if managing Azure VMs.
- Understand how hybrid environments (on-prem + cloud) are secured.

---

## ⚠️ Azure Limitation
Azure does not permit deploying intentionally vulnerable VMs such as Metasploitable due to platform restrictions.

---

## 💡 Workaround Setup (Local Lab)

### 🔧 Components
- **Scanner:** Linux VM running Nessus Essentials
- **Target:** Metasploitable
- **Environment:** Isolated virtual network using VirtualBox

### 🛠️ Tools
- Nessus Essentials
- Metasploitable 
- VirtualBox
- Azure Portal

---

## ☁️ Azure Integration Simulation
Even though the environment is local, the project mimics Azure practices:

- Simulated hybrid asset inventory
- Azure-style risk reporting
- Defender for Cloud process comparison

---

## 📝 What Was Done
- Nessus installed and configured on Linux VM
- Metasploitable scanned via network
- Vulnerability findings logged in a risk table
- Results analyzed as if part of Azure Defender for Cloud

---

## 📊 Risk Log Sample
A sample risk log with CVEs, severity, and remediation steps is included in `/risk-log/Risk_Log_Table.xlsx`

---

## 🚀 Next Steps
- Compare agent-based vs network-based vulnerability detection
