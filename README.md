# Wazuh SIEM Lab – Deployment, Detection & Alert Triage

## 📌 Objective
This project demonstrates end-to-end deployment of a Wazuh SIEM environment and detection of simulated security events through log analysis, FIM, IDS rules, and Sysmon integration.

## 🏗️ Environment Setup
- **Wazuh Manager:** Ubuntu 22.04 LTS  
- **Endpoints:** Windows 10 (agents installed)  
- **Tools:** Sysmon, Nmap, PowerShell, Wazuh Dashboard  

## 🔧 Configuration Performed
### 1. Wazuh Manager Setup
- Installed Wazuh Manager + Filebeat + Dashboard  
- Enabled security modules (FIM, IDS, Sysmon integration)

### 2. Agent Deployment
- Installed Wazuh Windows agents  
- Connected agents to manager (verified through dashboard)

### 3. Sysmon Integration
- Installed Sysmon with SwiftOnSecurity config  
- Confirmed event forwarding to Wazuh

---

## 🛡️ Detection Scenarios

### **Scenario 1: Unauthorized File Modification (FIM)**
- Created/modifed sensitive files  
- Wazuh FIM generated alerts  
- Verified integrity hashes + timestamps  

### **Scenario 2: Port Scanning (IDS)**
- Conducted Nmap scan from attacker machine  
- Wazuh IDS triggered OSSEC rule alerts  
- Identified source IP + scan type  

### **Scenario 3: Suspicious Process Execution (Sysmon)**
- Executed encoded PowerShell command  
- Sysmon events forwarded → Wazuh caught:
  - Process creation (Event ID 1)  
  - Network connection events  

### **Scenario 4: Brute-Force Authentication Attempts**
- Simulated multiple failed logins  
- Wazuh generated brute force alerts  

---

## 🧪 Alert Triage Workflow
1. **Identify alert rule & description**  
2. **Review source → user → process → hash**  
3. **Correlate Sysmon + event logs**  
4. **Determine if event is malicious or benign**  
5. **Document evidence & conclusions**

---

## 📄 Documentation & Deliverables
- `deployment-steps.md`
- `detection-scenarios.md`
- `fim-alert-sample.json`
- `sysmon-events.log`
- `nmap-scan-alerts.png` (optional screenshot)

---

## 🎯 Key Learnings
- Hands-on SIEM deployment experience  
- Understanding of alert pipelines  
- Ability to triage alerts using logs + Sysmon  
- Basic detection engineering concepts  
