# Security Policy — Cybercave SOC

## Reporting a Vulnerability

If you discover a security vulnerability in this site or the Cybercave SOC infrastructure, please report it responsibly.

**Do NOT open a public GitHub issue for security vulnerabilities.**

### How to Report

1. Email the SOC lead directly (contact via GitHub profile)
2. Include a description of the vulnerability, steps to reproduce, and potential impact
3. Allow up to 72 hours for an initial response

We take all reports seriously and will acknowledge receipt, investigate promptly, and keep you informed of our findings.

---

## Scope

This security policy covers:
- This GitHub Pages documentation site
- Any scripts or tools published in this repository

This policy does **not** cover:
- University network infrastructure (report those to university IT)
- Third-party tools linked from this site

---

## Secrets & Sensitive Data

This repository must never contain:
- Passwords or API keys
- Internal IP addresses or hostnames
- Student or staff personal information
- Network architecture details beyond what is publicly documented

If you find any of the above in this repo, report it immediately via the process above.

---

## Site Security Checklist (For Maintainers)

Run before each major release:

- [ ] No hardcoded credentials in HTML, CSS, or JS files
- [ ] No internal IPs or hostnames exposed in source code
- [ ] All external links use HTTPS
- [ ] No sensitive comments left in HTML source
- [ ] GitHub Actions secrets used for any API keys (not hardcoded)
- [ ] Content Security Policy headers configured (if using custom server)
- [ ] All form endpoints validated and spam-protected

---

## Supported Versions

| Version | Supported |
|---------|-----------|
| Current main branch | ✅ Yes |
| Older commits | ❌ No — please update to latest |

---

*Last updated: June 2026 — Cybercave SOC*
