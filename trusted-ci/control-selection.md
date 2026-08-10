# Cybercave SOC — Control Selection Report

**Institution:** Murray State University
**Program:** Cybercave Security Operations Center
**Prepared by:** ElDiyablo (SOC Lead)
**Reviewed by:** Prof. R. Joyce (Faculty Advisor)
**Date:** June 2026
**Framework References:** NIST CSF 2.0, CIS Controls v8, MITRE ATT&CK
**Status:** Draft — Pending Faculty Advisor Approval

---

## Purpose

This report maps current Cybercave SOC tools and processes to established
cybersecurity control frameworks. It documents which controls are
implemented, partially implemented, or not yet addressed — fulfilling
the Trusted CI Framework Must 16 (Baseline Security Controls) and
supporting the Gap Analysis remediation roadmap.

---

## Framework Overview

The SOC uses three complementary frameworks:

| Framework | Purpose | How We Use It |
|-----------|---------|---------------|
| NIST CSF 2.0 | Organizational security structure | Guides SOC function organization |
| CIS Controls v8 | Prioritized technical controls | Identifies specific control gaps |
| MITRE ATT&CK | Adversary behavior mapping | Drives detection rule development |

---

## Section 1: NIST CSF 2.0 Mapping

The NIST Cybersecurity Framework organizes controls into six functions:
Govern, Identify, Protect, Detect, Respond, Recover.

### GV — Govern
| Subcategory | Description | SOC Implementation | Status |
|-------------|-------------|-------------------|--------|
| GV.OC-01 | Organizational mission understood | Mission statement documented | ✅ Met |
| GV.OC-02 | Stakeholders identified | Obligations log stakeholder map | 🟡 Partial |
| GV.OC-03 | Legal obligations understood | obligations-log.md | 🟡 Partial |
| GV.RM-01 | Risk management policy established | Not formally documented | 🔴 Gap |
| GV.PO-01 | Policy established and communicated | SECURITY.md, user-guide.md | 🟡 Partial |

### ID — Identify
| Subcategory | Description | SOC Implementation | Status |
|-------------|-------------|-------------------|--------|
| ID.AM-01 | Asset inventory maintained | tools/index.html tool inventory | ✅ Met |
| ID.AM-02 | Software inventory maintained | tools/index.html | ✅ Met |
| ID.RA-01 | Vulnerabilities identified | OTX, VirusTotal, AbuseIPDB | ✅ Met |
| ID.RA-02 | Threat intelligence received | OTX pulses, CISA advisories | 🟡 Partial |
| ID.RA-06 | Risk responses prioritized | Ticket severity classification | 🟡 Partial |

### PR — Protect
| Subcategory | Description | SOC Implementation | Status |
|-------------|-------------|-------------------|--------|
| PR.AA-01 | Access control implemented | VPN + analyst credentials | ✅ Met |
| PR.AA-02 | Identity verified | Cyber range authentication | ✅ Met |
| PR.AT-01 | Awareness training provided | getting-started/index.html | 🟡 Partial |
| PR.AT-02 | Staff trained | resources/index.html | 🟡 Partial |
| PR.DS-01 | Data at rest protected | ELK index access controls | 🟡 Partial |
| PR.PS-01 | Configuration management | Not formally documented | 🔴 Gap |

### DE — Detect
| Subcategory | Description | SOC Implementation | Status |
|-------------|-------------|-------------------|--------|
| DE.AE-02 | Anomalies analyzed | Kibana alert triage workflow | ✅ Met |
| DE.AE-04 | Impact determined | Ticket severity classification | ✅ Met |
| DE.AE-06 | Findings communicated | Incident ticket system | ✅ Met |
| DE.CM-01 | Networks monitored | PA NGFW → ELK pipeline | ✅ Met |
| DE.CM-06 | External services monitored | OTX threat intelligence | ✅ Met |
| DE.CM-09 | Computing hardware monitored | Palo Alto firewall logs | ✅ Met |

### RS — Respond
| Subcategory | Description | SOC Implementation | Status |
|-------------|-------------|-------------------|--------|
| RS.MA-01 | Incident managed | ticketing/index.html workflow | ✅ Met |
| RS.MA-02 | Incidents triaged | 6-step ticket anatomy | ✅ Met |
| RS.CO-02 | Incidents reported | Google Form ticket submission | ✅ Met |
| RS.CO-03 | Information shared | Blog advisories published | ✅ Met |
| RS.AN-03 | Analysis performed | MITRE ATT&CK mapping in tickets | ✅ Met |
| RS.MI-01 | Incidents contained | Escalation to IT security | 🟡 Partial |

### RC — Recover
| Subcategory | Description | SOC Implementation | Status |
|-------------|-------------|-------------------|--------|
| RC.RP-01 | Recovery plan executed | Not formally documented | 🔴 Gap |
| RC.CO-03 | Recovery communicated | Not formally documented | 🔴 Gap |

---

## Section 2: CIS Controls v8 Mapping

CIS Controls v8 defines 18 control groups prioritized by implementation
group (IG1 = basic, IG2 = intermediate, IG3 = advanced).

| CIS Control | Description | SOC Implementation | IG Level | Status |
|-------------|-------------|-------------------|----------|--------|
| CIS 1 | Inventory of Enterprise Assets | tools/index.html | IG1 | ✅ Met |
| CIS 2 | Inventory of Software Assets | tools/index.html | IG1 | ✅ Met |
| CIS 3 | Data Protection | ELK access controls | IG1 | 🟡 Partial |
| CIS 4 | Secure Configuration | Not formally documented | IG1 | 🔴 Gap |
| CIS 5 | Account Management | VPN + GitHub access controls | IG1 | 🟡 Partial |
| CIS 6 | Access Control Management | Analyst credentials + VPN | IG1 | 🟡 Partial |
| CIS 7 | Continuous Vulnerability Management | OTX, VirusTotal monitoring | IG1 | 🟡 Partial |
| CIS 8 | Audit Log Management | ELK log ingestion pipeline | IG1 | ✅ Met |
| CIS 9 | Email & Web Browser Protections | resources/index.html guidance | IG1 | 🟡 Partial |
| CIS 10 | Malware Defenses | PA NGFW threat blocking | IG1 | ✅ Met |
| CIS 11 | Data Recovery | Not documented | IG1 | 🔴 Gap |
| CIS 12 | Network Infrastructure Management | PA NGFW + ELK pipeline | IG2 | 🟡 Partial |
| CIS 13 | Network Monitoring & Defense | Kibana dashboards + alerts | IG2 | ✅ Met |
| CIS 14 | Security Awareness Training | getting-started + resources pages | IG1 | 🟡 Partial |
| CIS 15 | Service Provider Management | obligations-log.md tool ToS | IG2 | 🟡 Partial |
| CIS 16 | Application Software Security | SECURITY.md, secret scanning | IG2 | 🟡 Partial |
| CIS 17 | Incident Response Management | ticketing/index.html | IG1 | ✅ Met |
| CIS 18 | Penetration Testing | Out of SOC scope | IG2 | N/A |

---

## Section 3: MITRE ATT&CK Detection Coverage

This table maps current SOC detection capabilities to MITRE ATT&CK tactics.

| Tactic | ID | Detection Capability | Tool | Coverage |
|--------|----|---------------------|------|----------|
| Initial Access | TA0001 | Phishing detection via PA logs | ELK + PA NGFW | 🟡 Partial |
| Execution | TA0002 | Malicious process indicators | PA threat logs | 🟡 Partial |
| Persistence | TA0003 | Outbound C2 beacon detection | ELK correlation | 🟡 Partial |
| Defense Evasion | TA0005 | URL filtering bypass attempts | PA NGFW | 🟡 Partial |
| Credential Access | TA0006 | Password spray detection | ELK auth log analysis | ✅ Detected |
| Discovery | TA0007 | Port scan detection | PA threat logs | ✅ Detected |
| Lateral Movement | TA0008 | Internal traffic anomalies | ELK network analysis | 🔴 Limited |
| Collection | TA0009 | Data staging indicators | Not currently monitored | 🔴 Gap |
| Command & Control | TA0011 | C2 traffic via threat category | PA NGFW + OTX | ✅ Detected |
| Exfiltration | TA0010 | Large outbound transfers | PA traffic logs | 🟡 Partial |
| Impact | TA0040 | Ransomware indicators | PA threat category | 🟡 Partial |

---

## Section 4: Control Gaps Summary

### Critical Gaps (address immediately)
| Gap | Framework | Recommended Control |
|-----|-----------|-------------------|
| No recovery plan | NIST RC | Draft basic business continuity procedure |
| No secure configuration baseline | CIS 4 | Document ELK and PA configuration standards |
| No data recovery procedure | CIS 11 | Define backup and recovery for ELK indices |
| Limited lateral movement detection | ATT&CK TA0008 | Develop internal traffic correlation rules |

### Moderate Gaps (address within 90 days)
| Gap | Framework | Recommended Control |
|-----|-----------|-------------------|
| Partial data protection | CIS 3 | Document ELK data classification and access controls |
| Partial account management | CIS 5 | Formalize access provisioning and revocation |
| Partial vulnerability management | CIS 7 | Add formal CVE monitoring to shift checklist |
| Partial phishing detection | ATT&CK TA0001 | Develop email-based phishing detection rules |

### Low Priority Gaps (address within 6 months)
| Gap | Framework | Recommended Control |
|-----|-----------|-------------------|
| Partial awareness training | CIS 14 | Build formal analyst training curriculum |
| Partial service provider management | CIS 15 | Complete tool ToS compliance review |
| Partial application security | CIS 16 | Expand SECURITY.md with code review checklist |

---

## Section 5: Recommendations

### Immediate Actions
1. Draft a basic recovery/continuity procedure for SOC operations
2. Document ELK and Palo Alto configuration baselines
3. Develop internal traffic correlation rules for lateral movement detection
4. Add CVE monitoring and CISA advisory review to weekly shift checklist

### Short Term (90 days)
1. Formalize access provisioning and revocation procedures
2. Develop email-based phishing detection rules in Kibana
3. Complete data classification for ELK log indices with Murray State IT
4. Build formal analyst training curriculum with progression milestones

### Long Term (6 months)
1. Expand detection coverage to Collection and Exfiltration tactics
2. Conduct tabletop incident response exercise
3. Present control selection report to Murray State IT for review
4. Re-assess CIS Controls implementation group target (IG1 → IG2)

---

## Approval & Review

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
*This report should be updated each semester as controls are implemented.*
*Next review date: December 2026*
