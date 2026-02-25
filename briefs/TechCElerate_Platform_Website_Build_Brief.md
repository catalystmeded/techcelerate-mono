# TechCElerate: Platform & Website Build Brief — All Verticals
## Prepared: 2026-02-22
## Purpose: Drop this into the dedicated Platform & Website Build chat as context
## Scope: PLATFORM-WIDE — Infrastructure serves all current and future verticals
## Note: The LMS, theme, automation, CRM, and payment stack are shared across all verticals. RT is the launch content set, but the platform architecture uses subdirectories (techcelerate-ce.com/radiology/, techcelerate-ce.com/pharmacy/, etc.) on a single WordPress install to support all future audiences. This decision is LOCKED — see Architecture Decision section below.

---

## WHAT THIS CHAT NEEDS TO PRODUCE

1. **Hosting decision** — Learning Templates 8 CPU Standard ($288/yr). Confirmed: NGINX, Ubuntu 24.04, dedicated server, cPanel. Pending: SSH, WP-CLI, cron confirmation (email sent). Fallback: Cloudways ($45/mo, 10-min pivot).
2. **WordPress installation and configuration** — from nginx welcome page to working LMS
3. **Theme and page architecture** — Kadence Pro setup, conversion-optimized design, all pages built per site copy docs
4. **LearnDash LMS configuration** — courses, quizzes, certificates, groups, access controls
5. **Payment processing** — Stripe + Paid Memberships Pro (or WooCommerce) integration
6. **Automation wiring** — Uncanny Automator triggers connecting LMS events to CRM, email, certificates
7. **HITL approval dashboard** — unified review queue for all pending human approvals

---

## CURRENT STATE

### What Exists
- **Domain**: techcelerate-ce.com (owned via Name.com)
- **Server**: Learning Templates hosting, IP 194.233.102.135, nginx welcome page visible
- **WordPress**: NOT installed
- **SSL**: Unknown (pending hosting eval)
- **DNS**: Managed at Name.com

### Tech Stack Owned (Confirmed — All Licenses Purchased)

**Core LMS Stack:**
| Plugin | Purpose | License | Status |
|--------|---------|---------|--------|
| LearnDash Plus + ProPanel | LMS engine | Annual $160/yr | 2x 10-site licenses. **⚠️ Expiry showed July 2021 — VERIFY** |
| Uncanny CE Credits | CE credit tracking + certificates | Annual (part of All Access $499/yr) | **⚠️ VERIFY renewal** |
| Uncanny Toolkit Pro | LearnDash enhancements | Part of All Access | Same as above |
| Uncanny Groups | Group enrollment management | Part of All Access | Same as above |
| Uncanny Codes | Enrollment codes/vouchers | Part of All Access | Same as above |
| Tin Canny Reporting | xAPI/SCORM reporting | Part of All Access | Same as above |

**Theme/Builder:**
| Plugin | Purpose | License |
|--------|---------|---------|
| Kadence WP Pro | Theme framework | Lifetime ($389) |
| Kadence Blocks Pro | Block editor extensions | Included with Kadence Pro |

**Automation/CRM:**
| Plugin | Purpose | License |
|--------|---------|---------|
| Uncanny Automator | Workflow automation (triggers/actions) | Lifetime Unlimited ($599) |
| FluentCRM Pro | CRM, email marketing, segmentation | Lifetime ($599) |
| Fluent Forms Pro | Form builder | Lifetime ($499) |

**Marketing/Analytics:**
| Plugin | Purpose | License |
|--------|---------|---------|
| AffiliateWP Ultimate | Affiliate/referral program | Lifetime ($559) |
| MonsterInsights Pro | Google Analytics integration | Annual $799/yr — **⚠️ VERIFY. Evaluate if needed at launch** |
| Social Ninja Pro | Social media feeds/integration | Lifetime ($299) |

**Performance/Legal:**
| Plugin | Purpose | License |
|--------|---------|---------|
| WP Rocket | Page caching | Annual $180/yr — **⚠️ VERIFY** |
| Iubenda | Privacy policy, cookie consent, T&C | Annual $159/yr — **⚠️ VERIFY** |

**NOT Needed (Cut):**
| Plugin | Reason |
|--------|--------|
| MailChimp ($370/mo) | Redundant — FluentCRM + Amazon SES replaces entirely. **Savings: $4,440/yr** |
| BuddyBoss | Too heavy for CE platform |
| Elementor/Divi | Kadence selected |
| CartFlows | Use Stripe + PMP instead |
| HubSpot | FluentCRM selected |
| Happy Scribe ($690) | Evaluate — may not be needed if not doing video transcription |
| Jasper | Evaluate — Claude API likely replaces for content generation |

**Needs Evaluation:**
| Plugin | Question |
|--------|----------|
| H5P | Interactive content (drag-drop, hotspot questions). Needed for ASRT 10% hotspot question requirement? |
| Paid Memberships Pro vs WooCommerce | Payment/subscription management. PMP is lighter. WooCommerce more extensible. |
| Gamification plugin | Engagement features. Defer to post-launch? |

### Plugins NOT Yet Purchased But Likely Needed
| Plugin | Purpose | Est. Cost |
|--------|---------|-----------|
| Paid Memberships Pro (or WooCommerce) | Subscription management + Stripe | Free core / $297-$597 for premium |
| Yoast SEO (or Rank Math) | SEO optimization | Free core / $99-$229 premium |
| UpdraftPlus (or similar) | Backup automation | Free core / $70-$195 premium |
| Wordfence (or similar) | Security | Free core / $119 premium |
| Amazon SES plugin (or FluentSMTP) | Transactional email delivery | Free (FluentSMTP) + SES costs |

---

## SITE ARCHITECTURE

### Architecture Decision: LOCKED — Single Install with Subdirectories

**Decision**: Single WordPress install using subdirectories for vertical separation.
**Rationale**: SEO authority consolidates on one domain. Maintenance is one codebase. Vertical-specific customization happens at the LearnDash course category level, not the URL level. Subdirectories can be migrated to subdomains later if ever needed.

**URL Structure:**
```
techcelerate-ce.com/                          ← Parent landing (multi-vertical hub)
├── /radiology/                               ← RT vertical landing page
│   ├── /radiology/courses/                   ← RT course catalog (filtered)
│   ├── /radiology/membership/                ← RT pricing + checkout
│   └── /radiology/chest-radiography/         ← Individual RT course
├── /pharmacy/                                ← Pharmacy tech vertical (future)
│   ├── /pharmacy/courses/
│   ├── /pharmacy/membership/
│   └── /pharmacy/compounding-basics/
├── /dental/                                  ← Dental hygienist vertical (future)
├── /account/                                 ← Shared user dashboard (all verticals)
├── /about/                                   ← Shared
└── /faqs/                                    ← Shared (or tabbed by vertical)
```

### Multi-Vertical Customization (Single Install)

Each vertical gets different accreditation rules, certificates, compliance requirements — all handled within one WordPress/LearnDash install:

| Requirement | How Customized Per Vertical | Plugin |
|---|---|---|
| Certificate template | Separate template per course category (RT → ASRT cert, Pharmacy → PTCB cert) | Uncanny CE Credits — multiple templates per category |
| Accreditation statement | RT: "Activity approved by ASRT." Pharmacy: "Approved by ACPE." Field value on certificate template. | Uncanny CE Credits template fields |
| Credit types | RT: Category A/A+. Pharmacy: CPE contact hours. Dental: CDT credits. Stored per course. | LearnDash custom fields + Uncanny CE Credits |
| Quiz/assessment rules | RT: 75% pass, 60% MC. Pharmacy: different rules. Configured per quiz, not globally. | LearnDash quiz settings (per quiz) |
| Required certificate fields | RT: 11 ASRT elements. Pharmacy: different elements per PTCB. Each vertical = own template. | Uncanny CE Credits — separate templates |
| Email sequences | RT subscriber → RT-specific welcome/biennium/course recs. Pharmacy → pharmacy sequences. | FluentCRM — tag-based segmentation |
| Pricing/membership | Separate membership levels: "RT Unlimited" $X/yr, "Pharmacy Unlimited" $Y/yr, "All Access" $Z/yr | Paid Memberships Pro — multiple levels |
| Course access | RT membership unlocks RT courses only. Pharmacy unlocks pharmacy only. All Access = everything. | LearnDash Groups + PMP integration |
| Compliance tracking | RT: 24 credits/2yr + CQR. Pharmacy: 20 credits/2yr. Dashboard shows vertical-specific progress. | Uncanny CE Credits + custom dashboard |
| State-specific rules | Course tagging: "CA-compliant" tag. Filterable in course catalog. | LearnDash tags + Kadence filtered grid |

### When to Split (Future — Not Now)
Single install handles 11 verticals cleanly. Only split if:
- A vertical needs its own admin team and development cycle
- Performance degrades from database size (unlikely before 1000+ courses)
- A vertical is sold or spun off as separate entity
- Migration path: subdirectory → subdomain is well-documented and low-risk

### Page Structure

**Header (all pages):**
- Logo (left) — TechCElerate with vertical sub-text per section (e.g., "FOR RADIOLOGIC TECHNOLOGISTS")
- Nav: CE Courses | Membership | About | FAQs | Account
- Vertical switcher (when 2+ verticals live)

**Home Page (techcelerate-ce.com/):**
- Hero: "Affordable CE for Healthcare Professionals" with vertical selection cards
- At RT-only launch: redirects directly to /radiology/ or IS the RT landing page
- Future: hub page with cards per vertical

**Vertical Landing Page (e.g., /radiology/):**
- Hero banner with RT-specific CTA ("Start for Free" or "Join Now")
- Value proposition bar (3-5 icons): ASRT Approved | Expert RT Authors | Instant Certificates | CQR Tracking
- Social proof: subscriber count, testimonials, ASRT approval badge
- Featured Courses grid (6 newest in this vertical)
- Price anchor: "All the CE you need for less than $1/week"
- "Get Started" CTA → Membership funnel

**CE Courses Page (/radiology/courses/):**
- Filterable course grid (by topic, credits, CQR category, state compliance)
- Search functionality
- Course cards with: title, credits, category (A/A+), CQR tags, estimated completion time

**Membership Page (/radiology/membership/):**
- Conversion-optimized funnel page
- Price comparison vs. competitors (anchored against ASRT $125/yr)
- "Free Course Friday" concept — 1 free course/month to drive signups
- Pricing tiers (pending pricing decision from RT Pricing brief)
- Stripe checkout integration
- Testimonials, trust badges, money-back guarantee

**About Page:**
- Company mission and positioning
- Author/SME credentials showcase
- Accreditation badges

**FAQs Page:**
- Categories: Membership, Credits, Technical, State Requirements
- Designed to minimize support (email-only support model)
- Tabbed by vertical when multiple verticals live

**Account/Dashboard:**
- LearnDash learner dashboard
- CE credit tracking (per vertical if user holds multiple memberships)
- Certificate download history
- Payment/subscription management
- CQR progress tracking (if RT)
- Biennium countdown timer

**Footer (all pages):**
- Terms and Conditions (Iubenda)
- Privacy Policy (Iubenda)
- State Requirements
- Contact Us (email only)
- ASRT approval badge + accreditation logos

---

## BRAND IMPLEMENTATION

### Colors (from Techcelerate_Brand_Guidelines_R1.pdf)
- **Cyan Blue**: #42A4D9 (RGB: 66, 164, 217)
- **Navy Blue**: #121531 (RGB: 18, 21, 49)

### Typography
- **H1**: Playfair Display, 50pt, Navy Blue
- **H2**: Playfair Display, 30pt, Navy Blue
- **H3**: Montserrat Semi Bold, 18pt, Cyan Blue, ALL CAPS, 50pt letter tracking
- **Body**: Montserrat Regular, 15pt, Navy Blue
- **Logo font**: Zanna
- **Sub-text font**: Montserrat Semibold, ALL CAPS

### Brand Tone
Innovative, Simple, Medical, Credible, Approachable, Intelligent, Sophisticated, Reliable

### Imagery Style
Technicians in warm, inviting environments. Modern but not sterile. Nice depth of field, bright lighting. Features pharmacy, veterinarian, radiological professionals.

---

## AUTOMATION ARCHITECTURE (What Gets Wired During Build)

### Uncanny Automator Triggers → Actions
| Trigger | Action | Plugin Chain |
|---------|--------|-------------|
| User completes LearnDash course | Generate CE certificate with 11 required ASRT elements | LearnDash → Uncanny CE Credits |
| User completes course | Add FluentCRM tag (course completed, credits earned) | LearnDash → Automator → FluentCRM |
| User registers | Welcome email sequence triggered | WordPress → Automator → FluentCRM |
| User purchases membership | Enroll in LearnDash group, activate access | Stripe/PMP → Automator → LearnDash Groups |
| Membership expires | Revoke course access, trigger renewal sequence | PMP → Automator → LearnDash + FluentCRM |
| User fails quiz 3x | Trigger support notification | LearnDash → Automator → FluentCRM/email |
| New course published | Notify all active subscribers | WordPress → Automator → FluentCRM |
| Affiliate referral converts | Credit affiliate, trigger payout | AffiliateWP → Automator |

### Certificate Automation (ASRT Compliance)
Certificate must auto-generate with these 11 elements (per ASRT requirements):
1. Sponsor name (TechCElerate / Catalyst MedEd)
2. Participant name (from user profile)
3. Activity title (exact, from ASRT approval letter)
4. ASRT reference number (preprinted)
5. Number of credits (preprinted)
6. Category (A or A+)
7. Approval statement: "Activity approved by ASRT."
8. Date completed (auto-populated)
9. Authorized representative signature (digital)
10. Participant's ASRT ID or unique identifier
11. Expiration date of CE activity

**Uncanny CE Credits plugin handles this** — needs configuration with template matching these 11 fields.

---

## HOSTING DECISION

### Status: Learning Templates — Pending 3 Confirmations
Email sent to Dennis (Feb 22, 2026) asking about SSH, WP-CLI, and custom cron.

**Learning Templates 8 CPU Standard ($288/yr + $120 setup):**
- 8 dedicated CPU cores, 8 GB RAM, 90 GB SSD, 4 TB bandwidth
- NGINX, Ubuntu 24.04, cPanel/WebMin, MariaDB
- SMTP pre-configured, Cloudflare CDN supported, UpdraftPlus + security pre-installed
- LearnDash NOT included on 8 CPU (included on 12 CPU+ plans)
- This is a dedicated server, not shared VPS — better raw performance than Cloudways/Kinsta at same price

**Three deal-breakers pending:**
1. SSH access — required for WP-CLI, Claude Code deployment, automation scripts
2. WP-CLI — required for automated plugin management, content deployment
3. Custom cron jobs — required for scheduled automation (not WordPress wp-cron)

**If any answer is no:** Pivot to Cloudways DO Premium 4 GB ($45/mo). Spin-up time: 10 minutes. Not a build blocker.

**Other confirmed requirements:**
| Requirement | Status |
|---|---|
| PHP 8.1+ | ✅ Multiple PHP versions available |
| REST API unrestricted | ✅ Dedicated server, no restrictions |
| External SMTP (Amazon SES) | ✅ SMTP pre-configured |
| CDN | ✅ Cloudflare supported, Zoom setup assistance |
| Backups | ✅ UpdraftPlus pre-installed |
| SSL | ✅ Included |
| Security | ✅ MalCare/WordFence pre-installed |

---

## BUILD SEQUENCE (Maximum Automation — Claude Builds, Lou Reviews)

### Phase 1: Foundation (Day 1)
- Server credentials received (SSH + WordPress admin)
- WordPress confirmed installed and configured (or we install via WP-CLI)
- SSL verified
- Kadence Pro theme activated
- Global styles configured: Cyan #42A4D9, Navy #121531, Playfair Display + Montserrat
- Permalink structure set
- User registration enabled with required fields (ASRT ID, profession)
- Security hardened
- **Lou's role**: Provide credentials, review global look and feel

### Phase 2: Conversion-Optimized Pages (Days 2-4)
- All pages built with Kadence blocks per site copy docs + conversion best practices
- RT landing page: hero → social proof → course grid → price anchor → CTA
- Membership/pricing page: competitor comparison, trust badges, testimonials, Stripe checkout
- Course catalog: filterable grid with credit counts, CQR tags, completion time estimates
- About page: credentials showcase, accreditation badges
- FAQs: support-minimizing, categorized
- Account/Dashboard: CE tracker, certificate history, biennium countdown
- **Design priority: conversion rate > aesthetics.** Every page has one job and one CTA.
- **Lou's role**: Review pages, approve design

### Phase 3: LMS Core (Days 5-7)
- LearnDash configured: course categories (Radiology as first), tags, CQR mapping
- Quiz engine: MC, T/F, matching per ASRT rules, 75% passing score
- Uncanny CE Credits: ASRT-compliant certificate template (11 required elements)
- Course structure: category-based for multi-vertical scaling
- 2-3 pilot courses loaded from existing FINAL drafts (RT_24003, RT_23001, RT_23009)
- **Lou's role**: Review certificate template, verify course rendering

### Phase 4: Payment & Access (Days 8-9)
- Stripe connected (Lou provides API keys)
- Paid Memberships Pro configured with RT membership level(s) per pricing decision
- LearnDash Groups: RT membership → RT course access
- Automator: purchase → group enrollment → course access → welcome email
- **Lou's role**: Create Stripe account, provide API keys, confirm pricing tiers

### Phase 5: CRM & Automation (Days 10-12)
- FluentCRM configured: RT subscriber segment, profession tags
- Amazon SES connected via FluentSMTP (Lou provides SES credentials)
- Email sequences deployed: welcome, onboarding, course completion, renewal, biennium
- Full automation chain tested: register → purchase → enroll → complete → certificate → CRM tag → email
- AffiliateWP activated and configured (defer recruitment to marketing phase)
- **Lou's role**: Create Amazon SES account, provide credentials, review email copy

### Phase 6: Content Loading (Days 13-16)
- Remaining FINAL/near-final courses loaded (up to 20 per content pipeline audit)
- Each course: content as HTML, quiz with question bank, CE credit value, CQR tags, certificate data
- SEO: Rank Math configured, sitemaps, meta descriptions per course
- Legal: Iubenda T&C + privacy policy pages live
- Performance: test page speed, optimize images (WebP), evaluate WP Rocket necessity
- **Lou's role**: Approve course rendering, verify compliance

### Phase 7: Testing & Soft Launch (Days 17-19)
- End-to-end automation testing (full user journey x3)
- Mobile responsiveness verification
- Cross-browser testing
- Beta testers invited (writer network, personal contacts)
- Monitor automation flows, fix issues
- **Lou's role**: Complete one full test journey yourself, invite beta testers

### Phase 8: Marketing Launch (Day 20+)
- Transition to Marketing & Growth workstream
- Social media profiles created
- First email blast to existing contacts
- SEO content pipeline activated
- Paid ads ready (if budget allocated)

**Total estimated build time: 17-19 working days from SSH credentials received to soft launch.** Marketing ramp runs parallel from Day 15+.

---

## LAURA'S PRODUCTION NOTES (Key Implementation Questions)

From Laura Notes.docx — these need answers during build:

1. **Tables/figures**: Need production work (redrawing, adding titles/footnotes). Solution: Create reusable image templates for course figures. AI can generate standardized figure images.

2. **Content posting**: "How is it set up — like a Word program so just copy and paste? Will you need HTML?" Solution: LearnDash uses WordPress block editor. Course content can be pasted from Word with formatting preserved, or generated via REST API as HTML.

3. **Table handling**: "Can they be posted from Word or need to be recreated?" Solution: HTML tables in LearnDash. AI pipeline should output course content as formatted HTML ready for direct insertion.

4. **Image format**: "What file format and image quality needed?" Solution: WebP for web delivery (with PNG/JPG fallback). Optimized at 72-150 DPI for screen viewing.

5. **Reference citations**: "Are reference citations linking to reference list and/or original source?" Solution: In-page anchor links from superscript citations to reference list at bottom of lesson. Standard web pattern.

6. **ASRT review access**: "ASRT needs to review posted content. Test link, username, password required." Solution: Create dedicated ASRT reviewer account with access to all courses. Include credentials in submission packet.

---

## REFERENCE DOCUMENTS
- `TechCElerate_Master_Knowledge_Base.md` — canonical project reference
- `WebDev_TechCElerate-ce.com.docx` — detailed site copy and page architecture
- `WebDev_TechCElerate_Info for Dennis_042823.docx` — hosting details and Dennis briefing
- `Techcelerate_Brand_Guidelines_R1.pdf` — colors, fonts, imagery, brand mark
- `Laura Notes.docx` — production/posting implementation questions
- `All Web and Tech List.xlsx` — complete plugin inventory with license keys
- `Plugins List for Dennis.xlsx` — developer-facing plugin list
