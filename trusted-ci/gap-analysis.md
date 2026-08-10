# Cybercave SOC — Trusted CI Framework Gap Analysis Report

**Institution:** Mississippi State University (MSU)
**Program:** Cybercave Security Operations Center
**Prepared by:** ElDiyablo (SOC Lead)
**Reviewed by:** Prof. R. Joyce (Faculty Advisor)
**Date:** June 2026
**Framework:** Trusted CI Cybersecurity Program Framework

---

## Executive Summary

This report evaluates the Cybercave SOC against the Trusted CI Framework's
"16 Musts" across four pillars: Mission Alignment, Governance, Resources,
and Controls. The assessment identifies current compliance status, gaps,
and a prioritized remediation roadmap.

**Overall Compliance Score: 9 / 16 Musts Met**

| Pillar | Musts Met | Total Musts | Status |
|--------|-----------|-------------|--------|
| Mission Alignment | 3 | 4 | 🟡 Partial |
| Governance | 2 | 4 | 🟡 Partial |
| Resources | 2 | 4 | 🔴 Gap |
| Controls | 2 | 4 | 🟡 Partial |

---

## Pillar 1: Mission Alignment

### Must 1 — Written Mission Statement
**Status:** ✅ Met

The SOC has a documented mission statement published on the public-facing
GitHub Pages site (about/index.html) and in the LAUNCH.md handover document.

> "The Cybercave Security Operations Center exists to defend the university's
> digital infrastructure, develop the next generation of cybersecurity
> professionals, and serve as a model for student-led security operations."

**Gap:** The mission statement does not explicitly reference MSU's research
mission or academic goals. Trusted CI specifically requires alignment with
the institution's research and academic objectives.

**Recommendation:** Update the mission statement to include explicit language
about supporting MSU's research community and academic mission.

---

### Must 2 — Defined Scope
**Status:** ✅ Met

The SOC scope is documented — monitoring campus network traffic via Palo Alto
NGFW logs ingested into ELK SIEM. Scope boundaries are defined in SECURITY.md
and the LAUNCH.md document.

**Gap:** Scope does not explicitly address research data systems or
research network segments.

**Recommendation:** Expand scope documentation to clarify coverage of
research-adjacent network infrastructure.

---

### Must 3 — Stakeholder Identification
**Status:** 🟡 Partial

Key stakeholders identified:
- Faculty Advisor: Prof. R. Joyce
- SOC Lead: ElDiyablo
- SOC Analysts: student participants

**Gap:** No formal mapping to institutional stakeholders (CISO, Research
Office, IT Directors). Customers of the SOC (researchers, faculty, students)
are not formally documented.

**Recommendation:** Complete a stakeholder map identifying all SOC customers
and institutional owners. See trusted-ci/stakeholder-map.md.

---

### Must 4 — Alignment with Institutional Mission
**Status:** 🔴 Not Met

The SOC currently operates primarily as a student training program with
secondary security value to the university. There is no formal documentation
linking SOC activities to MSU's strategic research and academic mission.

**Recommendation:** Draft a formal alignment document connecting SOC
operations to MSU's institutional goals. Present to faculty advisor
for approval.

---

## Pillar 2: Governance

### Must 5 — Defined Cybersecurity Lead
**Status:** ✅ Met

SOC Lead (ElDiyablo) is identified in all documentation as the primary
technical lead. Faculty Advisor (Prof. R. Joyce) serves as program owner.

**Gap:** No formal succession plan if SOC Lead graduates or leaves.

**Recommendation:** Document succession procedures and cross-train at
least one backup SOC Lead.

---

### Must 6 — Master Program Document
**Status:** 🟡 Partial

LAUNCH.md and user-guide.md partially fulfill this requirement. The site
and its documentation serve as the program's operational reference.

**Gap:** No single consolidated "Master Program Document" exists that
covers all governance elements in one place — mission, scope, roles,
reporting structure, and policy references.

**Recommendation:** Create trusted-ci/master-program.md consolidating
all governance elements.

---

### Must 7 — Reporting Structure
**Status:** 🔴 Not Met

No formal reporting structure to MSU leadership is documented. The SOC
currently reports informally to the faculty advisor.

**Recommendation:** Define and document a formal reporting chain:
SOC Lead → Faculty Advisor → Department Chair → CISO (or equivalent).
Include reporting cadence (weekly, monthly, semester).

---

### Must 8 — Institutional Obligations Log
**Status:** 🔴 Not Met

No formal log of legal, regulatory, or contractual obligations has been
created. The SOC handles student PII and network data that may be subject
to FERPA and institutional data governance policies.

**Recommendation:** Create trusted-ci/obligations-log.md documenting
all applicable legal and institutional requirements.

---

## Pillar 3: Resources

### Must 9 — Staffing Plan
**Status:** 🟡 Partial

The careers/index.html page defines three roles (Analyst Intern, Detection
Engineer, Documentation Contributor). Onboarding is documented in
getting-started/index.html.

**Gap:** No formal staffing plan documenting minimum headcount, skill
requirements, or backup coverage for analyst shifts.

**Recommendation:** Document minimum viable staffing levels and a
coverage plan for shift continuity.

---

### Must 10 — Budget & Sustainability
**Status:** 🔴 Not Met

No budget documentation exists. The SOC currently operates on zero direct
budget — tools are free/open-source, hosting is free (GitHub Pages),
and staffing is volunteer student labor.

**Gap:** Sustainability is at risk if the faculty advisor changes or
university support is withdrawn.

**Recommendation:** Document current resource dependencies and draft
a sustainability plan identifying what institutional support is needed
to maintain operations.

---

### Must 11 — Tool Inventory
**Status:** ✅ Met

tools/index.html provides a comprehensive inventory of all SOC tools
organized by category (SIEM, threat intel, detection, network analysis,
training).

**Gap:** No formal tool ownership, licensing, or renewal tracking exists.

**Recommendation:** Add ownership and license status columns to the
tools inventory.

---

### Must 12 — Training Plan
**Status:** 🟡 Partial

getting-started/index.html provides onboarding resources and foundational
reading. The careers page documents the shadow-shift onboarding process.

**Gap:** No structured training curriculum with milestones, assessments,
or completion tracking exists.

**Recommendation:** Create a formal training curriculum with defined
milestones for analyst progression from L1 to L2.

---

## Pillar 4: Controls

### Must 13 — Incident Response Procedure
**Status:** ✅ Met

ticketing/index.html documents the full incident ticket workflow including
triage, evidence collection, enrichment, MITRE mapping, and escalation.
The red button on the home page provides a clear reporting path.

**Gap:** No formal Incident Response Plan (IRP) document exists beyond
the ticketing workflow.

**Recommendation:** Draft a formal IRP covering severity levels,
escalation paths, containment procedures, and post-incident review.

---

### Must 14 — Log Retention Policy
**Status:** 🔴 Not Met

No log retention policy is documented. It is unclear how long ELK
indices are retained, who has access, and when data is purged.

**Recommendation:** Define and document a log retention policy covering
retention period, access controls, and purge procedures.

---

### Must 15 — Access Control
**Status:** 🟡 Partial

GitHub repo access is controlled via collaborator permissions (documented
in LAUNCH.md). ELK access is controlled via the cyber range VPN.

**Gap:** No formal access control policy document exists. No documented
process for revoking access when analysts graduate or leave.

**Recommendation:** Document access control procedures including
provisioning, review, and revocation processes.

---

### Must 16 — Baseline Security Controls
**Status:** ✅ Met

The SOC uses industry-standard baseline controls:
- MITRE ATT&CK for threat detection mapping
- NIST Cybersecurity Framework for operational structure
- ELK SIEM for log monitoring and alerting
- Palo Alto NGFW for perimeter defense
- OTX/VirusTotal/AbuseIPDB for threat intelligence

**Gap:** No formal control selection report documenting which specific
NIST 800-171 or CIS v8 controls are implemented vs. not implemented.

**Recommendation:** Complete trusted-ci/control-selection.md mapping
current tools to specific framework controls.

---

## Prioritized Gap Remediation Roadmap

### High Priority (Address within 30 days)
| Gap | Must | Action |
|-----|------|--------|
| Mission not aligned to research mission | Must 1 | Update mission statement |
| No institutional reporting structure | Must 7 | Define reporting chain |
| No obligations log | Must 8 | Create obligations-log.md |
| No log retention policy | Must 14 | Draft retention policy |

### Medium Priority (Address within 90 days)
| Gap | Must | Action |
|-----|------|--------|
| No master program document | Must 6 | Create master-program.md |
| No formal IRP | Must 13 | Draft incident response plan |
| No access revocation process | Must 15 | Document access procedures |
| No control selection report | Must 16 | Create control-selection.md |

### Low Priority (Address within 6 months)
| Gap | Must | Action |
|-----|------|--------|
| No stakeholder map | Must 3 | Create stakeholder-map.md |
| No succession plan | Must 5 | Document succession procedures |
| No staffing plan | Must 9 | Define minimum staffing levels |
| No budget/sustainability plan | Must 10 | Draft sustainability document |
| No training curriculum | Must 12 | Build analyst progression milestones |

---

## Next Steps

1. Present this report to Prof. R. Joyce for review and approval
2. Share with MSU CISO or IT Security Director
3. Begin High Priority remediations immediately
4. Re-assess compliance score at end of semester

---

*Cybercave SOC — MSU*
*This report should be updated each semester as gaps are addressed.*
*Next review date: December 2026*
