# DECISIONS — TechCelerate
# Prefix: TDEC-###
# Scope: TechCelerate-only decisions
# Home: techcelerate-mono/governance/DECISIONS_TECHCELERATE_v1.md
# Version: 1.0 | Created: 2026-03-06
# Rules: Append-only. Reversals require new entry. Status: ACTIVE / SUPERSEDED / DEFERRED / REJECTED

---

## TDEC-001 — Decision Log + TDEC Numbering Adopted

**Date:** 2026-03-06 | **Status:** ACTIVE | **Decided by:** Lou Settembrino

**Decision:** TechCelerate adopts formal decision logging with TDEC-### prefix. This file is the canonical decision log for all TechCelerate-only decisions. Cross-entity decisions go to XDEC (Master CP). Shared-services architecture decisions go to SDEC.

**Rationale:** TechCelerate decisions were scattered across CP chat history with no formal log. CAMEOS has a mature DEC sequence as the model. TechCelerate needs the same discipline before team expansion.

---

## TDEC-002 — File Naming Standard

**Date:** 2026-03-06 | **Status:** ACTIVE | **Decided by:** Lou Settembrino

**Decision:** All TechCelerate-generated operational docs use ALL_CAPS_UNDERSCORES with dates. Pattern: `TECHCELERATE_TOPIC_YYYY-MM-DD.md`. Versioned: `TECHCELERATE_TOPIC_vN_YYYY-MM-DD.md`. Existing Pattern A files (`TechCElerate_Topic_Brief.md`) rename on next update — not immediately.

**Aligns with:** XDEC-001 (canonical file naming standard)

---

## TDEC-003 — Content Ownership Map

**Date:** 2026-03-06 | **Status:** ACTIVE | **Decided by:** Lou Settembrino

**Decision:** Authoritative sources defined per content type:

| Content Type | Authority | Reference Only |
|---|---|---|
| ASRT compliance rules | CLAUDE.md + ASRT Accreditation Brief | Orchestrator output (snapshot) |
| Build contract / behavioral rules | CLAUDE.md | — |
| Brand standards | Brand Guidelines PDF → CLAUDE.md | Page builds |
| Pricing / tiers | Financial Model v2 | CP updates |
| Server access | .env file | CLAUDE.md (references only, never hardcodes) |
| Course content | techcelerate-mono/courses/ | Content Pipeline Brief (describes process) |
| Multi-vertical strategy | Solo Builder Playbook + Multi-Vertical Analysis | Market Capture Strategy |
| Tag taxonomy | TECHCELERATE_TAG_TAXONOMY.md (to create) | FluentCRM config |
| Shared services components | shared-services/shared/ | Vendor copies in tools/shared/ |

**Rationale:** Duplication across SI, Build State, CLAUDE.md, and Orchestrator output was causing staleness and conflicting sources.

---

## TDEC-004 — FluentCRM Tag Taxonomy

**Date:** 2026-03-06 | **Status:** DEFERRED | **Decided by:** Lou Settembrino

**Decision:** FluentCRM tag taxonomy must be created and locked before FluentCRM configuration in May 2026. Tag-based segmentation (no separate lists per vertical).

**Revisit trigger:** Before May 2026 build sprint.

---

## TDEC-005 — Shared Services Vendoring Pattern

**Date:** 2026-03-06 | **Status:** ACTIVE | **Decided by:** Lou Settembrino

**Decision:** TechCelerate consumes shared services via vendor copy to `tools/shared/`. Runtime-firewalled — no imports from shared-services repo directly. Customizations stay in `techcelerate-mono/tools/shared/`. Good changes promoted upstream periodically.

**Aligns with:** XDEC-003 (cross-entity vendoring pattern)

---

## TDEC-006 — Oracle Review Cadence

**Date:** 2026-03-06 | **Status:** ACTIVE | **Decided by:** Lou Settembrino

**Decision:** Build phase oracles in CLAUDE.md are reviewed and updated after each build phase completes. Oracles that drift from reality are worse than no oracles.

---

## TDEC-007 — AI Content Disclosure Language

**Date:** 2026-03-06 | **Status:** ACTIVE | **Decided by:** Lou Settembrino

**Decision:** Standard AI content disclosure: "Developed with AI-assisted research tools, reviewed and approved by [Name, Credentials]." Applied to all AI-assisted content unless ASRT provides different guidance on accreditation call.

**Note:** Do not flag content as "AI-generated" in ASRT submissions — use disclosure language above.

---

## TDEC-008 — Product Line Structure (Lines A/B/C)

**Date:** 2026-03-06 | **Status:** ACTIVE | **Decided by:** Lou Settembrino

**Decision:** TechCelerate operates three product lines under TechCelerate LLC:

| Line | Type | Accreditation |
|---|---|---|
| Line A | Accredited CE (RT/ASRT) | ASRT required |
| Line B | Compliance training (HIPAA, BBP, Infection Control, Workplace Violence, Cybersecurity, Sexual Harassment) | None — Category A autopilot |
| Line C | Premium / AI Literacy | None |

All launching July 4, 2026. DBA or separate brand evaluation deferred to $100K compliance revenue milestone (XDEC-005).
