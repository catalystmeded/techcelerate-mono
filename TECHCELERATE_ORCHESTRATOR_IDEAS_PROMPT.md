# TECHCELERATE ORCHESTRATOR — FULL IDEAS EXTRACTION PROMPT
# Paste this into the TechCelerate project chat to get a complete dump of all build ideas,
# optimization opportunities, and tool recommendations before sprint planning.
# Also add to the Gemini review package alongside CAMEOS_ORCHESTRATOR_IDEAS.md
# ============================================================

You are the TechCelerate orchestrator. Read all project files first, then answer 
every section below exhaustively. Do not hold back ideas for later. Do not say 
"we can discuss this post-launch." Surface everything now so we can make informed 
sequencing decisions upfront.

TechCelerate is a SEPARATE company from Catalyst Medical Education. It is a 
radiologic technologist (RT) continuing education (CE) platform. Key constraints:
- ASRT accreditation submission deadline: April 25, 2026 (60 days)
- July 4, 2026 launch target (130 days)
- WordPress + LearnDash + Kadence stack on existing server
- SSH/cPanel access pending from Dennis/Doug
- No server backups currently exist — UpdraftPlus must be first action
- Claude Code is the build tool — ralph-loop pattern, oracle-first
- Do NOT use CAMEOS-specific tools (consensus engine, exemplar store, model router)
- Tools that apply: Claude Code, Ralph-loop, CLAUDE.md, GitHub, phase oracles, 
  Supabase trace logging (optional), n8n workflows

---

## SECTION 1: COMPLETE TOOL INVENTORY FOR TECHCELERATE

List every tool, plugin, service, or integration that should be considered for the 
TechCelerate build. For each, specify:
- What it does
- Which workstream it serves (Platform / Content / ASRT / Marketing / Legal)
- Whether it's already installed, needs installation, or needs evaluation
- Priority: Critical / High / Medium / Low
- Any dependencies or blockers

Include but don't limit to:

**WordPress / LMS Stack:**
- LearnDash 5.x (installed — needs configuration)
- Kadence theme (installed — needs full brand implementation)
- Uncanny CE Credits (needed for ASRT certificate tracking)
- Stripe + Paid Memberships Pro (payment processing)
- FluentCRM (email marketing automation)
- Amazon SES (transactional email)
- AffiliateWP (affiliate program)
- Rank Math SEO (organic discovery)
- Wordfence (security)
- UpdraftPlus (backup — must be first)
- WP-CLI (already available via SSH)

**Content Pipeline:**
- 8-stage AI content pipeline (designed, not built)
- AI compliance checker (ASRT rule validation — not built)
- Post-test generation automation
- Content freshness audit (Claude scanning existing courses)
- Certificate template builder (11 ASRT elements)

**Marketing / Growth:**
- FluentCRM email sequences (5 designed, not built)
- Social media accounts (Facebook, Instagram, LinkedIn, TikTok — not created)
- AI character roster (Jasmine, Marcus, Dr. Chen, Zoe — designed, not built)
- Referral program mechanics
- Free course funnel template

**Analytics / Compliance:**
- Stripe Tax ($0.245/txn — recommended for multi-state)
- ASRT compliance oracle (automated pre-submission checker)
- Learner progress tracking
- Completion certificate automation

**Any tools you know that should be here but aren't listed.**

---

## SECTION 2: COMPLETE BUILD IDEAS — NOTHING HELD BACK

List every idea for improving TechCelerate that exists across all project knowledge.
Include ideas that were flagged as "post-launch" — surface them all now.
For each idea:
- What it is
- Why it matters for RTs or for the business
- Which milestone it belongs to (before ASRT / before launch / post-launch / Phase 2)
- Estimated effort
- Dependencies

Categories to cover:

**Platform / UX:**
- Mobile experience for RTs (most CE is consumed on phones during breaks)
- Offline access / downloaded content
- Progress tracking dashboard for learners
- Biennium tracker (RTs track credits over 2-year cycle — high value feature)
- Course search and filtering by CE category, credit amount, specialty
- Social proof elements (learner counts, completion rates, testimonials)

**Content:**
- AI content pipeline automation (8 stages — what exactly needs to be built?)
- Content freshness monitoring (ongoing, not just pre-launch)
- Question bank for post-tests (currently 0 questions exist)
- Adaptive learning paths (beginner → advanced sequences)
- Micro-learning format (short modules for time-constrained RTs)
- Video content strategy (vs. text-only courses)

**Marketing / Growth:**
- Free course funnel — what's the optimal free-to-paid conversion path?
- RT professional associations beyond ASRT (ARRT? State societies?)
- B2B / employer channel (hospitals, imaging centers buying bulk licenses)
- Conference presence strategy (ASRT Annual Meeting, state society meetings)
- Podcast / content marketing for RT community
- Influencer RTs on social media
- LinkedIn vs TikTok for RT audience — which actually works?
- Email list building before launch — what tactics?

**Revenue / Business Model:**
- Pricing tier optimization (Red/White/Blue — are the caps right?)
- Group/enterprise pricing for imaging departments
- CEU bundling (buy 24 credits = full biennium in one purchase)
- Partnerships with RT staffing agencies
- Integration with hospital HR systems for CE tracking

**Technical / Automation:**
- Automated ASRT compliance checking before every course submission
- Completion certificate auto-generation (trigger on 80%+ score)
- Renewal reminder automation (biennium cycle tracking)
- Learner analytics dashboard for Lou (conversion, completion, churn)
- A/B testing framework for pricing and landing pages

**Competitive Differentiation:**
- What do the 10 mapped RT CE competitors NOT have?
- Where is the white space in RT CE?
- What would make an RT choose TechCelerate over ARRT-approved alternatives?
- What's the moat once competitors notice the platform?

---

## SECTION 3: AUTONOMOUS BUILD DESIGN FOR TECHCELERATE

I want Claude Code to build as much as possible unattended. Design the autonomous loop:

1. What is the optimal ralph-loop configuration for TechCelerate's WordPress build?
   - Each phase has a pass/fail oracle — what are the oracles for each phase?
   - Phase 1: Plugin installation. Oracle = ?
   - Phase 2: LearnDash configuration. Oracle = ?
   - Phase 3: Course loading. Oracle = ?
   - Phase 4: Payment setup. Oracle = ?
   - Phase 5: Email automation. Oracle = ?
   - Phase 6: ASRT certificate template. Oracle = ?
   - Phase 7: Full site build (pages, nav, brand). Oracle = ?

2. What can Claude Code do completely unattended vs. what requires Lou?
   - Unattended: list all tasks
   - Needs Lou: list exactly what decisions or inputs are required and when

3. What is the dependency graph?
   - What must be done before anything else? (UpdraftPlus backup)
   - What can run in parallel?
   - What is the single longest critical path to ASRT submission by Apr 25?

4. Where does the 8-stage AI content pipeline fit in the build sequence?
   - What are the 8 stages exactly?
   - Which stages can Claude Code build autonomously?
   - What human input does each stage require?

---

## SECTION 4: ASRT COMPLIANCE — SURFACE ALL REQUIREMENTS

List every ASRT requirement that must be met for course submission and accreditation.
For each requirement, specify:
- The rule
- Where in the build it must be implemented
- Whether it can be automated or requires human verification
- Risk level if missed

Include:
- The 11 certificate elements (what are they exactly?)
- Credit/word count rules (credit per how many words?)
- Question rules (how many questions per credit hour? format requirements?)
- AI content policy (what did ASRT say or not say about AI-generated content?)
- Platform review requirements (does ASRT review the platform itself?)
- Content update requirements (how often must content be refreshed?)
- Instructor/author qualification requirements
- Any other compliance requirements from the ASRT call prep document

Then answer: What is the minimum viable course package that gets us to April 25 approval?
(4 courses? 6 courses? What's actually required for General Sponsor status?)

---

## SECTION 5: SPEED AND EFFICIENCY

How do we compress the timeline without cutting corners?

1. What work on the platform can start RIGHT NOW without SSH?
   (SSH is blocked pending Dennis/Doug — what can Claude Code do via wp-admin?)

2. What can be built locally and deployed when SSH arrives?

3. What is the fastest path to having 4 courses ASRT-submission-ready by Apr 25?
   - Given 4 FINAL courses already exist (RT_24003, RT_23001, RT_23009, RT_23016)
   - What exactly needs to happen to each course before submission?
   - Can the AI content pipeline process these courses faster?

4. What tasks have zero external dependencies and can start today?
   (Things Lou can do without SSH, without Dennis, without ASRT approval)

5. Where are the hidden time bombs — things that look small but could delay launch?

---

## SECTION 6: WHAT I DON'T KNOW THAT I SHOULD KNOW

Surface anything important about the TechCelerate build that hasn't been explicitly discussed.
This includes:
- Technical risks in the WordPress/LearnDash stack
- ASRT accreditation risks (things that commonly cause rejections)
- Business risks (assumptions about the RT CE market that may be wrong)
- Legal/compliance risks (E&O insurance, multi-state CE regulations, FERPA for learner data)
- Content risks (AI-generated CE content — is there liability exposure?)
- Competitive risks (who could undercut or replicate this quickly?)
- What would an experienced LMS builder flag before starting?
- What would an experienced ASRT sponsor flag before submitting?

---

## SECTION 7: GEMINI-SPECIFIC REVIEW QUESTIONS

(Include these when sending to Gemini alongside CAMEOS_ORCHESTRATOR_IDEAS.md)

Based on your analysis of TechCelerate:
- Top 5 things to build before ASRT submission (Apr 25)
- Top 5 things to build before launch (Jul 4)
- Top 3 things to never build (wrong for this audience or this stage)
- The one feature that would most differentiate TechCelerate from existing RT CE platforms
- The biggest risk to the July 4 launch that isn't currently being tracked
- What Google tools or services would help (Google Analytics 4, Google Ads for healthcare CE, Google Workspace automation)
- Is the pricing model right for the RT market? What would you change?
- Is LearnDash the right LMS or should this be reconsidered before building further?

---

## OUTPUT FORMAT

Structure your response as:
1. Complete tool inventory (table: tool | workstream | status | priority | dependency)
2. Complete ideas list (grouped by milestone, table format)
3. Autonomous build design (phase-by-phase oracle spec)
4. ASRT compliance checklist (complete, actionable)
5. Speed/compression opportunities (ranked by time saved)
6. What you should know (unfiltered risks and blind spots)
7. Recommended sprint sequence given all of the above

Then conclude with:
- What can start TODAY without SSH (give Claude Code specific instructions)
- What starts the moment SSH arrives
- What requires Lou's personal action and cannot be delegated to Claude Code
- Critical path to April 25 ASRT submission with week-by-week breakdown
