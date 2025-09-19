# Splunk Log Analysis — Windows Security Events

## 📌 Overview
This project demonstrates the use of **Splunk 9.3.2** for analyzing **8,000+ Windows Security logs**. The primary focus was on high-value security event IDs related to **privileged logons, process creation, and security group management changes**. The aim was to improve SOC visibility and triage workflows through dashboards, correlation searches, and event trend analysis.

---

## ⚙️ Setup
- **Data Source**: Windows Security logs (EVTX exports ingested into Splunk).
- **Splunk Version**: 9.3.2.
- **Analysis Approach**:
  - Created searches for critical security event IDs.
  - Built dashboards for event counts, top categories, and timelines.
  - Combined correlation searches to identify risky privilege activity.

---

## 🎯 Objectives
- Detect **privileged logons (4672)** and investigate process creation (4688).  
- Monitor **security group changes (4799)** for signs of privilege escalation.  
- Build SOC dashboards to visualize event frequency and categories.  
- Support faster incident response with correlation queries.  

---

## 🔍 Key Event IDs & Categories
- **4672** — Special Logon  
- **4688** — Process Creation  
- **4799** — Security Group Management  

Other significant events observed in dataset:  
- **5379, 4624, 5058, 5061, 5059** (logon/logoff, service shutdown, audit policy change).  

---

## 📊 Results
- **Total Events Analyzed**: 8,000+ Windows Security log entries.  
- **Top Event IDs**: 5379, 4624, 4672, 4799, 5061 (with 4672 and 4799 being high-value security signals):contentReference[oaicite:0]{index=0}.  
- **Audit Results**:  
  - Audit Success: 8,076 events  
  - Audit Failure: 52 events:contentReference[oaicite:1]{index=1}  
- **Task Categories Breakdown**:  
  - User Account Management: 3,668 events  
  - Logon: 1,384 events  
  - Special Logon: 1,280 events  
  - Security Group Management: 736 events:contentReference[oaicite:2]{index=2}  
- Built correlation between **special logon (4672)** and **process creation (4688)** → useful to detect privilege misuse.

📄 Full project report: (docs/SIEM_EVENTS_OVERVIEW.pdf)
