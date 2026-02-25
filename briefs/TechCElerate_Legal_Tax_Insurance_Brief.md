# TechCElerate: Legal, Tax & Insurance Brief — All Verticals
## Prepared: 2026-02-22
## Purpose: Drop this into the dedicated Legal, Tax & Insurance chat as context
## Scope: PLATFORM-WIDE — Entity structure, tax compliance, and insurance cover all verticals
## Note: Entity structure, sales tax, E&O insurance, Terms of Service, and privacy policies apply across all TechCElerate verticals. Writer/SME contracts will need vertical-specific versions as new audiences are added (different credentials, different accrediting bodies). The contract TEMPLATE created here should be designed for easy vertical adaptation.

---

## WHAT THIS CHAT NEEDS TO PRODUCE

1. **Entity structure clarity** — Catalyst MedEd vs. TechCElerate relationship, liability isolation
2. **Multi-state sales tax compliance** — automated solution for digital education subscriptions
3. **E&O / professional liability insurance** — coverage for AI-generated clinical education content
4. **Terms of Service and Privacy Policy** — Iubenda configuration or custom drafting
5. **Writer/SME contract updates** — update 2023 contracts for AI-assisted pipeline, IP assignment
6. **DMCA/IP protection** — content theft prevention for course materials
7. **Accessibility compliance** — ADA/Section 508 for online education platform

---

## CURRENT ENTITY STRUCTURE

### What Exists
- **Catalyst Medical Education** — operating/parent entity
  - PNC bank account (established June 2023, verification letters on file)
  - Email: subscription@catalystmeded.com (used for all plugin purchases)
  - All writer contracts are "Catalyst Medical Education Consulting Agreements"
  - All W-9s on file reference Catalyst
- **TechCElerate** — brand/product name
  - Domain: techcelerate-ce.com (owned via Name.com)
  - Hosting: Learning Templates (IP: 194.233.102.135)
  - No evidence of separate TechCElerate entity registration

### Open Questions
1. Is Catalyst MedEd an LLC, Corp, sole proprietorship, or DBA?
2. Is TechCElerate a DBA under Catalyst, or does it need separate registration?
3. What state is the entity registered in?
4. Do we need a separate entity for liability isolation (especially for AI-generated clinical content)?
5. Is the EIN on file and current?

---

## MULTI-STATE SALES TAX

### The Problem
TechCElerate sells digital education subscriptions to customers in all 50 states. Digital goods and services have varying sales tax treatment by state.

### Key Variables
| Factor | Impact |
|--------|--------|
| Product type | Online continuing education (digital service) |
| Customer location | All 50 states + potentially international |
| Nexus | Economic nexus likely triggered in states with low thresholds once revenue grows |
| Tax treatment | Varies by state — some exempt education, some tax digital goods |

### States That Exempt Education/Digital Goods (Partial List — NEEDS RESEARCH)
Many states exempt educational services or online courses from sales tax, but exemptions vary:
- Some exempt all educational services
- Some exempt only accredited/approved educational programs
- Some tax all digital goods regardless of educational nature
- Some have specific exemptions for continuing professional education

### Automated Solutions
| Solution | How It Works | Cost |
|----------|-------------|------|
| **Stripe Tax** | Built into Stripe. Auto-calculates, collects, and reports tax. | 0.5% per transaction |
| **TaxJar** | Plugin for WooCommerce/WordPress. Tax calculation, filing, and remittance. | $19-$99/mo + filing fees |
| **Avalara** | Enterprise-grade. Auto-calculation, exemption management, filing. | $50-$300/mo |
| **Manual** | Research each state, register individually, file quarterly/annually. | Time-intensive, error-prone |

**Recommendation**: Stripe Tax if using Stripe for payments. Zero configuration, handles everything. At 0.5% per transaction on a $49 subscription = $0.245 per transaction.

### Action Items
1. Determine entity's current sales tax registrations (if any)
2. Research digital education tax exemptions by state
3. Implement automated tax collection at launch (Stripe Tax recommended)
4. Register for sales tax in states where required (may not be all states if education exemption applies)

---

## E&O / PROFESSIONAL LIABILITY INSURANCE

### Why This Is Critical
TechCElerate provides clinical education content that informs how radiologic technologists practice. If content contains errors that lead to:
- Incorrect clinical practice
- Patient harm traced to a CE course
- Regulatory non-compliance due to outdated content
- Loss of licensure due to invalid CE credits

...the company faces potential liability.

### Additional Risk Factor: AI-Generated Content
AI-assisted content creation introduces a novel risk:
- AI may generate clinically inaccurate information
- AI may hallucinate references or statistics
- SME review mitigates but doesn't eliminate risk
- Insurance carriers may have specific AI content exclusions

### Coverage Types Needed
| Coverage | What It Covers | Estimated Cost |
|----------|---------------|----------------|
| **Errors & Omissions (E&O)** | Claims arising from professional services (education content accuracy) | $1,000-$3,000/yr |
| **General Liability** | Bodily injury, property damage, advertising injury | $500-$1,500/yr |
| **Cyber Liability** | Data breach, PII exposure, system compromise | $1,000-$2,500/yr |
| **Media Liability** | Copyright infringement, defamation in content | Often bundled with E&O |

### Insurance Considerations for AI Content
1. **Disclose AI involvement** to insurance carrier during application
2. **Document HITL (human-in-the-loop) review process** — insurers want to see human oversight
3. **Maintain audit trail** — who reviewed, when, approval records
4. **Content version control** — track all changes, maintain history
5. **Check for AI exclusions** — some policies may exclude AI-generated content

### Action Items
1. Get E&O insurance quotes (start with Hartford, Hiscox, or specialized healthcare education carriers)
2. Disclose AI-assisted content creation process in applications
3. Document SME review workflow for underwriter review
4. Consider umbrella policy as course library and subscriber base grow

---

## TERMS OF SERVICE

### Key Provisions Needed
| Provision | Why |
|-----------|-----|
| **CE credit disclaimer** | TechCElerate provides ASRT-approved CE. User responsible for verifying state-specific requirements. |
| **Content accuracy disclaimer** | Education content is for CE purposes. Not medical advice. Not a substitute for clinical judgment. |
| **AI content disclosure** | Content developed with AI-assisted tools, reviewed by licensed professionals. Transparent but not alarming. |
| **Subscription terms** | Auto-renewal, cancellation policy, refund policy |
| **Intellectual property** | All course content is owned by Catalyst MedEd. No reproduction, distribution, or sharing. |
| **Account sharing prohibition** | One account per person. CE credits tied to individual. |
| **Limitation of liability** | Cap liability at subscription price paid. Exclude consequential damages. |
| **Dispute resolution** | Arbitration clause with jurisdiction specification |
| **FERPA/education privacy** | If applicable — CE transcript data is educational records |
| **Data retention** | How long CE records are kept (ASRT requires records for duration of approval + X years) |

### Iubenda (Already Owned — $159/yr)
Iubenda can auto-generate:
- Privacy Policy (GDPR, CCPA, CalOPPA compliant)
- Cookie Policy
- Terms and Conditions (template-based, may need customization for CE-specific provisions)

**Recommendation**: Use Iubenda for privacy/cookie policies. Draft custom Terms of Service for CE-specific provisions (content accuracy, CE credit disclaimers, AI disclosure). Can be AI-drafted and attorney-reviewed.

---

## WRITER/SME CONTRACTS

### Current State
- All contracts are "Catalyst Medical Education Consulting Agreements"
- Signed with Heidi Veillette, Kelli Haynes, Jessyca Wagner, Mark Bowes
- W-9s on file for all four writers
- SOWs (Statements of Work) exist for individual course assignments

### Updates Needed for AI Pipeline
| Provision | Current | Needed |
|-----------|---------|--------|
| **Scope of work** | "Write original course content" | "Review and approve AI-generated course content for clinical accuracy" |
| **Compensation** | $2,000-$6,000 per course (writing) | $200-$500 per course (review/approval) — needs negotiation |
| **IP assignment** | Content created is work-for-hire owned by Catalyst | Add: "Reviews and modifications to AI-generated content are work-for-hire" |
| **AI disclosure consent** | N/A | Add: writer consents to being listed as clinical reviewer/author on AI-assisted content |
| **Liability** | Writer warrants accuracy of content | Clarify: writer warrants accuracy of final approved content (regardless of drafting method) |
| **Non-compete** | Unknown if present | Evaluate: prevent SMEs from reviewing for direct competitors |
| **Rate structure** | Per-course flat fee | Consider: hourly rate for review + per-course approval fee |

### New Contract Template Needed
- Updated consulting agreement for "SME Clinical Reviewer" role
- Clear work-for-hire IP assignment
- AI content disclosure and consent
- Hourly or per-course review compensation
- Clinical accuracy warranty
- Professional credential maintenance requirement

---

## DMCA / CONTENT PROTECTION

### Risks
- Competitors or users copying course content
- Users sharing login credentials for paid content
- Course content appearing on unauthorized sites
- AI training data concerns (courses being scraped for model training)

### Protections
| Protection | Implementation |
|------------|---------------|
| **DMCA agent registration** | Register with US Copyright Office ($6 fee) |
| **robots.txt** | Block scrapers from course content pages |
| **Login-gated content** | All course content behind authentication (LearnDash handles this) |
| **Copy protection** | Disable right-click/text selection on course pages (limited effectiveness) |
| **Watermarked certificates** | Unique identifiers on each certificate |
| **IP monitoring** | Periodic web search for copied content |
| **Terms of Service** | Explicit prohibition on content sharing/reproduction |

---

## ACCESSIBILITY COMPLIANCE

### Requirements
| Standard | Applies? | Why |
|----------|---------|-----|
| ADA Title III | Likely yes | Public accommodation (online education) |
| Section 508 | If government contracts | Federal accessibility standard |
| WCAG 2.1 AA | Best practice | Web Content Accessibility Guidelines |

### Implementation
- Kadence theme has good accessibility baseline
- Course content needs: alt text for images, proper heading hierarchy, color contrast, keyboard navigation
- Video content (if any) needs captions
- PDF certificates need accessibility tagging
- Quiz/assessment interfaces need screen reader compatibility

---

## PRIORITY SEQUENCE

1. **Confirm entity structure** — Is Catalyst properly structured? Does TechCElerate need separate registration?
2. **E&O insurance** — Get quotes immediately. Don't launch without coverage.
3. **Terms of Service** — Draft CE-specific terms. Use Iubenda for privacy/cookies.
4. **Sales tax research** — Determine if digital education exemptions apply. Configure Stripe Tax.
5. **Update writer contracts** — New SME reviewer agreement for AI pipeline.
6. **DMCA registration** — Quick, cheap, important.
7. **Accessibility audit** — Before launch, run WCAG 2.1 AA check on all pages.

---

## REFERENCE DOCUMENTS
- `TechCElerate_Master_Knowledge_Base.md` — canonical project reference
- Writer contracts folder — "Catalyst Medical Education Consulting Agreements"
- W-9s on file for all 4 writers
- Iubenda account (annual subscription, $159/yr)
- PNC bank account verification letters
