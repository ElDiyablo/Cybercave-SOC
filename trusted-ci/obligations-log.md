# Cybercave SOC — Institutional Obligations Log

**Institution:** Murray State University
**Program:** Cybercave Security Operations Center
**Prepared by:** ElDiyablo (SOC Lead)
**Reviewed by:** Prof. R. Joyce (Faculty Advisor)
**Date:** June 2026
**Status:** Draft — Pending Faculty Advisor Approval

---

## Purpose

This document records all legal, regulatory, contractual, and institutional
obligations that apply to the Cybercave SOC and its operations. Maintaining
this log is a requirement of the Trusted CI Framework (Must 8 — Institutional
Obligations Log) and ensures the SOC operates within all applicable
boundaries.

This log must be reviewed each semester and updated whenever new obligations
are identified or existing ones change.

---

## 1. Federal Legal Obligations

### FERPA — Family Educational Rights and Privacy Act
**Applies to:** Any SOC activity that could expose student educational records
**Requirement:** SOC analysts must not access, retain, or disclose student
educational records without authorization. Network logs that could reveal
student academic activity must be handled with appropriate protections.
**Current Status:** 🟡 Partial — No formal FERPA training for SOC analysts
**Action Required:** Add FERPA awareness to analyst onboarding materials

---

### CFAA — Computer Fraud and Abuse Act
**Applies to:** All SOC monitoring and investigation activities
**Requirement:** SOC activities must remain within explicitly authorized
scope. Unauthorized access to systems — even for security purposes —
violates federal law. All monitoring must be conducted only on systems
explicitly authorized by the faculty advisor and university IT.
**Current Status:** ✅ Met — Scope is defined in mission-statement.md
and SECURITY.md
**Action Required:** Ensure all analysts read and acknowledge scope
boundaries during onboarding

---

### CISA Cybersecurity Advisories
**Applies to:** SOC threat intelligence and detection activities
**Requirement:** SOC should monitor CISA advisories for active threats
affecting higher education and incorporate relevant indicators into
detection operations.
**Current Status:** 🟡 Partial — No formal process for monitoring CISA
advisories
**Action Required:** Add CISA advisory monitoring to weekly shift checklist

---

## 2. State Obligations

### Kentucky Data Breach Notification Law (KRS 365.732)
**Applies to:** Any confirmed data breach involving Murray State systems
**Requirement:** Murray State is required to notify affected individuals
and the Kentucky Attorney General within a defined timeframe following
a confirmed breach involving personal information.
**Current Status:** 🟡 Partial — SOC has incident ticketing but no formal
escalation path to trigger university breach notification procedures
**Action Required:** Define escalation procedure connecting SOC incident
tickets to university IT Security and legal counsel for breach notification
assessment

---

### Kentucky Postsecondary Education Privacy Act
**Applies to:** Student data handled during SOC operations
**Requirement:** Student data must be protected and used only for
authorized educational purposes.
**Current Status:** ✅ Met — SOC scope excludes direct access to student
data systems
**Action Required:** Document this exclusion explicitly in scope statement

---

## 3. Institutional Obligations

### Murray State University Acceptable Use Policy
**Applies to:** All SOC analyst activities on university systems
**Requirement:** All SOC analysts must comply with Murray State's
Acceptable Use Policy for university computing resources. Monitoring
activities must be conducted only for authorized security purposes.
**Current Status:** 🟡 Partial — Policy compliance assumed but not
formally acknowledged by analysts
**Action Required:** Add Acceptable Use Policy acknowledgment to analyst
onboarding checklist

---

### Murray State University Data Governance Policy
**Applies to:** Network telemetry and log data handled by the SOC
**Requirement:** Data collected and processed by the SOC must comply
with university data classification and handling requirements.
**Current Status:** 🔴 Not Met — No formal data classification applied
to SOC log data
**Action Required:** Work with Murray State IT to classify SOC log data
and document appropriate handling procedures

---

### Murray State University Information Security Policy
**Applies to:** All SOC tools, systems, and operations
**Requirement:** SOC operations must align with university information
security policies and standards.
**Current Status:** 🟡 Partial — SOC uses industry-standard tools and
frameworks but formal alignment with university policy has not been
documented
**Action Required:** Request copy of Murray State Information Security
Policy and document alignment

---

### Faculty Advisor Authorization
**Applies to:** All SOC monitoring activities and tool deployments
**Requirement:** All SOC operations must be conducted under the explicit
authorization of the faculty advisor (Prof. R. Joyce). Any expansion of
scope or addition of new tools requires faculty advisor approval.
**Current Status:** ✅ Met — Prof. R. Joyce serves as faculty advisor
and program owner
**Action Required:** Document formal authorization in a signed memo
each semester

---

## 4. Contractual Obligations

### GitHub Terms of Service
**Applies to:** SOC GitHub repository and GitHub Pages site
**Requirement:** Repository content must comply with GitHub's Terms of
Service. No malware, no exposed credentials, no content that violates
GitHub policies.
**Current Status:** ✅ Met — SECURITY.md documents prohibited content;
CI/CD workflow scans for exposed secrets
**Action Required:** Review annually

---

### Tool Terms of Service

| Tool | Provider | Key Obligation | Status |
|------|----------|----------------|--------|
| AlienVault OTX | AT&T Cybersecurity | Free tier — no redistribution of raw data | ✅ Compliant |
| VirusTotal | Google | Free tier — rate limits apply; no automated bulk scanning | ✅ Compliant |
| AbuseIPDB | AbuseIPDB | Attribution required when sharing data | ✅ Compliant |
| Shodan | Shodan | Academic use — no commercial redistribution | ✅ Compliant |
| Elastic (ELK) | Elastic | Open source license — self-hosted | ✅ Compliant |
| TryHackMe | TryHackMe | Educational use only | ✅ Compliant |
| LetsDefend | LetsDefend | Educational use only | ✅ Compliant |

---

## 5. Ethical Obligations

### Analyst Code of Conduct
All SOC analysts are expected to uphold the following ethical obligations:

| Obligation | Description | Enforcement |
|------------|-------------|-------------|
| Confidentiality | Network telemetry and investigation details must not be shared outside authorized channels | SOC Lead review |
| Scope adherence | Analysts must operate only within defined SOC scope | Faculty advisor authorization |
| Data minimization | Collect only the data necessary for security monitoring | Shift supervisor review |
| Non-disclosure | Confirmed incidents must not be disclosed publicly without authorization | Escalation procedure |
| Honest reporting | Ticket documentation must accurately reflect observations | Peer review |

---

## 6. Obligations Tracking

### Open Action Items

| # | Obligation | Action Required | Owner | Due Date | Status |
|---|------------|-----------------|-------|----------|--------|
| 1 | FERPA | Add FERPA training to onboarding | SOC Lead | Next semester | 🔴 Open |
| 2 | KRS 365.732 | Define breach escalation procedure | SOC Lead + IT | 30 days | 🔴 Open |
| 3 | Acceptable Use | Add policy acknowledgment to onboarding | SOC Lead | 30 days | 🔴 Open |
| 4 | Data Governance | Classify SOC log data with IT | SOC Lead + IT | 90 days | 🔴 Open |
| 5 | Info Security Policy | Document alignment with MSU policy | SOC Lead | 90 days | 🔴 Open |
| 6 | Faculty Authorization | Formalize signed semester authorization | Faculty Advisor | Each semester | 🟡 In Progress |
| 7 | CISA Advisories | Add to weekly shift checklist | SOC Lead | 30 days | 🔴 Open |

---

## 7. Stakeholder Map

| Stakeholder | Role | Relationship to SOC |
|-------------|------|---------------------|
| Prof. R. Joyce | Faculty Advisor | Program owner and authorizing official |
| ElDiyablo | SOC Lead | Primary operator and site developer |
| SOC Analysts | CYS Students | Shift operators and ticket writers |
| Murray State IT Security | University IT | Escalation target for confirmed incidents |
| Murray State CISO | University Leadership | Institutional oversight |
| Department Chair (CYS) | Academic Leadership | Academic program oversight |
| Murray State Legal Counsel | University Legal | Breach notification and compliance |
| Murray State Students | Campus Community | Primary beneficiaries of security awareness resources |
| Murray State Faculty/Staff | Campus Community | Indirect beneficiaries of SOC monitoring |

---

## Review & Approval

| Role | Name | Status | Date |
|------|------|--------|------|
| SOC Lead | ElDiyablo | Draft prepared | June 2026 |
| Faculty Advisor | Prof. R. Joyce | Pending review | |
| Murray State IT | | Pending | |

---

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | June 2026 | ElDiyablo | Initial draft |

---

*Cybercave SOC — Murray State University*
*This log must be reviewed each semester and updated when obligations change.*
*Next review date: December 2026*
