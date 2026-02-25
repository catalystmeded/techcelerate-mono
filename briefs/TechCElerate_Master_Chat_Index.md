# TechCElerate: Master Chat Index
## Prepared: 2026-02-22
## Purpose: Central directory mapping all workstream chats, briefs, and dependencies

---

## NAMING CONVENTION

TechCElerate is a multi-vertical platform targeting allied health professionals (radiologic technologists, medical assistants, pharmacy techs, dental hygienists, respiratory therapists, and more). Radiologic Technologists (RT) are the **launch vertical**.

**File naming:**
- `TechCElerate_RT_*` — RT-specific briefs (audience, competitors, accreditation, content). When expanding to a new vertical, duplicate and create `TechCElerate_[VERTICAL]_*` versions.
- `TechCElerate_*` (no vertical prefix) — Platform-wide briefs (infrastructure, legal, entity). These serve ALL verticals.

---

## CHAT ARCHITECTURE

```
┌─────────────────────────────────────────────────────┐
│          COMMAND POST (This Project Chat)            │
│  TechCElerate_Master_Knowledge_Base.md               │
│  All decisions logged back here                      │
└──────────────┬──────────────────────────────────────┘
               │
  PLATFORM-WIDE│(serve all verticals)
    ┌──────────┼──────────┐
    ▼          ▼          ▼
┌────────┐┌────────┐┌──────────┐
│PLATFORM││ LEGAL  ││  MASTER  │
│& BUILD ││ TAX &  ││  CHAT    │
│(all)   ││INSURANCE││  INDEX   │
└───┬────┘└────────┘└──────────┘
    │
  RT LAUNCH VERTICAL (duplicate per future vertical)
    ┌──────────┼──────────────────────────────────┐
    │          │          │          │             │
    ▼          ▼          ▼          ▼             ▼
┌────────┐┌────────┐┌────────┐┌────────┐   ┌──────────┐
│RT      ││RT      ││RT      ││RT      │   │RT        │
│PRICING ││CONTENT ││MARKETING││ASRT   │   │B2B /     │
│& UNIT  ││PIPELINE││& GROWTH ││ACCRED. │   │ENTERPRISE│
│ECONOMICS││       ││        ││        │   │          │
└────────┘└────────┘└────────┘└────────┘   └──────────┘
```

**When adding a new vertical (e.g., Medical Assistants):**
- Duplicate RT briefs → `TechCElerate_MA_Pricing_Brief.md`, `TechCElerate_MA_Content_Pipeline_Brief.md`, etc.
- Swap in: MA competitor data, AAMA/AMT accreditation rules, MA audience profile, MA-specific SMEs
- Platform-wide briefs (Platform Build, Legal) remain unchanged — the infrastructure serves all verticals

---

## WORKSTREAM CHATS

### 1. RT: Pricing & Unit Economics ⭐ START HERE
| Field | Detail |
|-------|--------|
| Brief | `TechCElerate_RT_Pricing_Unit_Economics_Brief.md` |
| Scope | **RT-specific** (competitor data, break-even). Contains vertical-agnostic pricing framework section. |
| Priority | **CRITICAL — blocks all other workstreams** |
| Dependencies | None (this is the starting point) |
| Feeds into | Platform Build (checkout config), Marketing (messaging), B2B (enterprise tiers), Content Pipeline (course value optimization) |
| Key output | Locked pricing decision with financial model |
| Status | Ready to start |

### 2. Platform & Website Build (All Verticals)
| Field | Detail |
|-------|--------|
| Brief | `TechCElerate_Platform_Website_Build_Brief.md` |
| Scope | **Platform-wide** — infrastructure serves all verticals |
| Priority | HIGH — parallel with pricing once hosting decision is made |
| Dependencies | Hosting eval response (email sent), Pricing decision (for checkout config) |
| Feeds into | Content Pipeline (LMS ready to receive courses), Marketing (site live for traffic), ASRT (test link for reviewer) |
| Key output | Working TechCElerate website with LearnDash LMS |
| Status | Blocked on hosting eval response |

### 3. RT: Content Pipeline & Automation
| Field | Detail |
|-------|--------|
| Brief | `TechCElerate_RT_Content_Pipeline_Brief.md` |
| Scope | **RT-specific** (course inventory, ASRT rules, RT writers). Pipeline architecture is reusable across verticals. |
| Priority | HIGH — can start course audit immediately |
| Dependencies | Platform Build (for final LMS packaging), ASRT Accreditation (for submission requirements) |
| Feeds into | ASRT (courses ready for submission), Marketing (course library for promotion), B2B (course catalog for enterprise) |
| Key output | 20 audited courses + AI content generation pipeline |
| Status | Course audit can start now; LMS deployment waits for Platform Build |

### 4. RT: Marketing & Growth Automation
| Field | Detail |
|-------|--------|
| Brief | `TechCElerate_RT_Marketing_Growth_Brief.md` |
| Scope | **RT-specific** (audience profile, channels, competitors). Automation infrastructure is reusable across verticals. |
| Priority | MEDIUM — starts after Platform Build and Pricing are locked |
| Dependencies | Pricing decision (messaging), Platform Build (site live), Content Pipeline (courses to promote) |
| Feeds into | B2B (lead generation), all workstreams (subscriber growth) |
| Key output | Automated marketing engine (email, social, SEO, ads, affiliates) |
| Status | Strategy can be planned now; execution waits for platform + pricing |

### 5. RT: ASRT Accreditation & Compliance
| Field | Detail |
|-------|--------|
| Brief | `TechCElerate_RT_ASRT_Accreditation_Brief.md` |
| Scope | **RT-specific** — ASRT is the RT accrediting body. Future verticals will have separate accreditation briefs (AAMA/AMT, PTCB, state boards, etc.). |
| Priority | **CRITICAL — longest lead time (up to 9 weeks)** |
| Dependencies | Content Pipeline (courses ready for submission), Platform Build (test link for ASRT reviewer) |
| Feeds into | Content Pipeline (approval requirements), Platform Build (certificate template), Marketing (ASRT approved messaging) |
| Key output | ASRT Institutional Provider status + first courses approved |
| Status | Re-contact ASRT can happen NOW. Application prep can start NOW. |

### 6. Legal, Tax & Insurance (All Verticals)
| Field | Detail |
|-------|--------|
| Brief | `TechCElerate_Legal_Tax_Insurance_Brief.md` |
| Scope | **Platform-wide** — entity, tax, insurance cover all verticals. Writer contract templates adaptable per vertical. |
| Priority | HIGH — E&O insurance and entity verification needed before launch |
| Dependencies | Pricing decision (affects sales tax calculation) |
| Feeds into | Platform Build (T&C pages, privacy policy), Content Pipeline (updated writer contracts), all workstreams (entity structure) |
| Key output | Entity verified, insured, tax-compliant, legal docs in place |
| Status | Entity verification and insurance quotes can start NOW |

### 7. RT: B2B / Enterprise Channel
| Field | Detail |
|-------|--------|
| Brief | `TechCElerate_RT_B2B_Enterprise_Brief.md` |
| Scope | **RT-specific** (hospital radiology depts, imaging centers). Group enrollment infrastructure is platform-wide and reusable for pharmacy chains, dental offices, nursing depts, etc. |
| Priority | LOW (Phase 2) — after DTC launch is stable |
| Dependencies | Pricing decision, Platform Build, Content Pipeline (sufficient course library) |
| Feeds into | Revenue diversification, Marketing (B2B outreach) |
| Key output | Enterprise pricing, group enrollment system, B2B outreach |
| Status | Strategy planned; execution deferred to post-launch |

---

## EXECUTION PRIORITY

### Can Start Immediately (No Dependencies)
1. **Pricing & Unit Economics** — open chat, drop brief, start analysis
2. **ASRT re-contact** — call or email to confirm current pricing/process
3. **Entity verification** — confirm Catalyst MedEd structure, EIN, registrations
4. **E&O insurance quotes** — start shopping immediately
5. **Course audit** — begin freshness review of 4 FINAL courses

### Start After Hosting Response
6. **Platform Build** — hosting decision → WordPress install → theme → LMS config

### Start After Pricing Decision
7. **Marketing strategy** — messaging, positioning, funnel design
8. **B2B pricing tiers** — derived from individual pricing

### Start After Platform + Content Ready
9. **ASRT submission** — first batch of 4-6 courses
10. **Marketing execution** — email sequences, social media, SEO
11. **Soft launch** — beta testers

---

## DOCUMENT INVENTORY

### Briefs (Created Today)

**RT Launch Vertical (duplicate per future vertical):**
| Document | Workstream |
|----------|-----------|
| `TechCElerate_RT_Pricing_Unit_Economics_Brief.md` | RT Pricing |
| `TechCElerate_RT_Content_Pipeline_Brief.md` | RT Content Pipeline |
| `TechCElerate_RT_ASRT_Accreditation_Brief.md` | RT Accreditation |
| `TechCElerate_RT_Marketing_Growth_Brief.md` | RT Marketing |
| `TechCElerate_RT_B2B_Enterprise_Brief.md` | RT B2B/Enterprise |

**Platform-Wide (serve all verticals):**
| Document | Workstream |
|----------|-----------|
| `TechCElerate_Platform_Website_Build_Brief.md` | Platform Build |
| `TechCElerate_Legal_Tax_Insurance_Brief.md` | Legal/Tax/Insurance |

### Canonical References
| Document | Purpose |
|----------|---------|
| `TechCElerate_Master_Knowledge_Base.md` | Single source of truth for all project data |
| `Techcelerate_Brand_Guidelines_R1.pdf` | Brand colors, fonts, imagery, tone |

### Decision Log
*Update this section as decisions are made in each workstream chat:*

| Decision | Date | Workstream | Details |
|----------|------|-----------|---------|
| — | — | — | (No decisions locked yet) |
