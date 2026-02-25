# CLAUDE.md — TechCelerate Sub-Project
# Inherits: root CLAUDE.md (always read root first)
# Company: TechCelerate (SEPARATE from Catalyst Medical Education)
# Version: 1.0 | Updated: 2026-02-25

---

## TECHCELERATE IDENTITY

TechCelerate = RT (Radiologic Technologist) continuing education platform
Accreditor: ASRT (American Society of Radiologic Technologists)
Sponsor type: General Sponsor (NOT Instructional Provider)
Stack: WordPress + LearnDash + FluentCRM + SES
Target launch: July 4, 2026
Server: Separate WP install from Catalyst main site

---

## CRITICAL BOUNDARY

TechCelerate is a SEPARATE company from Catalyst Medical Education.
Never mix: CAMEOS pipeline logic, Catalyst brand, CME grant content into TechCelerate.
Never mix: ASRT content, RT course material into CAMEOS or Catalyst.

---

## ASRT COMPLIANCE ORACLE (GATE 2 FOR ALL CONTENT)

Every course must pass before publishing:

| Rule | Requirement |
|------|------------|
| Credit calculation | 1 credit per 50-minute contact hour |
| Post-test questions | Minimum 10 per credit hour |
| Question format | Single best answer only (no SATA) |
| Pass threshold | 75% minimum |
| Content review | Licensed RT or SME sign-off required |
| Reference dates | All clinical references ≤ 5 years |
| Disclosure | All author COI disclosed |

**AI content policy**: All AI-generated content must be SME-reviewed before submission to ASRT.
This is non-negotiable. Do not flag content as "AI-generated" in submissions.

---

## CONTENT PIPELINE (8-STAGE)

```
Stage 1: Outline generation (Claude)
Stage 2: Section drafting (Claude)  
Stage 3: ASRT compliance check (automated oracle)
Stage 4: Post-test generation (Claude)
Stage 5: SME review (human — cannot be automated)
Stage 6: Revision pass (Claude, based on SME feedback)
Stage 7: Final ASRT format validation (automated)
Stage 8: LearnDash upload + configuration
```

Stages 1, 2, 4, 6 can run in ralph-loop.
Stage 5 always human. Stage 8 semi-automated via WP API.

---

## PLATFORM STACK RULES

- LearnDash: course delivery and progress tracking
- FluentCRM: email sequences and learner management (replaces MailChimp — $4,440/yr savings)
- SES: email delivery for FluentCRM
- RankMath: SEO (install post-launch)
- Wordfence: security (install post-launch)
- AffiliateWP: affiliate program (Phase 2)
- Stripe Tax: multi-state sales tax ($0.245/txn)

**Never install new plugins without Lou approval.** Plugin bloat = WP instability.

---

## PRIORITY COURSES FOR LAUNCH

| Course ID | Title | Writer | Status |
|-----------|-------|--------|--------|
| RT_24003 | Chest Radiography | Heidi Veillette | FINAL |
| RT_23001 | MS MRI Imaging | Heidi Veillette | FINAL |
| RT_23009 | Radiation Physics | Kelli Haynes | FINAL |
| RT_23016 | Radiography Imaging | Heidi Veillette | FINAL |

First action each sprint: Re-contact Heidi Veillette — highest value writer.

---

## ACTIVE BLOCKERS (as of 2026-02-24)

1. SSH/cPanel access — waiting on Dennis/Doug reply
2. ASRT call not made — call this week, April 25 deadline at risk
3. E&O insurance not started — get quotes before launch

Never build LearnDash course structure until SSH access confirmed.
