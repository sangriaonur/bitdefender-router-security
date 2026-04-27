# Bitdefender Router Security Testing

End-to-end security validation for home networking hardware using **Bitdefender** threat detection, DHS policy enforcement, containerized staging environments, and weekly structured reporting.

---

## Overview

This project covers the full security testing lifecycle for Verizon home routers and gateways — from initial container staging and deployment through active threat detection, policy compliance, and weekly update reporting.

---

## Test Environment

```
CHR30A Router  ──→  Container Staging  ──→  Bitdefender Validation  ──→  DHS Policy Check
                         │
                    Docker-based
                    staging pipeline
```

---

## Testing Phases

### Phase 1 — Container Staging & Validation
- Deploy Bitdefender agent in containerized staging environment
- Validate container integrity before production push
- Test: `CHR30A_Bitdefender_Container_Staging_&_Validation`
- Artifacts: MP4 screen recording of full staging workflow

### Phase 2 — Security Scanning
- Active threat detection against known malicious endpoints
- DNS filtering validation (block malicious/phishing domains)
- Intrusion detection system (IDS) rule verification
- Vulnerability scan against router admin interface

### Phase 3 — DHS Policy Enforcement
- Device Host Security (DHS) compliance checks
- Network isolation policy validation
- Unauthorized device detection testing
- Weekly report generation: `DHS_Weekly_Report`

### Phase 4 — Verizon Digital Secure Home
- Security failure scenario testing
- Parental controls and content filtering validation
- VPN pass-through testing
- Documented in: `Verizon_Digital_Secure_Home_security_failures`

---

## Weekly Reporting

Structured HTML weekly reports generated per sprint:

| Week | Period | Report |
|------|--------|--------|
| Week 1 | Apr 21–25, 2026 | DHS_Weekly_Report_Apr21-25_2026.html |
| Week 1 | Apr 22, 2026 | VHA_Security_Validation (PPTX/PDF) |

Reports include:
- Tests executed
- Pass/fail breakdown
- Defects found (with screenshots)
- Next week testing plan

---

## Procedure Reference

Full testing procedure documented in:
`bitdefender_complete_procedure_v2.pdf`

Testing plan architecture from:
`Bitdefender Router Security Testing Plan - Google Gemini.html`

---

## Tools & Tech

| Tool | Purpose |
|------|---------|
| **Bitdefender Box / Agent** | Primary threat detection engine |
| **Docker** | Container staging environment |
| **Wireshark** | Packet inspection during attack scenarios |
| **NotebookLM** | AI-assisted weekly report summarization |
| **Google Gemini** | Test plan generation and analysis |
| **Python** | Automation scripts for test data parsing |

---

## Key Findings Format

```
Test ID    | Description                        | Result | Notes
───────────────────────────────────────────────────────────────────
BD-001     | Malicious domain DNS blocking       | PASS   | 100% block rate
BD-002     | Phishing URL detection              | PASS   | 2s detection time
BD-003     | Unauthorized device alert           | PASS   | Alert within 30s
BD-004     | Container integrity post-deploy     | PASS   | SHA256 verified
BD-005     | IDS rule trigger (port scan)        | FAIL   | Rule gap - logged
```
