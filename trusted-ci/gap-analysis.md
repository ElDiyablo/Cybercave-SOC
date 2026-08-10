# Cybercave SOC — Trusted CI Framework Gap Analysis Report

**Institution:** Murray State University
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
GitHub Pages site (about/index.html) and in trusted-ci/mission-statement.md.

> "The Cybercave Security Operations Center exists to defend Murray State
> University's digital infrastructure, advance the university's academic
> mission through applied cybersecurity practice, and develop the next
> generation of security professionals from within the Murray State
> student body."

**Gap:** Mission statement should be formally approved by Department Chair
and reviewed each semester.

**Recommendation:** Submit mission-statement.md to Prof. R. Joyce for
formal sign-off and schedule semester reviews.

---

### Must 2 — Defined Scope
**Status:** ✅ Met

The SOC scope is documented — monitoring campus network traffic via Palo Alto
NGFW logs ingested into ELK SIEM. Scope boundaries are defined in
SECURITY.md, LAUNCH.md, and trusted-ci/mission-statement.md.

**Gap:** Scope does not explicitly address which university network segments
are covered vs. excluded.

**Recommendation:** Work with Murray State IT to formally document which
network segments fall within SOC monitoring scope.

---

### Must 3 — Stakeholder Identification
**Status:** 🟡 Partial

Key stakeholders identified:
- Faculty Advisor: Prof. R. Joyce
- SOC Lead: ElDiyablo
- SOC Analysts: Murray State CYS students

**Gap:** No formal mapping to institutional stakeholders (CISO, IT Directors,
Department Chair). Customers of the SOC (students, faculty, IT staff) are
not formally documented.

**Recommendation:** Complete a stakeholder map — see
trusted-ci/obligations-log.md for the initial draft.

---

### Must 4 — Alignment with Institutional Mission
**Status:** 🟡 Partial

The SOC mission statement includes alignment language connecting SOC
operations to Murray State's academic and student success goals.

**Gap:** No formal acknowledgment from university leadership that the SOC
mission aligns with institutional strategic goals.

**Recommendation:** Present mission-statement.md to Department Chair or
CISO for formal institutional acknowledgment.

---

## Pillar 2: Governance

### Must 5 — Defined Cybersecurity Lead
**Status:** ✅ Met

SOC Lead (ElDiyablo) is identified in all documentation as the primary
technical lead. Faculty Advisor (Prof. R. Joyce) serves as program owner.

**Gap:** No formal succession plan if SOC Lead graduates or leaves the
program. Given the student nature of the program, turnover is expected.

**Recommendation:** Document succession procedures and cross-train at
least one backup SOC Lead each semester.

---

### Must 6 — Master Program Document
**Status:** 🟡 Partial

LAUNCH.md and user-guide.md partially fulfill this requirement. The site
and its documentation serve as the program's operational reference.

**Gap:** No single consolidated Master Program Document exists that covers
all governance elements — mission, scope, roles, reporting structure,
and policy references — in one place.

**Recommendation:** Create trusted-ci/master-program.md consolidating
all governance elements into one authoritative document.

---

### Must 7 — Reporting Structure
**Status:** 🔴 Not Met

No formal reporting structure to Murray State leadership is documented.
The SOC currently reports informally to the faculty advisor with no
defined cadence or format.

**Recommendation:** Define and document a formal reporting chain:
SOC Lead → Faculty Advisor → Department Chair → CISO (or equivalent).
Include reporting cadence (weekly shift reports, monthly summaries,
semester reviews).

---

### Must 8 — Institutional Obligations Log
**Status:** 🔴 Not Met

No formal log of legal, regulatory, or contractual obligations has been
created. The SOC handles network telemetry and operates within a university
environment subject to FERPA and Murray State data governance policies.

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
requirements, or backup coverage procedures for analyst shifts.

**Recommendation:** Document minimum viable staffing levels and a
shift coverage plan to ensure continuity of monitoring operations.

---

### Must 10 — Budget & Sustainability
**Status:** 🔴 Not Met

No budget documentation exists. The SOC currently operates on zero direct
budget — tools are free/open-source, hosting is free (GitHub Pages),
and staffing is volunteer student labor through CYS coursework.

**Gap:** Sustainability is at risk if faculty advisor support changes,
course structure changes, or key student contributors graduate.

**Recommendation:** Document current resource dependencies and draft
a sustainability plan identifying what institutional support is needed
to maintain operations long-term.

---

### Must 11 — Tool Inventory
**Status:** ✅ Met

tools/index.html provides a comprehensive inventory of all SOC tools
organized by category: SIEM (ELK), threat intelligence (OTX, VirusTotal,
AbuseIPDB, Shodan), detection frameworks (MITRE ATT&CK, Sigma, CAR),
network analysis (Wireshark, CyberChef), and training platforms.

**Gap:** No formal tool ownership, licensing status, or renewal tracking.

**Recommendation:** Add ownership and license status to the tools inventory
to support long-term sustainability planning.

---

### Must 12 — Training Plan
**Status:** 🟡 Partial

getting-started/index.html provides onboarding resources and a curated
foundational reading list (MITRE, FIRST, NCSC, Gartner, Splunk).
The careers page documents the shadow-shift onboarding process.

**Gap:** No structured training curriculum with defined milestones,
assessments, or analyst progression tracking (L1 → L2 → Lead).

**Recommendation:** Create a formal training curriculum with defined
milestones and a simple tracking mechanism for analyst progression.

---

## Pillar 4: Controls

### Must 13 — Incident Response Procedure
**Status:** ✅ Met

ticketing/index.html documents the full incident ticket workflow including
triage, evidence collection, enrichment, MITRE ATT&CK mapping, and
recommended actions. The red incident button on the home page provides
a clear community reporting path.

**Gap:** No formal standalone Incident Response Plan (IRP) document exists
beyond the ticketing workflow page.

**Recommendation:** Draft a formal IRP covering severity classification,
escalation paths, containment procedures, and post-incident review process.

---

### Must 14 — Log Retention Policy
**Status:** 🔴 Not Met

No log retention policy is documented. It is unclear how long ELK indices
are retained, who has access to historical data, and when data is purged.

**Recommendation:** Work with Murray State IT to define and document a
log retention policy covering retention period, access controls, and
purge procedures compliant with university data governance requirements.

---

### Must 15 — Access Control
**Status:** 🟡 Partial

GitHub repo access is controlled via collaborator permissions documented
in LAUNCH.md. ELK access is controlled via the cyber range VPN and
analyst credentials managed by the faculty advisor.

**Gap:** No formal access control policy document. No documented process
for revoking access when analysts graduate or leave the program.

**Recommendation:** Document access control procedures including
provisioning, periodic review, and revocation processes for both
GitHub and ELK/cyber range access.

---

### Must 16 — Baseline Security Controls
**Status:** ✅ Met

The SOC uses industry-standard baseline controls:
- MITRE ATT&CK for threat detection technique mapping
- NIST Cybersecurity Framework for operational structure
- ELK SIEM for log monitoring and alerting
- Palo Alto NGFW for perimeter defense and telemetry
- OTX/VirusTotal/AbuseIPDB for threat intelligence enrichment

**Gap:** No formal control selection report documenting which specific
NIST 800-171 or CIS v8 controls are implemented vs. not implemented.

**Recommendation:** Complete trusted-ci/control-selection.md mapping
current tools to specific framework controls.

---

## Prioritized Gap Remediation Roadmap

### High Priority — Address within 30 days

| Gap | Must | Owner | Action |
|-----|------|-------|--------|
| No formal reporting structure | Must 7 | SOC Lead + Faculty Advisor | Define reporting chain and cadence |
| No obligations log | Must 8 | SOC Lead | Create obligations-log.md |
| No log retention policy | Must 14 | SOC Lead + Murray State IT | Draft retention policy |
| Mission not formally approved | Must 4 | Faculty Advisor | Present to Department Chair |

### Medium Priority — Address within 90 days

| Gap | Must | Owner | Action |
|-----|------|-------|--------|
| No master program document | Must 6 | SOC Lead | Create master-program.md |
| No formal IRP | Must 13 | SOC Lead | Draft incident response plan |
| No access revocation process | Must 15 | SOC Lead | Document access procedures |
| No control selection report | Must 16 | SOC Lead | Create control-selection.md |

### Low Priority — Address within 6 months

| Gap | Must | Owner | Action |
|-----|------|-------|--------|
| No stakeholder map | Must 3 | SOC Lead | Document institutional stakeholders |
| No succession plan | Must 5 | Faculty Advisor | Document succession procedures |
| No staffing plan | Must 9 | SOC Lead | Define minimum staffing levels |
| No budget/sustainability plan | Must 10 | Faculty Advisor | Draft sustainability document |
| No training curriculum | Must 12 | SOC Lead | Build analyst progression milestones |

---

## Compliance Score Summary

| Must | Description | Status |
|------|-------------|--------|
| Must 1 | Written mission statement | ✅ Met |
| Must 2 | Defined scope | ✅ Met |
| Must 3 | Stakeholder identification | 🟡 Partial |
| Must 4 | Institutional alignment | 🟡 Partial |
| Must 5 | Defined cybersecurity lead | ✅ Met |
| Must 6 | Master program document | 🟡 Partial |
| Must 7 | Reporting structure | 🔴 Not Met |
| Must 8 | Obligations log | 🔴 Not Met |
| Must 9 | Staffing plan | 🟡 Partial |
| Must 10 | Budget & sustainability | 🔴 Not Met |
| Must 11 | Tool inventory | ✅ Met |
| Must 12 | Training plan | 🟡 Partial |
| Must 13 | Incident response procedure | ✅ Met |
| Must 14 | Log retention policy | 🔴 Not Met |
| Must 15 | Access control | 🟡 Partial |
| Must 16 | Baseline security controls | ✅ Met |

**Final Score: 6 Met / 5 Partial / 5 Not Met**

---

## Next Steps

1. Present this report to Prof. R. Joyce for review and approval
2. Share with Murray State IT Security or CISO
3. Begin High Priority remediations immediately
4. Re-assess compliance score at end of semester

---

*Cybercave SOC — Murray State University*
*This report should be updated each semester as gaps are addressed.*
*Next review date: December 2026*
