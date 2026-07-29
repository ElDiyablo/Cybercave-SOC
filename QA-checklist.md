# Cybercave SOC — QA Testing Checklist

**Complete this checklist before every major release and on Launch Day.**
Check off each item as you verify it. If something fails, note it in the Issues column and open a GitHub Issue.

---

## 1. Link Testing

### Internal Links — verify each page loads correctly

| Page | URL | Status | Notes |
|------|-----|--------|-------|
| Home | `/index.html` | ⬜ | |
| About | `/about/index.html` | ⬜ | |
| Getting Started | `/getting-started/index.html` | ⬜ | |
| Tools | `/tools/index.html` | ⬜ | |
| Resources | `/resources/index.html` | ⬜ | |
| Ticketing | `/ticketing/index.html` | ⬜ | |
| Blog Index | `/blog/index.html` | ⬜ | |
| Blog Post 1 | `/blog/post-financial-aid-phishing.html` | ⬜ | |
| Blog Post 2 | `/blog/post-password-spray.html` | ⬜ | |
| Blog Post 3 | `/blog/post-soc-intro.html` | ⬜ | |
| Careers | `/careers/index.html` | ⬜ | |
| SECURITY.md | `/SECURITY.md` | ⬜ | |
| User Guide | `/user-guide.md` | ⬜ | |

### Navigation Bar — verify on every page

| Check | Status | Notes |
|-------|--------|-------|
| Home link works from all pages | ⬜ | |
| About link works from all pages | ⬜ | |
| Getting Started link works from all pages | ⬜ | |
| Tools link works from all pages | ⬜ | |
| Resources link works from all pages | ⬜ | |
| Ticketing link works from all pages | ⬜ | |
| Blog link works from all pages | ⬜ | |
| Join Us link works from all pages | ⬜ | |
| Active page is highlighted in nav | ⬜ | |

### Critical Links — verify these specifically

| Link | Location | Status | Notes |
|------|----------|--------|-------|
| 🚨 Report Incident Now button | Home page | ⬜ | Should link to university incident form |
| Open Ticket Form button | Ticketing page | ⬜ | Should link to Google Form |
| GitHub repo link | Footer (all pages) | ⬜ | |
| MITRE ATT&CK | Getting Started | ⬜ | |
| FIRST SOC guide PDF | Getting Started | ⬜ | |
| OTX Portal | Tools + Getting Started | ⬜ | |
| VirusTotal | Tools | ⬜ | |
| AbuseIPDB | Tools | ⬜ | |
| haveibeenpwned | Resources | ⬜ | |
| Blog post 1 → Back to Blog link | Blog Post 1 | ⬜ | |
| Blog post 2 → Back to Blog link | Blog Post 2 | ⬜ | |
| Blog post 3 → Back to Blog link | Blog Post 3 | ⬜ | |

---

## 2. Content Audit

### Placeholder Text — confirm none of these remain on the live site

| Item | Location | Status | Notes |
|------|----------|--------|-------|
| "Update Each Shift" removed or filled | Home threat widget | ⬜ | |
| "Your Name Here" replaced | About team cards | ⬜ | |
| `href="#"` replaced on incident button | Home page | ⬜ | Real URL added |
| `href="#"` replaced on ticket form | Ticketing page | ⬜ | Real Google Form URL |
| `<range-ip>` replaced in terminal | Getting Started | ⬜ | Real Kibana IP |

### Mission & Content Review

| Check | Status | Notes |
|-------|--------|-------|
| Mission statement is accurate and approved | ⬜ | |
| Team cards reflect current SOC members | ⬜ | |
| Program history dates are correct | ⬜ | |
| Service catalog matches actual SOC services | ⬜ | |
| Blog posts reviewed for accuracy | ⬜ | |
| No spelling or grammar errors on main pages | ⬜ | |
| All content is appropriate for university compliance | ⬜ | |

---

## 3. Browser Compatibility

Test the home page and at least two other pages in each browser:

| Browser | Home | About | Resources | Notes |
|---------|------|-------|-----------|-------|
| Chrome (latest) | ⬜ | ⬜ | ⬜ | |
| Firefox (latest) | ⬜ | ⬜ | ⬜ | |
| Edge (latest) | ⬜ | ⬜ | ⬜ | |
| Safari (Mac/iOS) | ⬜ | ⬜ | ⬜ | |
| Chrome Mobile (Android) | ⬜ | ⬜ | ⬜ | |
| Safari Mobile (iPhone) | ⬜ | ⬜ | ⬜ | |

### Mobile Responsiveness Checks

| Check | Status | Notes |
|-------|--------|-------|
| Nav bar displays correctly on mobile | ⬜ | |
| Hero section readable on small screens | ⬜ | |
| Cards stack vertically on mobile | ⬜ | |
| Tables scroll horizontally on mobile | ⬜ | |
| Threat widget readable on mobile | ⬜ | |
| Red banner readable on mobile | ⬜ | |
| Footer readable on mobile | ⬜ | |

---

## 4. Security Audit

| Check | Status | Notes |
|-------|--------|-------|
| No hardcoded passwords or API keys in any file | ⬜ | |
| No internal IP addresses exposed in HTML source | ⬜ | |
| No sensitive comments left in HTML (`<!-- password: -->` etc.) | ⬜ | |
| All external links use HTTPS (not HTTP) | ⬜ | |
| SECURITY.md is present and accurate | ⬜ | |
| No student PII visible anywhere on the site | ⬜ | |
| Incident form link is correct and working | ⬜ | |
| GitHub repo has branch protection enabled | ⬜ | |

---

## 5. Performance Checks

| Check | Status | Notes |
|-------|--------|-------|
| Home page loads in under 3 seconds | ⬜ | Test at fast-3g or use PageSpeed |
| Google Fonts load correctly | ⬜ | |
| No broken images or missing icons | ⬜ | |
| No console errors in browser dev tools | ⬜ | Press F12 → Console tab |
| Search bar returns results correctly | ⬜ | Try searching "phishing", "tools", "ticketing" |

**Run a free performance test:**
- PageSpeed Insights: `https://pagespeed.web.dev/`
- Enter: `https://eldiyablo.github.io/Cybercave-SOC/`

---

## 6. Launch Day Final Checks

Complete these on Week 12 launch day only:

| Check | Status | Notes |
|-------|--------|-------|
| All QA items above are checked off | ⬜ | |
| SOC manager has been given repo access | ⬜ | |
| User Guide has been shared with all staff | ⬜ | |
| LAUNCH.md handover document is complete | ⬜ | |
| Threat widget shows current real data | ⬜ | |
| Incident report button links to real form | ⬜ | |
| Google Form ticket link is active | ⬜ | |
| Site URL shared with faculty advisor | ⬜ | |
| Site URL shared with university IT contact | ⬜ | |
| First blog post drafted for launch day | ⬜ | |

---

## Issues Log

Document any failures found during QA here before opening GitHub Issues:

| # | Page | Issue Found | Severity | Fixed? |
|---|------|-------------|----------|--------|
| 1 | | | | ⬜ |
| 2 | | | | ⬜ |
| 3 | | | | ⬜ |
| 4 | | | | ⬜ |
| 5 | | | | ⬜ |

---

*Last updated: June 2026 — Cybercave SOC*
*Run this checklist before every major release. Keep a copy with the date completed for your records.*
