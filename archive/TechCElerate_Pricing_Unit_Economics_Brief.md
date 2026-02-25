# TechCElerate: Pricing & Unit Economics Brief
## Prepared: 2026-02-22
## Purpose: Drop this into the dedicated Pricing & Unit Economics chat as context

---

## WHAT THIS CHAT NEEDS TO PRODUCE

1. **Locked pricing decision** for RT launch vertical (subscription tier structure, price points)
2. **Unit economics model** showing cost-per-subscriber, break-even subscriber count, and margin targets
3. **Pricing framework** that scales across future verticals (the pricing engine, not just the RT price)
4. **Scenario modeling** across 3-5 price points with subscriber growth projections
5. **Competitive positioning map** — where TechCElerate sits and why

---

## COMPETITIVE LANDSCAPE (RT CE Market — Current as of Feb 2026)

### Competitor Pricing Matrix

| Provider | Model | Price | Credits Included | Course Library | Notes |
|----------|-------|-------|-----------------|----------------|-------|
| **ASRT** (asrt.org) | Annual membership | $125/yr ($340 for full membership w/ 17 CE) | 17 CE credits/yr (20 with premium) | 500+ courses | Industry association; also the accreditation body. Auto-transfers credits to ARRT. Includes journals, advocacy, career resources. The "premium" option everyone measures against. |
| **eRADIMAGING** | Annual membership | $54.95/yr | Unlimited access | Moderate library | Long-standing provider. Simple model. ASRT Category A approved. Good reviews from last-minute renewers. |
| **GetYourCEU** | Unlimited subscription | $44.99/yr | Unlimited access, 220+ courses, 24-credit courses available | 220+ courses | Strong in California and Texas markets. Free demo course. 22,000+ customer ratings. |
| **X-RayCE** (xrayce.com) | Per-course OR annual unlimited | $3-$75/course; $60/yr unlimited | Unlimited (annual) or per-credit purchase | 60+ courses, 110+ CE credits | Trusted by 50,000+ RTs since 2001. CQR tracking dashboard. Hybrid model (per-course + subscription). Free 1-credit course. |
| **Gage CE** (gagece.com) | Per-course | Varies (24-credit course packs available) | Per purchase | Large catalog incl. 24-credit bundles | Also operates scrubsce.com. Textbook-based courses. Phone support. |
| **ScrubsCE** (scrubsce.com) | Per-course | $54.95-$169.95 per course package | Per purchase (1,500+ credit hours available) | 1,500+ credit hours | Lowest price guarantee. Book + test or test-only options. Online + mail options. Same ownership as Gage CE. |
| **TakeCE** (takece.com) | Per-course bundles | $39.90-$69 for 15-27 credit bundles | Per purchase | Large catalog | 350,000+ CE credits awarded annually. 18,000+ professionals/year. Strong in Texas, California, Florida. 25% referral program. |
| **Medical Professionals** | Annual unlimited | $49.99/yr | Unlimited access, 70+ courses | 70+ courses (English & French) | Since 2002. 127,000+ RTs trained. Group rates for hospitals. ASRT-approved. |
| **FastCECredits** | Per-course | ~$5-8/credit | Per purchase | Moderate | Budget option. |
| **RadTechCredits** | Per-course | Low-cost | Per purchase | Small | Appears to be winding down (fulfilling through Dec 2026). |

### Market Pricing Summary
- **Budget tier**: $3-8 per credit (per-course purchase: TakeCE, FastCECredits, X-RayCE individual)
- **Value tier**: $44.99-$60/yr unlimited (GetYourCEU, eRADIMAGING, X-RayCE annual, Medical Professionals)
- **Premium tier**: $125-$340/yr (ASRT membership — includes non-CE benefits)
- **Legacy/textbook tier**: $55-$170 per course package (ScrubsCE, Gage CE)

### Key Insight
The market has clearly bifurcated: the legacy providers (ScrubsCE, Gage CE) still sell textbook-based per-course packages at $55-$170, while modern digital providers have converged on $45-$60/yr unlimited subscriptions. ASRT sits above at $125+ but bundles association membership benefits.

**Nobody is at $19/yr.** The lowest unlimited annual subscription is GetYourCEU at $44.99/yr. A $19/yr price would be 58% below the cheapest competitor.

---

## TechCElerate COST STRUCTURE

### Fixed Costs (Annual, Post-Launch)
| Item | Cost | Notes |
|------|------|-------|
| Hosting | $600-$1,800/yr | Depends on provider (Learning Templates vs Cloudways/Kinsta) |
| LearnDash license | $160/yr | Already owned (2x 10-site licenses) |
| Uncanny Owl All Access | $499/yr | CE Credits, Toolkit, Groups, Codes, Reporting |
| MonsterInsights Pro | $799/yr | Analytics (evaluate if needed at launch) |
| WP Rocket | $180/yr | Caching |
| Iubenda | $159/yr | Legal/privacy compliance |
| ASRT Institutional Provider | $325-$750/yr | Depends on submission volume |
| Domain/DNS | ~$20/yr | Name.com |
| **Total Fixed** | **~$2,742-$4,366/yr** | |

### Already-Owned (Lifetime Licenses — No Recurring Cost)
| Item | Paid | Notes |
|------|------|-------|
| Kadence WP Pro + Blocks | $389 | Theme/builder |
| FluentCRM Pro | $599 | CRM (replaces $370/mo MailChimp) |
| Fluent Forms Pro | $499 | Forms |
| Uncanny Automator | $599 | Workflow automation |
| AffiliateWP Ultimate | $559 | Affiliate marketing |
| Social Ninja Pro | $299 | Social media |
| **Total Already Invested** | **$2,944** | Zero ongoing cost |

### Variable Costs Per Course (AI-Assisted Pipeline)
| Component | Traditional Cost | AI-Assisted Cost | Notes |
|-----------|-----------------|-------------------|-------|
| Content drafting | $2,000-$6,000 | $100-$300 | AI generates 80%+, SME reviews |
| SME clinical review | Included above | $200-$500 | Licensed RT reviews AI-generated content |
| Editing/formatting | $200-$400 | $50-$100 | AI handles AMA formatting, human spot-checks |
| ASRT submission fee | $150-$365/course | $150-$365/course | Fixed by ASRT, not reducible |
| Post-test generation | Included above | $50 | AI generates, SME validates |
| LMS packaging | $100-$200 | $25-$50 | API-automated |
| **Total per course** | **$2,450-$6,965** | **$575-$1,365** | 75-80% cost reduction |

### Variable Costs Per Subscriber (Annual)
| Component | Cost | Notes |
|-----------|------|-------|
| Payment processing (Stripe) | 2.9% + $0.30/txn | On a $19 sub = ~$0.85; on a $49 sub = ~$1.72 |
| Amazon SES email | ~$0.50-$1.00/yr | Transactional + marketing emails |
| CE certificate generation | ~$0 | Automated via Uncanny CE Credits |
| Support (AI chatbot + escalation) | ~$0.50-$2.00/yr | 80% automated, human for Tier 2+ |
| **Total per subscriber** | **~$1.85-$4.72/yr** | Varies by price point |

---

## BREAK-EVEN SCENARIOS

### Assumptions
- 20 courses at launch (existing drafts, refreshed and packaged)
- Additional 10 courses/year generated via AI pipeline
- ASRT Institutional Provider at $325/yr (1-12 submissions)
- Course submission at $150-$260/course (self-learning, 1-2 year approval)
- Year 1 content investment: ~$15,000-$25,000 (refresh 20 courses + generate 10 new)

### Scenario A: $19/year
| Metric | Value |
|--------|-------|
| Revenue per subscriber | $19.00 |
| Stripe fee | $0.85 |
| Variable cost per sub | ~$1.85 |
| **Contribution margin** | **$16.30 (85.8%)** |
| Fixed costs (annual) | ~$3,500 |
| Break-even (fixed only) | **215 subscribers** |
| Year 1 content investment | ~$20,000 |
| Break-even (all-in Year 1) | **1,442 subscribers** |
| Target addressable market | 340,000+ RTs (ARRT registered) |
| Penetration needed | 0.42% for break-even |

### Scenario B: $39/year
| Metric | Value |
|--------|-------|
| Revenue per subscriber | $39.00 |
| Stripe fee | $1.43 |
| Variable cost per sub | ~$2.43 |
| **Contribution margin** | **$36.57 (93.8%)** |
| Fixed costs (annual) | ~$3,500 |
| Break-even (fixed only) | **96 subscribers** |
| Year 1 content investment | ~$20,000 |
| Break-even (all-in Year 1) | **643 subscribers** |
| Penetration needed | 0.19% |

### Scenario C: $49/year
| Metric | Value |
|--------|-------|
| Revenue per subscriber | $49.00 |
| Stripe fee | $1.72 |
| Variable cost per sub | ~$2.72 |
| **Contribution margin** | **$46.28 (94.4%)** |
| Fixed costs (annual) | ~$3,500 |
| Break-even (fixed only) | **76 subscribers** |
| Year 1 content investment | ~$20,000 |
| Break-even (all-in Year 1) | **508 subscribers** |
| Penetration needed | 0.15% |

### Scenario D: $59/year
| Metric | Value |
|--------|-------|
| Revenue per subscriber | $59.00 |
| Stripe fee | $2.01 |
| Variable cost per sub | ~$3.01 |
| **Contribution margin** | **$55.99 (94.9%)** |
| Fixed costs (annual) | ~$3,500 |
| Break-even (fixed only) | **63 subscribers** |
| Year 1 content investment | ~$20,000 |
| Break-even (all-in Year 1) | **420 subscribers** |
| Penetration needed | 0.12% |

### Revenue Projections at Scale (Year 2+, content costs amortized)

| Subscribers | $19/yr Revenue | $39/yr Revenue | $49/yr Revenue | $59/yr Revenue |
|-------------|---------------|---------------|---------------|---------------|
| 500 | $9,500 | $19,500 | $24,500 | $29,500 |
| 1,000 | $19,000 | $39,000 | $49,000 | $59,000 |
| 2,500 | $47,500 | $97,500 | $122,500 | $147,500 |
| 5,000 | $95,000 | $195,000 | $245,000 | $295,000 |
| 10,000 | $190,000 | $390,000 | $490,000 | $590,000 |

---

## STRATEGIC PRICING QUESTIONS TO RESOLVE

### 1. Single tier vs. multi-tier?
- **Single tier** (one price, unlimited access): Simplest. Easiest to market. What eRADIMAGING, GetYourCEU, and Medical Professionals do.
- **Multi-tier** (free/basic/premium): More revenue optimization. Risk of complexity. Could offer: Free (1 course/month) → Basic ($X/yr, unlimited) → Premium ($Y/yr, unlimited + CQR tracking + certificates).
- **Hybrid** (per-course + subscription): What X-RayCE does. Captures both budget-conscious per-credit buyers and subscription buyers.

### 2. Pricing position: disruptive vs. competitive?
- **Disruptive ($19-$29)**: Undercut everyone. Drives volume. Risk: perceived as low-quality. Requires high subscriber count for meaningful revenue.
- **Competitive ($39-$49)**: Match or slightly undercut established players (GetYourCEU at $44.99, Medical Professionals at $49.99). Signals quality. Lower volume needed.
- **Premium ($59-$79)**: Position on quality, CQR alignment, modern platform. Fewer subscribers needed but harder to acquire in price-sensitive market.

### 3. Free tier / lead magnet strategy?
- "Free Course Friday" concept (from WebDev docs) — one free course per month to drive signups
- Free introductory course to demonstrate quality (what X-RayCE does)
- Free for students / new graduates (under 25 or .edu email)?

### 4. B2B pricing (hospitals, imaging centers, clinics)?
- Group rates for departments (what Medical Professionals offers)
- Per-seat enterprise pricing
- Volume discounts
- This is potentially higher LTV than individual subscriptions

### 5. Annual vs. monthly billing?
- Annual only: Simpler, lower churn, better cash flow
- Monthly option: Lower barrier to entry, higher effective annual price, higher churn
- Market standard is annual for RT CE (because biennium cycle is 2 years)

### 6. Price anchoring against ASRT?
- ASRT membership is $125/yr for 17 CE credits (effectively $7.35/credit)
- At $49/yr for unlimited, TechCElerate is dramatically cheaper per credit
- Marketing angle: "All the CE credits you need for less than half the cost of ASRT membership — without the membership requirement"

---

## WHAT VARIES BY VERTICAL

When expanding beyond RT, pricing inputs change:

| Factor | Radiologic Technologists | Medical Assistants | Pharmacy Techs | Nurses |
|--------|-------------------------|-------------------|----------------|--------|
| CE required | 24 credits/2yr | 30-60 credits/2-5yr (varies by state) | 20 credits/2yr | 20-30 credits/2yr |
| Accrediting body | ASRT/ARRT | AAMA/AMT/NHA | PTCB/ExCPT | State boards/ANCC |
| Competitor pricing range | $45-$125/yr | $29-$79/yr | $39-$89/yr | $24-$60/yr |
| Content production cost | HIGH (clinical, SME required) | MEDIUM-HIGH (mixed clinical/admin) | HIGH (pharmacology, controlled substances) | HIGH (clinical, state-specific) |
| Workforce size | ~340,000 | ~760,000 | ~450,000 | ~4,000,000+ |
| Price sensitivity | Moderate (self-pay common) | High (often entry-level, lower wages) | Moderate | Low-Moderate (employer often pays) |
| B2B opportunity | Moderate (hospital groups) | High (employer-funded) | High (pharmacy chains) | Very High (hospital systems) |

**Key insight**: The pricing structure needs to be a FRAMEWORK, not a single number. Each vertical may have a different optimal price point based on competitive landscape, willingness to pay, and content production costs.

---

## DATA GAPS TO FILL IN THIS CHAT

1. **Current BLS wage data for RTs** — affects price sensitivity analysis (your BLS data is from 2018)
2. **Competitor course counts** — how many courses does each competitor actually offer? Affects perceived value.
3. **Churn benchmarks** — what's typical annual churn for CE subscription platforms? Affects LTV calculations.
4. **Employer reimbursement rates** — what percentage of RTs get CE costs reimbursed by employer? Affects price sensitivity.
5. **Student/new grad market size** — how many new RTs enter the workforce annually? Affects free tier sizing.
6. **State-specific requirements** — some states mandate specific topics (CA: digital radiography + fluoroscopy safety). Creates pricing leverage for compliant bundles.

---

## RECOMMENDED ANALYSIS SEQUENCE

1. Pull current BLS wage data for RTs and all target verticals
2. Model unit economics at $19, $29, $39, $49, $59 with sensitivity analysis
3. Map competitor value propositions (not just price — features, library size, UX)
4. Model subscriber growth scenarios (conservative, moderate, aggressive) for each price point
5. Determine if multi-tier makes sense or adds unnecessary complexity at launch
6. Evaluate B2B pricing as separate revenue stream
7. Lock the RT pricing decision
8. Build the vertical-agnostic pricing framework for expansion

---

## REFERENCE DOCUMENTS
- `TechCElerate_Master_Knowledge_Base.md` — canonical reference for all project data
- `TechCElerate_Overview_Automation_Blueprint.docx` — full automation blueprint and build sequence
- `Techcelerate_Brand_Guidelines_R1.pdf` — brand guidelines (colors, fonts, imagery)
- Original source files: `All Web and Tech List.xlsx`, `Writers.xlsx`, `CE Approval Information_ASRT.docx`
