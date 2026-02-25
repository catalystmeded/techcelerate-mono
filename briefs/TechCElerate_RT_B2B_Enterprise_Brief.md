# TechCElerate: B2B / Enterprise Channel Brief — RT Launch Vertical
## Prepared: 2026-02-22
## Purpose: Drop this into the dedicated B2B & Enterprise chat as context
## Scope: RADIOLOGIC TECHNOLOGISTS (RT) — Launch Vertical Only
## Note: This is a Phase 2+ workstream. Build after DTC launch is stable. Customer segments (hospital radiology departments, imaging centers) and outreach targets are RT-specific. The group enrollment system, enterprise pricing framework, and admin dashboard architecture are platform-wide and will serve all future verticals. When expanding, the same infrastructure supports pharmacy chains, dental offices, nursing departments, etc.

---

## WHAT THIS CHAT NEEDS TO PRODUCE

1. **B2B pricing model** — per-seat enterprise pricing for hospitals, imaging centers, clinics
2. **Group enrollment system** — LearnDash Groups + Uncanny Groups configuration
3. **Department admin dashboard** — manager-level reporting (compliance tracking, completion rates)
4. **Bulk licensing / purchase orders** — support for institutional procurement processes
5. **Enterprise outreach strategy** — targeting hospital radiology departments
6. **RT program partnerships** — relationships with accredited radiologic technology programs

---

## WHY B2B MATTERS

### Revenue Multiplier
Individual subscriptions at $19-$59/yr are the foundation. But B2B changes the math:
- Average hospital radiology department: 15-50 RTs
- Imaging center: 5-15 RTs
- Large health system: 100-500+ RTs across multiple facilities
- A single enterprise deal at 50 seats × $40/seat = $2,000/year — equivalent to 40+ individual subscribers

### Lower Acquisition Cost
- One sale serves many users
- Decision-maker is radiology manager or education coordinator, not individual RT
- Annual institutional budget line item (sticky revenue, lower churn)
- Often covered by employer education budget (removes price sensitivity)

### Competitive Landscape
- **Medical Professionals** already offers group rates for departments
- **ASRT** offers institutional membership packages
- **ScrubsCE** has no visible B2B offering
- **eRADIMAGING** has no visible B2B offering
- **X-RayCE** has no visible B2B offering
- **Opportunity**: Most competitors are DTC-only. B2B is an underserved channel.

---

## B2B CUSTOMER SEGMENTS

### Segment 1: Hospital Radiology Departments
| Attribute | Detail |
|-----------|--------|
| Decision-maker | Radiology Department Manager, Chief Technologist, or Education Coordinator |
| Size | 15-50 RTs per department, large systems 100-500+ |
| Budget | Annual CE/education budget per employee ($200-$500/RT typical) |
| Pain point | Tracking CE compliance across entire staff, ensuring everyone meets deadlines |
| Buying process | Budget approval → procurement/purchasing → PO or corporate credit card |
| Value proposition | Centralized compliance dashboard, bulk pricing, automatic ARRT reporting |

### Segment 2: Outpatient Imaging Centers
| Attribute | Detail |
|-----------|--------|
| Decision-maker | Practice manager, lead technologist, or medical director |
| Size | 5-15 RTs per location |
| Budget | Smaller education budgets, more price-sensitive |
| Pain point | Minimizing time-off-site for CE, ensuring all staff are current |
| Buying process | Often credit card purchase by manager |
| Value proposition | Affordable, fast, no travel needed, instant certificates |

### Segment 3: Multi-Site Health Systems
| Attribute | Detail |
|-----------|--------|
| Decision-maker | VP of Imaging Services, System-wide Education Director |
| Size | 100-500+ RTs across multiple facilities |
| Budget | Centralized education procurement |
| Pain point | Standardizing CE across all locations, tracking system-wide compliance |
| Buying process | RFP/RFQ process, vendor approval, multi-year contracts possible |
| Value proposition | Enterprise dashboard, SSO integration, LMS integration, volume pricing |

### Segment 4: RT Education Programs
| Attribute | Detail |
|-----------|--------|
| Decision-maker | Program Director, Department Chair |
| Size | 20-50 students per cohort, multiple cohorts per year |
| Budget | Student activity fees or program budget |
| Pain point | Preparing students for registry exams, introducing CE early |
| Buying process | Academic purchasing process |
| Value proposition | Free/discounted student access → pipeline to paid graduates |

---

## B2B PRICING FRAMEWORK

### Per-Seat Enterprise Pricing (Draft)
| Tier | Seats | Annual Price/Seat | vs. Individual | Notes |
|------|-------|-------------------|---------------|-------|
| Small Group | 5-14 | $39/seat | ~20% discount | Self-service signup |
| Department | 15-49 | $34/seat | ~30% discount | Admin dashboard included |
| Enterprise | 50-99 | $29/seat | ~40% discount | Dedicated account manager |
| Health System | 100+ | $24/seat | ~50% discount | Custom contract, SSO, API |

*Pricing TBD pending individual pricing decision (see Pricing & Unit Economics chat)*

### Add-On Features for Enterprise
| Feature | Value | Price |
|---------|-------|-------|
| Compliance dashboard | Manager sees all staff CE status, deadlines, completion rates | Included at 15+ seats |
| Custom reporting | Exportable compliance reports for regulatory audits | Included at 50+ seats |
| SSO integration | Single sign-on via SAML/LDAP | Enterprise tier only |
| Custom course library | Curated course selection for specific department needs | Available at 50+ seats |
| Dedicated support | Named account manager, priority support | Enterprise tier only |
| Invoice/PO billing | Net-30 institutional invoicing | Available at 15+ seats |

---

## TECHNICAL REQUIREMENTS

### LearnDash Groups (Already Owned)
- Uncanny Groups plugin enables group management
- Group leaders can enroll/remove members
- Group-level reporting and progress tracking
- Group-based course access control

### What Needs To Be Built
| Feature | Tool | Complexity |
|---------|------|------------|
| Group admin dashboard | Kadence + custom template + LearnDash Groups | Medium |
| Bulk user enrollment | Uncanny Codes (already owned) — generate enrollment codes | Low |
| Group compliance report | Tin Canny Reporting + custom views | Medium |
| Invoice/PO billing | WooCommerce or PMP with manual invoice option | Low |
| SSO integration | miniOrange SAML or WP SAML Auth plugin | High (defer to Enterprise tier) |
| Group CE transcript | Custom export combining LearnDash + Uncanny CE Credits data | Medium |

### Uncanny Codes for B2B
Already owned. Can generate batch enrollment codes:
- Manager purchases X seats → receives X unique enrollment codes
- Distributes codes to staff → each code activates individual account
- No need for manager to have staff email addresses upfront
- Trackable: see which codes are redeemed, by whom

---

## B2B OUTREACH STRATEGY

### Phase 1: Low-Touch (Leverage DTC Subscribers)
- Identify individual subscribers who work at hospitals/imaging centers
- "Does your department need CE credits? Ask your manager about group rates."
- Referral bonus for connecting us with decision-makers

### Phase 2: Direct Outreach
- Build target list of radiology department managers
- LinkedIn outreach to Chief Technologists and Education Coordinators
- Email campaign to hospital imaging departments
- Trade show presence at RSNA, ASRT annual conference

### Phase 3: Channel Partnerships
- State RT association partnerships (co-branded CE packages)
- GPO (Group Purchasing Organization) listings
- Healthcare staffing agency partnerships (CE as employee benefit)
- RT program partnerships (student pipeline to paid graduate subscriptions)

### RT Program Strategy (Long Game)
| Action | Outcome |
|--------|---------|
| Offer free access to RT students during program | Brand loyalty from day 1 |
| Provide program directors with compliance tools | Relationship with gatekeepers |
| Sponsor student RT organizations | Brand visibility in pipeline |
| Graduate discount (first year $X) | Convert students to paid subscribers at graduation |
| Track graduates → individual subscriptions → department referrals | Full lifecycle funnel |

---

## METRICS TO TRACK

| Metric | Target | Why |
|--------|--------|-----|
| B2B revenue as % of total | 20-30% by Year 2 | Diversification |
| Average deal size | $500+ annual | Efficiency of sales effort |
| Seats per account | 15+ average | Indicates department-level adoption |
| B2B churn rate | < 10% annual | Institutional contracts are stickier |
| Time to close | < 30 days (small), < 90 days (enterprise) | Pipeline velocity |
| Referral rate from DTC → B2B | 5%+ of individual subscribers refer their department | Organic B2B growth |

---

## REFERENCE DOCUMENTS
- `TechCElerate_Master_Knowledge_Base.md` — canonical project reference
- `TechCElerate_RT_Pricing_Unit_Economics_Brief.md` — individual pricing affects B2B tiers
- Medical Professionals website (medical-professionals.com) — reference for group rate positioning
- Uncanny Groups + Uncanny Codes documentation
- LearnDash Groups documentation
