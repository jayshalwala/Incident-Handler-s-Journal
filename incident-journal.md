# Incident Handler’s Journal – Ransomware Attack
**Company:** Small U.S. Health Care Clinic  
**Date:** 2024-07-23 09:00:00  

---

## 1. Situation
**What happened:**  
At 09:00 am local time, multiple employees reported inability to access patient records and saw a ransom note demanding payment for decryption keys. Systems were encrypted by a known healthcare‑targeting ransomware group.

**Scope:**  
- All Windows workstations encrypted  
- Domain file share and EMR database inaccessible  
- Business operations ceased  

---

## 2. Evidence Collected
- **Email Gateway Logs:** Identified malicious email with attachment `Invoice_071724.zip`.  
- **Endpoint Alerts:** Anti‑malware flagged `ransomware.exe` on initial host.  
- **Event Logs:** Windows Security logs showed execution of new service and mass file encryption.  

---

## 3. Root Cause Analysis
- **How:** Phishing email with weaponized attachment exploited unpatched Office vulnerability (CVE‑XXXX).  
- **Why:** Lack of employee phishing training and delayed patching on Windows workstations.  

---

## 4. Actions Taken
| Time       | Action                                                                                   | Outcome                          |
|------------|------------------------------------------------------------------------------------------|----------------------------------|
| 09:05 am   | Isolated affected workstations from network (disabled network adapter)                   | Stopped lateral spread           |
| 09:10 am   | Powered off compromised file server to prevent further encryption                       | Prevented backup encryption      |
| 09:15 am   | Contacted external incident response vendor and legal counsel                            | Engaged specialists              |
| 10:00 am   | Notified management, compliance, and regulatory teams (HIPAA requirements)               | Stakeholders informed            |
| 11:00 am   | Began forensic imaging of impacted systems                                               | Captured artifacts               |

---

## 5. Decisions & Recommendations
- **Pay Ransom?** Declined pending legal/insurance review.  
- **Short‑Term Remediation:**  
  - Restore from last known good backups.  
  - Rotate all domain and service account credentials.  
- **Long‑Term Controls:**  
  - Patch management policy to deploy Office security updates within 72 hours.  
  - Quarterly phishing awareness training with simulated campaigns.  
  - Deploy email attachment sandboxing and URL filtering.  

---

## 6. Lessons Learned
- Phishing remains primary vector—invest in user conditioning.  
- Verified backups are critical for recovery without paying ransom.  
- Clear incident playbooks accelerate response and reduce downtime.
