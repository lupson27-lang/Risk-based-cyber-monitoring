# 📄 monitoring_strategy.md

## Risk-Based Monitoring Strategy (IT & OT)

### Purpose
This document defines a **risk-driven monitoring approach** based on the previously defined `risk_register.md`. It specifies **what is monitored, how it is monitored, and why**, ensuring alignment with **enterprise risk management, GRC frameworks, and OT/IT constraints**.

---

### Monitoring Strategy Overview

| Asset / System | Monitoring Type | Data Sources / Telemetry | Detection Logic / Criteria | Escalation Path | Frequency / Notes |
|----------------|----------------|-------------------------|---------------------------|----------------|-----------------|
| Domain Controllers / Identity Services | Authentication & Privilege Monitoring | Active Directory logs, Sysmon, SIEM event feeds | Unusual login times, multiple failed logins, privilege changes, new admin accounts | SOC analyst → IT Security Manager → CISO | Continuous real-time monitoring; periodic review for orphan accounts |
| Customer Data / Database Servers | Data Access Monitoring | Database logs, query audit logs, DLP alerts | Unusual query volumes, access from unknown IPs, unexpected privilege escalations | DB Admin → Security Analyst → Compliance Officer | Real-time alerts; weekly reporting for trend analysis |
| Email / Collaboration Tools | Phishing & Malware Monitoring | Email gateway logs, attachment sandboxing, SIEM correlation | Mass email anomalies, known malware signatures, suspicious attachments | SOC analyst → IT Security Manager → End-User Awareness Team | Continuous; automated alerts with quarterly awareness metrics |
| Critical Application Servers | Application Behavior & Integrity Monitoring | Application logs, error patterns, SIEM correlation | Unexpected process execution, configuration changes, abnormal errors | Application Owner → Security Analyst → IT Security Manager | Real-time; review weekly for trending anomalies |
| Network Infrastructure | Network Traffic & Device Monitoring | Firewall logs, IDS/IPS, switch/router logs, NetFlow/SFlow | Rogue devices, anomalous traffic flows, unexpected configuration changes | Network Admin → Security Analyst → IT Security Manager | Continuous; exceptions documented for legacy segments |

---

### Key Principles

1. **Risk-Driven Prioritization**  
   Monitoring is **based on business-criticality** rather than tool capabilities or alert volume.

2. **Coverage Awareness**  
   All blind spots or limitations are **documented in `coverage_gaps_and_accepted_risk.md`**, including OT endpoints, legacy systems, and third-party environments.

3. **Ownership & Accountability**  
   Each alert has a **clear owner**, escalation path, and documented decision authority.

4. **Integration with GRC**  
   Alerts feed into **risk registers, incident response playbooks, and executive dashboards**, ensuring monitoring is **evidence for governance and audit**.

5. **Periodic Review & Continuous Improvement**  
   Monitoring strategy is **reviewed quarterly** to ensure alignment with evolving risks, asset changes, and regulatory requirements.

---

### Notes for OT / Energy / Healthcare Extension

- **OT / Industrial Control Systems**: Monitor PLC communications, SCADA alarms, and safety events. Detection criteria are adjusted for operational safety and reliability.  
- **Healthcare**: Include medical device telemetry, patient data access logs, and HIPAA compliance events.  
- **Energy / Manufacturing**: Include critical OT network monitoring, control system anomalies, and safety-impacting signals.  

---

### Why This File Matters

This file demonstrates that you can:
- Convert **risk entries into actionable monitoring objectives**
- Align **technical detection with governance priorities**
- Anticipate **limitations and escalation paths**
- Communicate **formally and clearly** for leadership and audit purposes
