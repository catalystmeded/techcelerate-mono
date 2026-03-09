# TechCelerate Multi-Vertical AI Build Specification
## From RT CE Platform → Universal Mandatory Education Engine
### Created: March 1, 2026 | Version: 1.0

---

## STRATEGIC PREMISE

TechCelerate today: WordPress + LearnDash, single-profession (RTs), single-accreditor (ASRT), single-compliance-ruleset. TAM: $13M.

TechCelerate tomorrow: AI-powered multi-vertical mandatory education platform serving 55+ market segments across healthcare, financial, legal, compliance, and emerging markets. TAM: $40.8B+.

The transformation isn't about adding more courses. It's about building an **engine that can enter any mandatory education market in weeks instead of months**, with AI handling the 80% that's repetitive across all of them: content generation, compliance checking, assessment creation, certificate issuance, and learner tracking.

**Philosophy:** Automation tool, not vibecoding. Build the machine that builds the courses.

---

## ARCHITECTURE: WHAT CHANGES

### Current (Single-Vertical)
```
WordPress + LearnDash
  ├── RT courses (hardcoded content)
  ├── ASRT compliance rules (hardcoded)
  ├── Certificate template (1 format, 11 ASRT elements)
  ├── Pricing (RT-specific tiers)
  └── Marketing (RT audience only)
```

### Target (Multi-Vertical Engine)
```
TechCelerate Platform Engine
  ├── Vertical Registry (profession configs)
  │     ├── RT: ASRT rules, 24 credits/biennium, 1500 words/credit...
  │     ├── Sonographer: ARDMS rules, 30 credits/3yr...
  │     ├── Medical Assistant: AAMA rules, 60 pts/5yr...
  │     ├── CPA: NASBA rules, 40 hrs/yr...
  │     └── [any new profession added as config, not code]
  │
  ├── AI Content Engine
  │     ├── Course Generator (profession-aware)
  │     ├── Assessment Generator (compliance-aware)
  │     ├── Compliance Checker (ruleset-aware)
  │     └── Content Refresher (clinical/regulatory update scanner)
  │
  ├── Multi-Accreditation Manager
  │     ├── Certificate templates (per accreditor)
  │     ├── Submission packet generator (per accreditor)
  │     ├── Credit tracking (per profession's rules)
  │     └── Audit-ready reporting (per accreditor)
  │
  ├── Storefront Engine
  │     ├── Per-profession landing pages (auto-generated)
  │     ├── Per-profession pricing
  │     ├── Per-profession email sequences
  │     └── Per-profession SEO content
  │
  └── Intelligence Layer
        ├── Market demand signals (job postings, regulatory changes)
        ├── Competitive pricing monitor
        ├── Learner analytics (cross-profession)
        └── Accreditation deadline tracker
```

---

## THE 20 AI BUILD IDEAS

### LAYER 1: VERTICAL REGISTRY (The Foundation)
*Everything else depends on this. Parameterize the platform.*

---

#### BUILD 1: Profession Configuration Engine
**What:** A structured data layer where each profession is defined as a config object — not hardcoded into the platform. Each config includes: profession name, governing bodies, CE/credit requirements, cycle length, renewal rules, word-count-per-credit requirements, assessment rules (passing score, question count, question types), certificate required elements, state-specific variations, and approved delivery methods.

**Why:** Right now every compliance rule is baked into TechCelerate's LearnDash setup. Adding sonographers means manually reconfiguring everything. With a config engine, adding a new profession is a data entry task — upload a JSON config and the platform adapts.

**What it replaces:** Manual LearnDash configuration per profession. Currently takes weeks per new vertical. Target: hours.

**Implementation:**
- Supabase table: `profession_configs`
- Fields: profession_id, name, accreditor, credits_required, cycle_months, words_per_credit, pass_score, question_count, cert_elements[], state_overrides[], delivery_methods[], renewal_rules{}
- WordPress plugin reads config via REST API
- LearnDash course creation auto-applies config rules

**Build effort:** 2 sprints (foundation for everything)
**AI leverage:** Claude generates initial config from accreditor documentation — paste an accreditor's CE requirements PDF, get a structured config back in minutes.

---

#### BUILD 2: State Compliance Matrix
**What:** A database of state-specific CE requirements overlaid on each profession's national requirements. Many professions (nurses, engineers, insurance agents, attorneys, cosmetologists) have state-level requirements that add to or modify national rules. The matrix tracks: which states require what additional hours, which topics are state-mandated (e.g., opioid prescribing in 30+ states, implicit bias in CA/IL), and which states accept online delivery.

**Why:** State variation is the #1 barrier to multi-vertical expansion. This matrix is what makes the difference between "we serve RTs nationally" and "we serve 15 professions in all 50 states."

**Implementation:**
- Supabase table: `state_requirements`
- Fields: profession_id, state, additional_hours, mandated_topics[], online_allowed (bool), special_rules{}, regulatory_body, renewal_deadline_pattern
- Auto-populated initially from BLS/regulatory data
- Updated via regulatory change scanner (Build 14)

**Build effort:** 1 sprint for structure + ongoing population
**AI leverage:** Claude scrapes state licensing board websites and extracts structured requirements. 50 states × 15 professions = 750 configs. AI does this in days, human would take months.

---

#### BUILD 3: Multi-Accreditation Certificate Engine
**What:** A template system that generates compliant certificates for ANY accrediting body. ASRT requires 11 specific elements. AAMA requires different elements. NASBA requires different elements. Each certificate auto-populates based on the profession config.

**Why:** Certificates are legally binding documents. Wrong format = audit failure = accreditation risk. Currently one template hardcoded for ASRT. Need N templates, auto-selected.

**Implementation:**
- Certificate template library in WordPress (Uncanny Automator or custom)
- Each template maps to a profession_config.cert_elements[] array
- PDF generation with dynamic field population
- QR code verification link (anti-fraud)
- Batch certificate generation for employer accounts

**Build effort:** 1 sprint
**AI leverage:** Minimal — this is template engineering, not AI. But AI can audit certificates against accreditor requirements post-generation.

---

### LAYER 2: AI CONTENT ENGINE
*The machine that builds the courses.*

---

#### BUILD 4: Universal Course Generator
**What:** An AI pipeline that generates complete, compliance-ready CE courses for ANY profession in the Vertical Registry. Input: topic, profession, target credit hours. Output: complete course package (narrative content at required word count, learning objectives, references, author attribution framework, assessment questions, CE application packet).

**Why:** This is THE game-changer. Manual course development: $3K-8K per course, 4-8 weeks. AI-generated course (with SME review): $200-500 per course, 2-5 days. At scale across 15 professions, this is the difference between $1M+ content investment and $50K.

**How it works:**
```
INPUT: {
  topic: "AI in Diagnostic Imaging",
  profession: "RT",
  target_credits: 2.0,
  format: "self-study enduring"
}

PIPELINE:
1. Profession config lookup → word count target (3,000), question count (20), pass score (75%)
2. Literature scan → PubMed/Google Scholar for recent evidence on topic
3. Outline generation → learning objectives aligned to accreditor taxonomy
4. Content generation → multi-pass with clinical accuracy verification
5. Assessment generation → questions mapped to learning objectives
6. Compliance check → automated validation against profession config
7. SME review queue → human expert reviews AI output (HITL gate)
8. Certificate mapping → auto-tagged with correct accreditor elements
9. Submission packet → generates accreditor-ready application

OUTPUT: Complete course package ready for SME review → accreditor submission
```

**This is CAMEOS architecture applied to course generation.** Same pattern: template → generate → evaluate → enforce → HITL gate. The ralph-loop works here too.

**Build effort:** 4-6 sprints (this is the core product)
**AI leverage:** This IS the AI. Claude/GPT-4o for generation, consensus evaluation for quality, automated compliance checking, literature search for evidence base.

---

#### BUILD 5: Assessment Generator
**What:** AI-generated post-test questions that are: mapped to specific learning objectives, at the appropriate Bloom's taxonomy level for the profession, formatted per accreditor requirements (e.g., ASRT requires specific question types), distractor-validated (wrong answers are plausible but clearly wrong), and bias-checked.

**Why:** Question writing is the most time-consuming part of CE development. SMEs hate doing it. AI can generate 50 candidate questions in minutes; SME reviews and approves 20. Current state: 0 questions in LearnDash across all courses.

**Implementation:**
- Question generation prompt chain with profession-specific parameters
- Bloom's taxonomy level enforcement (knowledge/comprehension/application)
- Distractor quality scoring (too easy? too tricky? ambiguous?)
- Question bank with tagging: topic, objective, difficulty, profession
- Anti-cheating: question pool randomization per attempt

**Build effort:** 2 sprints
**AI leverage:** High. AI generates questions; SME approves. 90%+ reduction in SME time on assessment creation.

---

#### BUILD 6: Content Freshness Scanner
**What:** Automated monitoring that flags when existing course content is outdated due to: new clinical guidelines, regulatory changes, drug approvals/withdrawals, technology changes, or accreditor rule updates. Runs on a schedule (weekly for healthcare, monthly for others).

**Why:** Stale content is an accreditation risk and a learner trust killer. Currently no automated monitoring — rely on SMEs to manually check. Across 15 professions × 50+ courses each, manual monitoring is impossible.

**Implementation:**
- Scheduled Claude API calls with web search
- Per-course metadata: topic keywords, key guidelines referenced, drugs mentioned, technology referenced, last-reviewed date
- Scan sources: PubMed, FDA, CMS, professional society guidelines, regulatory body announcements
- Output: freshness score (green/yellow/red) + specific flagged items
- Integration: n8n workflow → flags route to content queue

**Build effort:** 2 sprints
**AI leverage:** Very high. AI monitors hundreds of sources across dozens of professions. Impossible manually.

---

#### BUILD 7: Content Repurposing Engine
**What:** Takes a single course and generates derivative formats: study guide PDF, infographic summary, podcast script, social media series (10 posts), email newsletter excerpt, video script, slide deck, and quick-reference card. Each derivative links back to the full course (lead generation).

**Why:** One $300 course investment should generate 8-10 marketing/educational assets. Most CE companies get 1. This is how you dominate SEO and social across 15 professions without a content team.

**Build effort:** 2 sprints
**AI leverage:** Very high — this is pure AI content transformation.

---

### LAYER 3: MULTI-STOREFRONT ENGINE
*One platform, many front doors.*

---

#### BUILD 8: Profession-Specific Storefront Generator
**What:** Automated generation of profession-specific landing pages, course catalogs, and marketing copy. Each profession gets its own "front door" — different branding accent colors, terminology, featured courses, and pricing — all generated from the Vertical Registry config + a small set of profession-specific brand parameters.

**Why:** A sonographer landing on a page full of RT content bounces. Each profession needs to feel like the platform was built for THEM. But building 15 custom storefronts manually is insane. AI generates them from templates + configs.

**Implementation options:**
- Option A (WordPress): Custom page templates with dynamic content based on profession URL parameter
- Option B (Subdomain): sono.techcelerate-ce.com, ma.techcelerate-ce.com, rt.techcelerate-ce.com
- Option C (Separate brands): TechCelerate for imaging, different brand for MAs, etc.

**Recommendation:** Option B — subdomains. One WordPress install, many front doors. SEO benefits of separate domains without maintenance overhead.

**Build effort:** 2 sprints
**AI leverage:** AI generates all copy, meta descriptions, FAQ sections, and SEO content per profession.

---

#### BUILD 9: Dynamic Pricing Engine
**What:** Per-profession, per-market pricing that auto-adjusts based on: competitive benchmarks (what others charge per credit in that profession), willingness to pay signals (profession median salary → price sensitivity), accreditation cost amortization (higher accreditation cost → higher pricing), and market maturity (new markets start with penetration pricing → raise to market rate).

**Why:** RTs pay $3-8/credit. Attorneys pay $10-30/credit. CPAs pay $5-15. One price fits none. Currently pricing is hardcoded for RTs.

**Implementation:**
- Pricing rules engine in profession_configs
- A/B testing framework for price optimization
- Competitive price monitoring (Build 15)
- Employer vs. individual pricing tiers per profession

**Build effort:** 1 sprint
**AI leverage:** AI monitors competitor pricing across professions. Price optimization via A/B test analysis.

---

#### BUILD 10: Automated Email Sequence Generator
**What:** For each new profession added to the platform, AI generates a complete email marketing sequence: welcome series, course recommendation based on credit needs, biennium/cycle renewal reminders (timed to THAT profession's cycle), completion congratulations, and re-engagement for lapsed learners. Each sequence uses profession-specific terminology, deadlines, and compliance language.

**Why:** Currently 5 email sequences designed for RTs. Each profession needs its own. 15 professions × 5 sequences × 8 emails = 600 emails. AI writes them all from profession configs.

**Build effort:** 1 sprint
**AI leverage:** Very high — Claude generates all email copy from profession config + email sequence template.

---

### LAYER 4: INTELLIGENCE & AUTOMATION
*The platform that gets smarter over time.*

---

#### BUILD 11: Accreditation Application Generator
**What:** AI generates complete accreditation/approval applications for new accrediting bodies. Input: target accreditor + TechCelerate's organizational info. Output: completed application packet, supporting documentation list, compliance checklist, and submission-ready forms.

**Why:** Accreditation applications are 80% boilerplate (organizational info, mission, policies, infrastructure) and 20% accreditor-specific. AI fills the 80% instantly, flags the 20% that needs human input. This is CAMEOS applied to accreditation — same pattern as grant proposal generation.

**This is where CAMEOS and TechCelerate architectures converge.** The proposal generation pipeline can be adapted: instead of generating grant proposals, it generates accreditation applications. Same template → generate → evaluate → enforce → HITL pattern.

**Build effort:** 3 sprints (high-value, reusable across all new verticals)
**AI leverage:** Very high. This is CAMEOS DNA applied to a different document type.

---

#### BUILD 12: Regulatory Change Monitor
**What:** Continuous scanning of regulatory sources across all professions in the Vertical Registry. Detects: new state CE mandates, accreditor rule changes, scope of practice expansions (trigger new training needs), new mandatory training topics (e.g., AI literacy mandates emerging), and license renewal deadline changes.

**Why:** Regulatory changes CREATE markets. When Illinois mandates sexual harassment training, that's instant demand. When CMS expands MA scope, that's mandatory training. The first platform to detect and respond wins.

**Implementation:**
- Scheduled web scraping + Claude analysis
- Sources: state legislature trackers, Federal Register, accreditor announcement pages, CMS/FDA/OSHA rule changes
- Output: categorized alerts with market impact assessment
- Auto-triggers: "New mandate detected → generate course outline → queue for SME review"

**Build effort:** 2 sprints
**AI leverage:** This is pure AI — scanning hundreds of sources, extracting structured data, assessing business impact.

---

#### BUILD 13: Competitive Intelligence Monitor
**What:** Automated tracking of competitor course catalogs, pricing, new course launches, and marketing across each profession. Answers: what are competitors charging, what topics are they covering that we're not, where are pricing gaps we can exploit, and which competitors are entering/exiting markets.

**Why:** 55 markets × 5-20 competitors each = too many to monitor manually. AI scans weekly and surfaces actionable intelligence.

**Implementation:**
- Competitor registry per profession (already partially built in TechCelerate competitive analysis)
- Weekly web scraping of competitor course pages
- Price comparison dashboard
- Gap analysis: topics competitors offer that we don't
- Alert: "Competitor X raised prices by 20% in CPA market" → pricing opportunity

**Build effort:** 2 sprints
**AI leverage:** High — AI scrapes, categorizes, and analyzes. Human acts on insights.

---

#### BUILD 14: Employer Dashboard (B2B)
**What:** Self-service portal for employers (hospitals, clinics, CPA firms, law firms, etc.) to: purchase bulk licenses for employees across multiple professions, track employee completion and compliance status, get alerts when employees' credits are expiring, generate compliance reports for auditors, and auto-assign required courses based on employee role/profession.

**Why:** B2B is where the money is. Individual RTs pay $50/year. A 500-bed hospital pays $50K+/year to keep all staff compliant across RT, nursing, HIPAA, BBP, infection control. The employer doesn't care about profession boundaries — they want ONE platform for all mandatory training.

**This is the killer app for multi-vertical.** An employer with RTs AND MAs AND nurses AND pharmacy techs wants ONE dashboard, not four platforms.

**Build effort:** 4-6 sprints (this is a product in itself)
**AI leverage:** AI generates compliance reports, predicts which employees will lapse, recommends courses based on role + gap analysis.

---

#### BUILD 15: Learner Intelligence Engine
**What:** Cross-profession learner analytics that tracks: individual learning paths, knowledge gaps (based on assessment performance), credit status vs. requirements, optimal course recommendations, and predictive alerts ("You need 8 more credits by March 2027 — here are 3 courses that fit your schedule").

**Why:** Most CE platforms are passive — learners browse a catalog. TechCelerate becomes a GPS for professional compliance: "Here's exactly what you need, when you need it, in the format you prefer."

**Build effort:** 2 sprints
**AI leverage:** Recommendation engine + predictive analytics. Claude API for personalized learning path generation.

---

### LAYER 5: SCALE INFRASTRUCTURE
*What makes this work at 15+ professions without 15× the team.*

---

#### BUILD 16: Course Quality Evaluator (MetaBuilder Pattern)
**What:** Automated quality scoring of every course — whether AI-generated or human-written. Evaluates: clinical/technical accuracy, readability level vs. target audience, compliance with accreditor requirements, assessment quality (question validity, distractor quality), and content freshness. Assigns a quality score (0-100) and flags specific issues.

**Why:** At scale (hundreds of courses across 15 professions), human QA review of every course is impossible. This is the MetaBuilder/SENTINEL pattern from CAMEOS applied to course content. The evaluator chain ensures quality doesn't degrade as you scale.

**This directly answers your question about using MetaBuilder as a build auditor.** Yes — the MetaBuilder architecture (Evals → AI Agent → LLM + Memory + Tools) works perfectly here. The evaluator chain audits each course, the memory stores quality baselines per profession, and the tools execute compliance checks.

**Build effort:** 3 sprints
**AI leverage:** Very high — consensus evaluation (Claude + GPT-4o) for quality scoring, just like CAMEOS quality_scorer_v2.py.

---

#### BUILD 17: Accreditation Submission Tracker
**What:** Pipeline management for accreditation applications across all professions. Tracks: application status per accreditor, required documents and their completion status, submission deadlines, reviewer feedback and required revisions, approval dates and renewal schedules.

**Why:** Managing 5-10 active accreditations simultaneously (ASRT, AAMA, ACPE, CAPCE, NASBA, etc.) requires project management. This is TechCelerate's internal operations tool.

**Build effort:** 1 sprint
**AI leverage:** Low — this is mostly project management. AI helps draft revision responses.

---

#### BUILD 18: Multi-Language Course Adapter
**What:** AI translation and cultural adaptation of courses for non-English-speaking learners. Priority languages: Spanish (huge in healthcare, food safety, construction), Mandarin, Tagalog, Vietnamese, Korean (per BLS healthcare workforce demographics).

**Why:** Food handler training alone has ~15M workers, many Spanish-speaking. HIPAA training covers 18M healthcare workers. Medical assistants are 29% Hispanic. Multi-language is both a market expansion play and an accessibility requirement.

**Build effort:** 2 sprints
**AI leverage:** Very high — Claude handles translation + cultural adaptation. Human reviewer for clinical/legal accuracy in target language.

---

#### BUILD 19: White-Label Platform Engine
**What:** The ability to license TechCelerate's infrastructure to other organizations (accredited providers, employer groups, professional associations) as a white-label platform. They get: their brand on the storefront, their course catalog, their pricing — but running on TechCelerate's engine (content generation, compliance checking, certificate issuance, learner tracking).

**Why:** This is the CAMEOS platform play applied to TechCelerate. Instead of serving learners directly in every market, you become the infrastructure layer. A state nursing board could white-label TechCelerate for their members. A CPA association could run their CE program on your engine. Revenue model shifts from per-learner to platform licensing (higher margins, stickier contracts).

**Build effort:** 6-8 sprints (major architectural work)
**AI leverage:** The AI content engine is the differentiator that makes white-label valuable. Without it, it's just another LMS.

---

#### BUILD 20: Market Entry Automation Pipeline
**What:** The fully automated pipeline for entering a new mandatory education market. Input: "We want to enter the [Medical Assistant] CE market." The pipeline executes:

```
1. SCOUT: AI researches the profession → generates Vertical Registry config
2. COMPLY: AI generates accreditation application → queues for human review
3. CREATE: AI generates first 10 courses → queues for SME review  
4. BUILD: Platform auto-creates storefront, pricing, email sequences
5. MONITOR: Competitive intelligence + regulatory monitoring activates
6. LAUNCH: Marketing automation sequences fire
```

**Why:** This is the endgame. New market entry goes from "6 months and $50K" to "2 weeks and $5K." At that speed, you can test markets cheaply — enter, measure demand, double down or exit.

**Build effort:** This isn't a separate build — it's Builds 1-18 working together as an automated pipeline.
**AI leverage:** This IS the AI platform. Every step is AI-powered with human gates at critical points.

---

## BUILD SEQUENCE (Recommended)

### Phase 0: Ship TechCelerate for RTs (NOW → Jul 4, 2026)
Don't change the current plan. Launch for RTs on time. Everything below is POST-LAUNCH.

### Phase 1: Foundation (Jul-Sep 2026) — 8 weeks
| Build # | Name | Effort | Unlocks |
|---------|------|--------|---------|
| 1 | Profession Config Engine | 2 sprints | Everything |
| 2 | State Compliance Matrix | 1 sprint | Multi-state delivery |
| 3 | Multi-Accreditation Certificate Engine | 1 sprint | New professions |
| 5 | Assessment Generator | 2 sprints | Course completeness |

**Outcome:** Platform can serve Sonographers, Nuclear Med, Rad Therapy (Tier 2 — zero accreditation cost) with proper configs, certificates, and assessments.

### Phase 2: Content Engine (Oct-Dec 2026) — 10 weeks
| Build # | Name | Effort | Unlocks |
|---------|------|--------|---------|
| 4 | Universal Course Generator | 4-6 sprints | Scalable content |
| 6 | Content Freshness Scanner | 2 sprints | Content maintenance at scale |
| 16 | Course Quality Evaluator | 3 sprints | Quality at scale |

**Outcome:** Can generate new courses for ANY configured profession in days, not months. Quality evaluation chain ensures standards. CAMEOS patterns directly reused.

### Phase 3: Growth Engine (Jan-Mar 2027) — 10 weeks
| Build # | Name | Effort | Unlocks |
|---------|------|--------|---------|
| 8 | Storefront Generator | 2 sprints | Multi-profession marketing |
| 9 | Dynamic Pricing Engine | 1 sprint | Per-profession economics |
| 10 | Email Sequence Generator | 1 sprint | Per-profession nurture |
| 11 | Accreditation Application Generator | 3 sprints | Fast market entry |
| 7 | Content Repurposing Engine | 2 sprints | 10× content ROI |

**Outcome:** Can enter Medical Assistants (743K market), Pharmacy Techs (472K), EMS (270K). Each new market entry is semi-automated.

### Phase 4: Intelligence Layer (Apr-Jun 2027) — 8 weeks
| Build # | Name | Effort | Unlocks |
|---------|------|--------|---------|
| 12 | Regulatory Change Monitor | 2 sprints | Proactive market entry |
| 13 | Competitive Intelligence Monitor | 2 sprints | Pricing + gap intelligence |
| 14 | Employer Dashboard (B2B) | 4-6 sprints | Enterprise revenue |

**Outcome:** B2B revenue stream active. Platform detects new regulatory mandates and auto-generates courses.

### Phase 5: Platform (Jul-Dec 2027) — 16 weeks
| Build # | Name | Effort | Unlocks |
|---------|------|--------|---------|
| 15 | Learner Intelligence Engine | 2 sprints | Personalization |
| 17 | Accreditation Submission Tracker | 1 sprint | Operations scale |
| 18 | Multi-Language Adapter | 2 sprints | Non-English markets |
| 19 | White-Label Engine | 6-8 sprints | Platform business model |
| 20 | Market Entry Automation Pipeline | Integration | Full automation |

**Outcome:** TechCelerate is a platform company, not a course company.

---

## COST COMPARISON

### Manual approach (no AI builds):
- Content development: $5K/course × 50 courses/profession × 15 professions = **$3.75M**
- Accreditation applications: $15K/accreditor × 10 accreditors = **$150K**
- Assessment creation: $1K/course × 750 courses = **$750K**
- Marketing per profession: $20K × 15 = **$300K**
- Staff: 5-10 additional FTEs = **$500K-1M/yr**
- **Total: ~$5M+ over 2 years, plus $1M+/yr ongoing**

### AI-powered approach (these 20 builds):
- Build investment: ~$150K-250K in development time (mostly your time + Claude)
- Content development: $300/course × 50 courses/profession × 15 professions = **$225K**
- Accreditation applications: $2K/accreditor × 10 accreditors = **$20K**
- Assessment creation: $50/course × 750 courses = **$37.5K**
- Marketing per profession: $3K × 15 = **$45K**
- Staff: 1-2 additional (SME reviewers) = **$100-200K/yr**
- **Total: ~$600K-800K over 2 years, plus $200K/yr ongoing**

**AI cost reduction: ~85% ($5M → $700K)**

---

## KEY ARCHITECTURAL DECISIONS NEEDED

1. **WordPress or custom?** LearnDash can stretch to multi-profession, but at 15+ professions with thousands of courses, custom React + headless CMS may perform better. Decision point: Phase 2.

2. **One domain or many?** techcelerate-ce.com/sono vs. sono.techcelerate-ce.com vs. sonoce.com. Impacts SEO, branding, and accreditor perception.

3. **Brand unity or profession brands?** "TechCelerate" signals technology professionals. Works for RTs. Doesn't work for CPAs. Options: umbrella brand ("ClearPath CE") with profession sub-brands, or keep TechCelerate for healthcare + acquire brands for non-healthcare.

4. **Build vs. acquire for non-healthcare?** CPA market ($3.9B) has established players. Building from scratch against Becker/Surgent/Western CPE is a decade-long fight. Acquiring a small NASBA-registered provider and porting the AI engine onto it is faster.

5. **CAMEOS codebase reuse?** Builds 4, 11, and 16 directly reuse CAMEOS patterns (template → generate → evaluate → enforce → HITL). Should they share a codebase (shared-services repo) or be independent implementations?

**Recommendation:** Shared. The content generation pipeline, quality evaluation chain, and compliance enforcement patterns are identical in architecture. Different configs, same engine. This is what the shared-services repo was designed for.

---

## ZERO-ACCREDITATION QUICK WINS (Launch Before Phase 1)

These markets require NO accreditation to enter. TechCelerate can add them to the existing platform immediately after RT launch:

| Market | Learners | Revenue Potential | What You Need |
|--------|----------|-------------------|---------------|
| HIPAA Training | 18M | $900M total market | Compliant content only |
| Bloodborne Pathogens | 18M | $270M total market | OSHA-compliant content |
| Infection Control | 18M | $450M total market | CMS-compliant content |
| Cybersecurity Awareness | 50M | $2.5B total market | No accreditation |
| AI Literacy (any profession) | 40M+ | $1.6B emerging | First mover advantage |

**Combined zero-accreditation TAM: $5.7B+**

These can be added as "compliance training" bundles alongside RT CE courses, especially for the Employer Dashboard play — hospitals need their RTs to have HIPAA + BBP + Infection Control training anyway.

---

## THE PUNCHLINE

You don't need 55 separate initiatives. You need **one engine with 55 configs.**

Every build on this list makes the NEXT market entry cheaper and faster. By Build 20 (Market Entry Automation Pipeline), adding a new profession to TechCelerate should take 2 weeks and cost under $5K — including AI-generated courses, compliance-checked assessments, auto-generated storefront, and marketing sequences.

That's not a CE company. That's a **mandatory education infrastructure company.**

And CAMEOS is the same pattern applied to CME proposal generation. The architectural DNA is identical. Build it once, apply it everywhere.
