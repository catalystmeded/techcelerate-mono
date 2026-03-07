# CLAUDE.md — TechCelerate
# Inherits: ~/.claude/CLAUDE.md (global rules always loaded — do not duplicate here)
# Company: TechCelerate (SEPARATE from Catalyst Medical Education)
# Version: 3.0 | Updated: 2026-03-06

---

## CRITICAL BOUNDARY

TechCelerate is a **SEPARATE company** from Catalyst Medical Education.
- Never mix: CAMEOS pipeline logic, Catalyst brand, CME grant content into TechCelerate
- Never mix: ASRT content, RT course material into CAMEOS or Catalyst
- Cross-project decisions → Master CP only

---

## CURRENT STATUS

**ASRT submission deadline: April 25, 2026** — always display days remaining at session start
**Full launch: July 4, 2026**
**Platform build: Phase 0+1 not yet started this cycle**

---

## TECHCELERATE IDENTITY

- **What:** Multi-vertical continuing education platform
- **Primary accreditor:** ASRT (American Society of Radiologic Technologists)
- **Sponsor type:** General Sponsor (NOT Instructional Provider)
- **Stack:** WordPress + LearnDash + FluentCRM + SES
- **Server:** SSH root@45.59.100.119 | Webmin port 10000 | WP-CLI installed
- **WP version:** 6.9.1 | PHP 8.3.20 | LearnDash 5.0.1.1
- **Dennis handles:** nginx only — never touch nginx config

---

## PRODUCT LINE STRUCTURE (TDEC-008)

| Line | Type | Accreditation | Build Timing |
|---|---|---|---|
| **Line A** | Accredited CE (RT/ASRT) | ASRT required | Now — April 25 deadline |
| **Line B** | Compliance training (HIPAA, BBP, Infection Control, Workplace Violence, Cybersecurity, Sexual Harassment) | None required | May–June 2026 |
| **Line C** | Premium / AI Literacy | None required | May–June 2026 |

All three lines launch July 4, 2026.

---

## FOUNDING TIER PRICING

| Tier | Price | Notes |
|---|---|---|
| Red | $250 one-time | Founding supporter |
| White | $9.99/yr | Standard annual |
| Blue | $19.99/yr | Enhanced annual |
| 250th Extended | $25/yr | Special founding tier |
| RT Standard | $39.99/yr | Full standard access |

---

## ASRT COMPLIANCE ORACLE (GATE 2 — ALL LINE A CONTENT)

Every course must pass before publishing:

**Credit-to-Word-Count Table:**

| Credits | Min Words | Min Questions |
|---|---|---|
| 0.25 | 1,600 | 2 |
| 0.50 | 2,450 | 4 |
| 0.75 | 3,700 | 6 |
| 1.00 | 4,900 | 8 |
| 1.25 | 6,125 | 10 |
| 1.50 | 7,375 | 12 |
| 2.00 | 9,850 | 16 |
| 3.00 | 14,750 | 24 |
| 4.00 | 19,700 | 32 |

**Additional ASRT Rules:**
- ≥60% questions must be multiple choice
- No "all of the above", "none of the above", "both A and B"
- Each MC question: exactly 4 options
- True/false ≤10% of total questions
- All learning objectives use measurable Bloom's taxonomy verbs
- AMA 11th Edition references (delegates to AMA11Validator)
- References older than 5 years flagged as WARNING
- 75% passing score
- All 11 certificate elements mandatory (see Certificate section)
- Approval statement exact text: "Activity approved by ASRT."
- AI content: SME-reviewed before submission. Do not flag as "AI-generated" in submissions.

---

## CERTIFICATE — 11 MANDATORY ELEMENTS

1. Sponsor name (Catalyst Medical Education / TechCelerate)
2. Participant name
3. Activity title
4. Reference number
5. Credits awarded
6. Credit category (A)
7. Approval statement: "Activity approved by ASRT."
8. Date completed
9. Authorized signature
10. ASRT ID
11. Expiration date

---

## PRIORITY COURSES FOR ASRT SUBMISSION

| Course ID | Title | Writer | Status |
|---|---|---|---|
| RT_24003 | Chest Radiography | Heidi Veillette | FINAL |
| RT_23001 | MS MRI Imaging | Heidi Veillette | FINAL |
| RT_23009 | Radiation Physics | Kelli Haynes | FINAL |
| RT_23016 | Radiography Imaging | Heidi Veillette | FINAL |

First action each sprint: Re-contact Heidi Veillette — highest value writer.

---

## CONTENT PIPELINE (8-STAGE)

| Stage | Action | Automated? |
|---|---|---|
| 1 | Outline generation | Claude — ralph-loop |
| 2 | Section drafting | Claude — ralph-loop |
| 3 | ASRT compliance check | Automated oracle (ComplianceEngine) |
| 4 | Post-test generation | Claude — ralph-loop |
| 5 | SME review | **Human — cannot be automated** |
| 6 | Revision pass | Claude, based on SME feedback |
| 7 | Final ASRT format validation | Automated (ComplianceEngine) |
| 8 | LearnDash upload + config | Semi-automated via WPClient |

---

## SHARED TOOLS (VENDOR COPY)

Location: `tools/shared/` — vendored from shared-services. Runtime-firewalled.

```python
from tools.shared.compliance_engine import ComplianceEngine
from tools.shared.reference_validator import AMA11Validator
from tools.shared.batch_processor import BatchProcessor
from tools.shared.wp_client import WPClient
from tools.shared.certificate_generator import CertificateGenerator
from tools.shared.course_templater import CourseTemplater
```

**Never import from shared-services repo directly.**
Customizations to these tools stay in this repo's copy.

---

## PLATFORM STACK

| Tool | Purpose | Status |
|---|---|---|
| LearnDash | Course delivery + progress tracking | ✅ Installed v5.0.1.1 |
| FluentCRM | Email + learner management (replaces MailChimp) | ✅ Owned (lifetime license) |
| SES | Email delivery for FluentCRM | ⬜ Account needed |
| Stripe | Payments | ⬜ Account needed |
| RankMath | SEO | ⬜ Post-launch |
| Wordfence | Security | ⬜ Post-launch |
| Stripe Tax | Multi-state sales tax ($0.245/txn) | ⬜ Configure with Stripe |

**Never install new plugins without Lou approval.**

---

## ACTIVE BLOCKERS

1. ASRT call not yet made — AI content policy response pending (April 25 deadline at risk)
2. E&O insurance not started — must have before launch
3. Stripe account not created — blocks payment setup
4. AWS + SES account not created — 24hr sandbox clock not started
5. Heidi Veillette not re-contacted — blocks content audit
6. MailChimp cancellation pending — cancel after FluentCRM + SES configured ($4,440/yr savings)

---

## BATTING ORDER (TO ASRT SUBMISSION)

1. UpdraftPlus → Google Drive backup (before any build)
2. Stripe account + AWS/SES account
3. Phase 0+1 — backup + plugin swap (Claude Code unattended)
4. Email Heidi Veillette — SME re-contact
5. Phase 2 — LearnDash configuration
6. Course freshness audit (4 FINAL courses)
7. Post-test question generation
8. Certificate template (11 ASRT elements)
9. ASRT submission packets — 4 courses
10. Submit by April 25

---

## GOVERNANCE REFERENCE

| Document | Location |
|---|---|
| Decision Log (TDEC-###) | `governance/DECISIONS_TECHCELERATE_v1.md` |
| Build contract (this file) | `techcelerate-mono/CLAUDE.md` |
| Orchestrator Output | `governance/TECHCELERATE_ORCHESTRATOR_OUTPUT_20260226.md` |

**Key decisions:** TDEC-001 (decision log + numbering), TDEC-002 (file naming), TDEC-005 (vendoring pattern), TDEC-008 (product line structure A/B/C)
