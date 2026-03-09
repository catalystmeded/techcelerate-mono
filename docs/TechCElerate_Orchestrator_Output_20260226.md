# TECHCELERATE ORCHESTRATOR OUTPUT — COMPLETE IDEAS EXTRACTION
## Generated: 2026-02-26
## Source: All project briefs, site audit, Dennis correspondence, shared infrastructure, financial model, brand guidelines
## Status: SSH root access confirmed. WP-CLI installed. Claude Code ready.

---

# SECTION 1: COMPLETE TOOL INVENTORY

## WordPress / LMS Stack

| Tool | Workstream | Status | Priority | Dependencies | Notes |
|---|---|---|---|---|---|
| **LearnDash 5.0.1.1** | Platform | ✅ Installed, active | Critical | — | Needs full configuration: quiz engine, groups, access controls, CE credit settings |
| **Kadence Pro + Blocks Pro** | Platform | ✅ Installed, active | Critical | — | Brand partially implemented. Needs full page builds, nav structure, footer |
| **Kadence Child Theme (Learning Templates)** | Platform | ✅ Active | Critical | — | Custom child theme from Dennis. Preserve — don't replace with stock Kadence |
| **Uncanny CE Credits** | Platform/ASRT | ⬜ Need to install | Critical | Uncanny All Access license | ASRT certificate generation. 11 mandatory elements. No substitute. |
| **Uncanny Toolkit Pro** | Platform | ⬜ Need to install | High | Uncanny All Access license | LearnDash enhancements, custom fields, progress tracking |
| **Uncanny Groups** | Platform/B2B | ⬜ Need to install | High | Uncanny All Access license | Group enrollment for B2B Phase 2. Install now, configure later. |
| **Uncanny Codes** | Platform/B2B | ⬜ Need to install | Medium | Uncanny All Access license | Enrollment codes for enterprise. Install now, configure later. |
| **Uncanny Automator** | Platform | ⬜ Need to install | Critical | Lifetime license owned | Wires LMS events → CRM → email → certificates. The automation backbone. |
| **Tin Canny Reporting** | Platform | ⬜ Need to install | Medium | Uncanny All Access license | xAPI/SCORM reporting. Useful but not launch-critical. |
| **FluentCRM Pro** | Marketing | ⬜ Need to install | Critical | Lifetime license owned | Replaces $4,440/yr MailChimp. All email sequences, segmentation, automation. |
| **Fluent Forms Pro** | Platform | ⬜ Need to install | High | Lifetime license owned | Registration forms, survey forms (Levesque ASK Method), contact forms |
| **FluentSMTP** | Platform | ⬜ Need to install | Critical | Free plugin | Connects FluentCRM to Amazon SES. Without this, no emails go out. |
| **Paid Memberships Pro** | Platform | ⬜ Need to install | Critical | Free core; evaluate premium | Subscription management + Stripe. Replaces WooCommerce (lighter, purpose-built). |
| **AffiliateWP Ultimate** | Marketing | ⬜ Need to install | Medium | Lifetime license owned | Affiliate + referral program. Install now, recruit affiliates post-launch. |
| **Rank Math SEO** | Marketing | ⬜ Need to install | High | Free core | On-page SEO, sitemaps, meta descriptions. SEO drives long-term organic traffic. |
| **Wordfence** | Platform | ✅ Installed, active | Critical | — | 48% protection. Needs optimization, premium evaluation, 2FA enforcement. |
| **UpdraftPlus** | Platform | ✅ Installed, active | Critical | Google Drive account | Currently manual-only, no remote storage. Must connect to Google Drive FIRST. |
| **WP Rocket** | Platform | 🟡 License owned, not installed | Medium | Annual $180/yr — verify active | Page caching. Install after build is functional — caching during dev causes confusion. |
| **Iubenda** | Legal | 🟡 License owned, not installed | High | Annual $159/yr — verify active | Privacy policy, cookie consent, T&C. Legal requirement before launch. |
| **Stripe** | Platform | ⬜ Account not created | Critical | Lou creates account | Payment processing. Need API keys for PMP integration. |
| **Amazon SES** | Marketing | ⬜ Account not created | Critical | Lou creates AWS account | Email delivery at $0.10/1000. 24-hr sandbox approval required. Start now. |
| **SheerID** | Platform | ⬜ Not started | Medium | API integration | Heroes Program verification (veterans, first responders). Phase 2. |
| **H5P** | Content | ⬜ Evaluate | Low | — | Interactive content (hotspot questions for ASRT 10% requirement). May not need — LearnDash quiz types may suffice. |

## Plugins to REMOVE (Currently Installed)

| Plugin | Current Status | Why Remove | When |
|---|---|---|---|
| **WooCommerce** | Active | Replaced by PMP + Stripe. Heavy, unnecessary overhead. | Before PMP install |
| **WooCommerce Custom My Account** | Active | Goes with WooCommerce | Same time |
| **LearnDash WooCommerce Integration** | Active | Goes with WooCommerce | Same time |
| **WP Mail SMTP** | Active | Replaced by FluentSMTP + SES. Currently broken (421 error). | After FluentSMTP installed |
| **Kadence Custom Fonts** | Active | Flagged as abandoned by Wordfence. Security risk. | Immediately |
| **Kadence Shop Kit** | Inactive | WooCommerce-dependent. Removing WooCommerce. | With WooCommerce |
| **Kadence Starter Templates** | Active | Demo content already deleted. No longer needed. | After build complete |
| **Kadence Galleries** | Inactive | Not needed for CE platform | Now |
| **Kadence Child Theme Builder** | Inactive | Already have child theme from Dennis | Now |
| **CM Footnotes** | Inactive | Replaced by native anchor links in course template | Now |
| **WPForms Lite** | Inactive | Replaced by Fluent Forms Pro | Now |
| **The Events Calendar** | Inactive | Not needed | Now |
| **Kadence Conversions** | Active | Popups/slide-ins. Defer to post-launch. | Deactivate now, evaluate post-launch |
| **Kadence Reading Time** | Active | Nice to have but adds complexity. | Keep for now |

## Content Pipeline Tools

| Tool | Workstream | Status | Priority | Notes |
|---|---|---|---|---|
| **Claude API (via Claude Code)** | Content | ✅ Available | Critical | Drafts courses, generates questions, runs compliance checks, freshness audits |
| **ASRT Compliance Checker** | Content/ASRT | ⬜ Not built | Critical | Rule-based validation: word count, question count, format, required components. Build as Python script in Claude Code. |
| **Post-Test Generator** | Content | ⬜ Not built | Critical | AI generates MC questions from course content. SME validates. 0 questions exist currently. |
| **Certificate Template** | ASRT | ⬜ Not built | Critical | PDF template with 11 ASRT elements. Uncanny CE Credits plugin generates from template. |
| **Course HTML Template** | Content | ⬜ Not built | High | Standardized LearnDash HTML structure for all courses. Clinical pearl callouts, reference tooltips, key takeaways. |
| **Content Freshness Monitor** | Content | ⬜ Not built | Medium | Claude scans courses against current clinical guidelines. Annual cron job + on-demand. |
| **ASRT Submission Packet Generator** | ASRT | ⬜ Not built | High | Auto-generates Word doc + application fields + cover letter per course. |

## Marketing / Growth Tools

| Tool | Workstream | Status | Priority | Notes |
|---|---|---|---|---|
| **FluentCRM email sequences** | Marketing | ⬜ Designed, not built | High | 5 sequences: welcome, onboarding, completion, renewal, biennium. Copy exists in brief. |
| **HeyGen or Synthesia** | Marketing | ⬜ Not started | Medium | AI avatar video for characters (Jasmine, Marcus). Phase 2 — text-only at launch. |
| **Wave.video** | Marketing | ✅ Owned (AppSumo lifetime) | Medium | Video editing. Use when video content starts. |
| **Buffer or Hootsuite** | Marketing | ⬜ Not purchased | Medium | Social scheduling. $6-120/mo. Evaluate at launch. |
| **Canva** | Marketing | ⬜ Not purchased | Low | Social graphics. $13/mo. Claude can generate most assets. |
| **Google Ads** | Marketing | ⬜ Not started | Low | Phase 3+. After organic foundation. |
| **Meta Ads** | Marketing | ⬜ Not started | Low | Phase 3+. Facebook/Instagram targeting RT professionals. |

## Automation / Infrastructure Tools (from Shared Infrastructure)

| Tool | Workstream | Status | Priority | Notes |
|---|---|---|---|---|
| **Claude Code 2.1.58** | Platform | ✅ Ready to install on Mac | Critical | Primary build tool. Ralph-loop pattern. |
| **Remote Control (`/rc`)** | Platform | ✅ Available | High | Monitor Claude Code sessions from browser while doing other work. |
| **GitHub (techcelerate-mono)** | Platform | ✅ Repo initialized | High | Version control for scripts, CLAUDE.md, templates. Commit after each phase. |
| **GitHub Actions** | Platform | ⬜ Not configured | Medium | WP-CLI health check on commit. Course content validation. Post-launch. |
| **n8n** | Platform | ⬜ Not installed | Medium | Approval workflows for SME course review. Install on build machine. Post-launch for most use cases, but could help with ASRT submission tracking. |
| **Uptime Robot** | Platform | ⬜ Not configured | Medium | Free site monitoring. 5-minute pings. Set up at launch. |
| **Supabase trace logging** | Platform | 🟡 Available, optional | Low | Log Claude Code build steps. Nice for debugging but not required. |
| **Stripe Tax** | Legal | ⬜ Not configured | High | Auto sales tax at $0.245/txn. Configure with Stripe account. |

## Tools NOT in Current Plan That Should Be Considered

| Tool | What It Does | Priority | Why Consider |
|---|---|---|---|
| **MainWP** | Manage multiple WordPress sites from one dashboard | Low | Only useful when 2+ verticals launch. Phase 3+. |
| **Query Monitor** | WordPress debugging during development | Medium | Install during build, remove before launch. Catches slow queries, PHP errors. |
| **WP Crontrol** | View and manage WordPress cron jobs | Medium | Useful during build to verify automation triggers fire correctly. |
| **Redirection** | 301 redirect manager | High | Critical for subdomain → subdirectory migration. Every old URL must redirect. |
| **Google Site Kit** | GA4 + Search Console in WordPress | Medium | Free. Better than MonsterInsights ($799/yr). Evaluate replacing MonsterInsights. |
| **Complianz** | Cookie consent alternative | Low | Iubenda already owned. Only if Iubenda license lapsed. |
| **LearnDash Gradebook** | Grade tracking for learners | Low | Not needed for CE (pass/fail, not letter grades). |
| **GamiPress** | Gamification | Low | Completion streaks, badges, leaderboards. Fun but not launch-critical. Phase 2+. |
| **Simple History** | Audit log of all WordPress admin actions | Medium | Track what Claude Code changes. Good for debugging and accountability. |
| **Health Check & Troubleshooting** | WP debugging in safe mode | Medium | Install during build phase, remove before launch. |

---

# SECTION 2: COMPLETE BUILD IDEAS — NOTHING HELD BACK

## Before ASRT Submission (by April 25, 2026)

| ID | Idea | Why It Matters | Effort | Dependencies |
|---|---|---|---|---|
| A1 | **ASRT compliance checker script** | Automated validation of all ASRT rules before submission. Catches errors that would cause rejection. | 4-8 hrs Claude Code | ASRT rules documented ✅ |
| A2 | **Course freshness audit (4 FINAL courses)** | 2-3 year old content may have outdated guidelines, retracted references, stale statistics. | 2-4 hrs per course (AI pass), 1-2 hrs SME review each | Course docs accessible ✅ |
| A3 | **Post-test question generation** | 0 questions exist. ASRT requires 2 questions per 0.25 credits. 4 courses need ~40+ questions total. | 2-3 hrs Claude Code generation + SME validation | Course content finalized |
| A4 | **ASRT submission packet generator** | Auto-fills application form, compiles Word doc, generates cover letter, creates reviewer credentials. | 4-6 hrs to build template | Compliance checker done |
| A5 | **Certificate template (11 elements)** | ASRT won't approve without compliant certificate. Can submit to approval@asrt.org for free pre-review. | 2-4 hrs with Uncanny CE Credits | Plugin installed |
| A6 | **ASRT reviewer test account** | ASRT needs to access courses on the live platform to review. Dedicated account with full access. | 30 min | Site functional |
| A7 | **CQR category mapping for all 4 courses** | Competitive differentiator. Also validates that courses cover required ARRT content specifications. | 2 hrs (AI maps, SME validates) | ARRT content specs |
| A8 | **Reference URL validation** | Check every citation URL in all 4 courses. Flag broken links, retracted papers, updated guidelines. | 1 hr per course (automated) | Course docs |
| A9 | **Word count verification** | Verify each course meets ASRT credit-to-word-count minimums using exact inclusion/exclusion rules. | 30 min per course (automated) | Compliance checker |
| A10 | **Contact ASRT about 3-year approval** | Confirm 3-year is available for self-learning. $365 vs $260 (2-yr) — saves on resubmission cycles. | 5 min on call | ASRT call pending |

## Before Launch (by July 4, 2026)

| ID | Idea | Why It Matters | Effort | Dependencies |
|---|---|---|---|---|
| L1 | **Complete plugin swap** | Remove WooCommerce stack, install Uncanny/Fluent/PMP/Rank Math stack. Current site has wrong plugins. | 2-3 hrs Claude Code | Plugin .zips downloaded |
| L2 | **Subdomain → main site migration** | SEO authority on one domain. Dennis handles nginx after WordPress migration. | 4-6 hrs Claude Code + Dennis | Dennis coordination |
| L3 | **Full page build (7+ pages)** | Landing page, pricing, courses catalog, about, FAQ, account dashboard, free course page. All lorem ipsum currently. | 8-12 hrs Claude Code | Brand guidelines ✅, pricing locked ✅ |
| L4 | **LearnDash full configuration** | Quiz engine, access controls, groups, course categories, certificate integration, progress tracking. | 4-6 hrs Claude Code | Uncanny plugins installed |
| L5 | **Load all 20 courses into LearnDash** | Content as HTML lessons, quizzes with question banks, CE credit values, CQR tags, images. | 1-2 hrs per course (40 hrs total, highly automatable) | Course content processed |
| L6 | **Stripe + PMP payment setup** | Subscription checkout, founding tier pricing (Red/White/Blue), auto-enrollment on purchase. | 3-4 hrs | Stripe account created |
| L7 | **FluentCRM + SES email automation** | 5 email sequences, subscriber segmentation, biennium tracking, automated triggers. | 6-8 hrs Claude Code | SES account + FluentCRM installed |
| L8 | **Uncanny Automator trigger wiring** | Course complete → certificate → CRM tag → email. Purchase → group enrollment → access. ~12 automations. | 4-6 hrs Claude Code | All plugins installed |
| L9 | **ARRT credit reporting tool** | "Report My Credits" button: auto-generates copy-paste text, PDF summary, direct ARRT portal link. Zero-cost differentiator. | 4-6 hrs | LearnDash + Uncanny CE Credits configured |
| L10 | **Biennium countdown dashboard widget** | Shows days/credits remaining. iCal download for 90/60/30 day reminders. Captures birth month at registration. | 3-4 hrs | LearnDash user profile fields |
| L11 | **50 state CE requirements pages** | High-value SEO play. Each page maps TechCElerate courses to state requirements. | 8-12 hrs (AI generates, human spot-checks) | State requirements researched |
| L12 | **Free course funnel** | One permanently free 1-credit course. Registration gate (email + name + profession). Welcome sequence trigger. | 2-3 hrs | FluentCRM configured |
| L13 | **Mobile-first responsive testing** | RTs complete CE on phones during breaks. Every page, every course, every quiz must work perfectly on mobile. | 4-6 hrs testing + fixes | Pages built |
| L14 | **Founding member campaign pages** | Red/White/Blue tier landing pages with live counters, countdown timers, urgency mechanics. | 4-6 hrs | PMP + Stripe configured |
| L15 | **Refund automation** | 7-day window, 2-course completion cap. Stripe checks days + completions automatically. | 2-3 hrs | Stripe + LearnDash data integration |
| L16 | **Student/new grad free tier** | .edu email or graduation <12 months = free Year 1. FluentCRM auto-tags, 11-month conversion sequence. | 3-4 hrs | FluentCRM + PMP configured |
| L17 | **ARRT Registry Exam Prep Tool** | Free practice questions (repurposed from post-test banks). Email gate. Top-of-funnel for student pipeline. | 6-8 hrs | Question bank exists |
| L18 | **Security hardening** | SSL verification, file permissions, admin 2FA, remove Doug's admin account (downgrade to editor), XML-RPC disabled, REST API restricted. | 2-3 hrs Claude Code | SSH access ✅ |
| L19 | **UpdraftPlus → Google Drive automated daily backups** | Dennis confirmed no server backups. This is the only disaster recovery. | 30 min | Google Drive account |
| L20 | **SEO foundation** | Rank Math config, XML sitemap, robots.txt, meta descriptions for all pages, schema markup for courses. | 3-4 hrs | Rank Math installed |
| L21 | **Favicon + site icon** | Currently not set. Brand identity gap. | 15 min | Brand mark SVG exists ✅ |
| L22 | **Admin email fix** | Currently support@learning-templates.com with pending change to support@techcelerate.com (note: missing dash). Should be support@techcelerate-ce.com. | 5 min | — |
| L23 | **Privacy Policy + Refund Policy** | Currently in Draft status. Must be Published before launch. Iubenda generates privacy; refund policy needs custom draft. | 1-2 hrs | Iubenda configured |
| L24 | **Levesque ASK survey** | Embedded in registration: "What frustrates you most about CE?" FluentCRM tags based on response → personalized onboarding. | 2-3 hrs | Fluent Forms + FluentCRM |
| L25 | **Hormozi value stack on pricing page** | Perceived value $265+ crossed out, show actual price. Competitor comparison table. "Feel stupid saying no" design. | 2-3 hrs | Page build phase |
| L26 | **Course completion social sharing** | "Share your certificate" to LinkedIn/Facebook. Free marketing from every completion. | 2-3 hrs | Certificate template done |
| L27 | **Email list building landing page** | "Get notified when founding tiers open July 4" — live June 1. Captures emails before launch. | 1-2 hrs | FluentCRM configured |
| L28 | **Server cron jobs** | Replace wp-cron with real cron for reliable scheduled tasks (backups, email queues, content checks). Dennis said he'll add cron commands for you. | 30 min | Send commands to Dennis |
| L29 | **MonsterInsights evaluation** | $799/yr. Google Site Kit (free) does 80% of the same thing. Save $799/yr by switching. | 1 hr evaluation | — |
| L30 | **"Quick Complete" format for short courses** | Single-page reading experience for 0.5-1.0 credit courses. No clicking through 8 lessons for a 30-min course. | 2-3 hrs per course template | LearnDash configured |

## Post-Launch (Phase 2+)

| ID | Idea | Why It Matters | Effort | Dependencies |
|---|---|---|---|---|
| P1 | **AI Learning Characters (Jasmine, Marcus, Dr. Chen, Zoe)** | No competitor does this. Parasocial familiarity increases completion rates, social sharing, brand recognition. | 2-4 weeks total (avatars, scripts, videos, social pipeline) | HeyGen/Synthesia subscription |
| P2 | **B2B enterprise channel** | Single hospital deal = 50 subscribers. Lower acquisition cost, stickier revenue. Per-seat pricing $24-39/seat. | 4-6 weeks to build group enrollment, admin dashboard, billing | LearnDash Groups + Uncanny Groups |
| P3 | **Video courses (ESPN-style)** | Short video summary (5-10 min) + full transcript below. Variable playback speed. Captions for accessibility. | 2-3 weeks per course | HeyGen or manual recording |
| P4 | **Per-course pricing option** | $8/course when annual is $39. Makes annual the obvious deal. Revenue from RTs who won't commit to subscription. | 1-2 weeks | PMP configured |
| P5 | **Monthly billing option** | Market tests whether monthly demand exists. Higher churn but captures a segment. | 1 week | PMP configured |
| P6 | **Adaptive learning paths** | Beginner → intermediate → advanced sequences based on quiz performance. | 2-3 weeks | Sufficient course library (30+) |
| P7 | **Micro-learning modules** | 15-minute bite-sized lessons for time-constrained RTs. 0.25 credit each. | 1 week per module | Content pipeline |
| P8 | **Hospital HR integration** | SSO, LMS-to-HR data sync, compliance reporting. Enterprise tier only. | 4-8 weeks | B2B channel established |
| P9 | **CE credit auto-reporting to ARRT** | Direct digital submission to ARRT instead of manual reporting. Massive differentiator if technically possible. | Research needed — ARRT may not have an API | ARRT cooperation |
| P10 | **Gamification** | Completion streaks, badges, leaderboards, department challenges. GamiPress or custom. | 2-3 weeks | Post-launch engagement data |
| P11 | **Podcast: "RT Rounds"** | Weekly 15-min podcast covering clinical topics, CE tips, industry news. Characters as hosts. | Ongoing (2-3 hrs/week) | Character voices established |
| P12 | **Conference presence** | ASRT Annual Meeting booth, state RT society sponsorships. Physical presence builds trust. | $5,000-15,000/event | Revenue justifies investment |
| P13 | **Spanish language courses** | ~15% of RTs are Hispanic/Latino. No competitor offers Spanish CE. First mover advantage. | 2-3 weeks per course (AI translation + bilingual SME review) | English courses stable |
| P14 | **Offline/downloadable content** | PDF versions of courses for areas with poor connectivity. Also useful for employer printing. | 1-2 weeks | Course content finalized |
| P15 | **A/B testing framework** | Test pricing page designs, course titles, email subject lines, ad copy. Data-driven optimization. | 1 week setup | Sufficient traffic (>500 visitors/month) |
| P16 | **Second vertical expansion** | Medical assistants, pharmacy techs, dental hygienists, or respiratory therapists. Same platform infrastructure. | 3-6 months per vertical | RT vertical profitable |
| P17 | **White-label enterprise** | License TechCElerate platform to hospitals who want branded CE portals. | 2-3 months | B2B channel proven |
| P18 | **CEU bundling product** | "Complete Biennium Pack" — 24 credits in one purchase. Appeals to procrastinators near deadline. | 1 week | 24+ credits of courses available |
| P19 | **RT staffing agency partnerships** | CE as employee benefit. Staffing agencies buy bulk licenses for their placed RTs. | 2-4 weeks outreach | B2B pricing established |
| P20 | **Integration with hospital scheduling** | Auto-assign CE courses during scheduled downtime. Integration with radiology department scheduling systems. | Research needed | Enterprise relationships |
| P21 | **Heroes Program (SheerID)** | Free lifetime access for veterans, military, EMTs, firefighters, police. "Free for Life. Pay It Forward." | 2-3 weeks | SheerID API integration |

---

# SECTION 3: AUTONOMOUS BUILD DESIGN

## Ralph-Loop Configuration for TechCElerate

### Phase 0: Backup + Security
**Spec:** Server has automated off-site backups, security baseline, clean admin accounts.
**Oracle (pass when ALL true):**
- `UpdraftPlus Settings → Remote Storage` shows Google Drive connected ✅
- Automated daily backup schedule configured (files + database)
- `wp user list --allow-root` shows ≤2 admin accounts (Lou + ASRT reviewer)
- Doug's account downgraded to Editor or removed
- `wordfence scan --allow-root` returns 0 critical issues
- Kadence Custom Fonts deactivated and deleted
- All admin passwords changed from defaults

**Unattended?** 90% — needs Lou's Google Drive OAuth and decision on Doug's account.

### Phase 1: Plugin Swap
**Spec:** Remove old plugins, install correct stack, all active with no conflicts.
**Oracle (pass when ALL true):**
```bash
wp plugin list --allow-root --status=active --format=csv | sort
```
Returns exactly these active plugins (and no others from the remove list):
- affiliatewp
- fluent-crm-pro (or equivalent slug)
- fluent-forms-pro
- fluentsmtp
- kadence-blocks
- kadence-blocks-pro
- kadence-pro
- kadence-reading-time
- learndash (sfwd-lms)
- learndash-hub
- paid-memberships-pro
- rank-math-seo
- uncanny-automator
- uncanny-ce-credits (or equivalent slug)
- uncanny-groups
- uncanny-owl-toolkit-pro
- updraftplus
- wordfence

AND `wp plugin list --allow-root --status=active` shows 0 update notices.
AND visiting wp-admin shows no PHP errors or fatal notices.

**Unattended?** 95% — needs plugin .zip files pre-downloaded to server or uploaded via wp-admin. May need license key activation for Uncanny/FluentCRM/Kadence (Lou provides keys).

### Phase 2: LearnDash Configuration
**Spec:** LMS configured for RT CE delivery with proper quiz engine, access controls, certificate integration.
**Oracle (pass when ALL true):**
- LearnDash Settings → General: Focus Mode enabled, accent color #42A4D9
- LearnDash Settings → Registration: Custom registration page set
- Course categories created: "Radiography", "MRI", "CT", "Radiation Safety", "Patient Care"
- Course tags for CQR categories created: "CQR-Safety", "CQR-Image Production", "CQR-Patient Care", "CQR-Procedures"
- Quiz settings: 75% passing score default, open-book enabled, unlimited retakes
- LearnDash Groups: "RT Unlimited" group created
- Certificate template: test certificate generates with all 11 ASRT elements
- User registration captures: ASRT ID, birth month (for biennium tracking), profession
- `wp learndash course list --allow-root` returns proper course categories

**Unattended?** 80% — needs Lou to verify certificate template matches ASRT requirements, approve registration field design.

### Phase 3: Course Loading
**Spec:** All FINAL courses loaded as LearnDash courses with lessons, quizzes, proper HTML formatting.
**Oracle (pass when ALL true):**
- Each course has: title, author, learning objectives, outline, lessons matching outline sections, images, references
- Word count per course meets ASRT minimum for claimed credits (verified by compliance checker)
- Post-test quiz exists per course with correct question count (2 per 0.25 credits)
- Quiz questions: ≥60% multiple choice, no "all/none of the above", negative wording formatted correctly
- Each quiz has answer key with learning objective mapping
- Course renders correctly on desktop and mobile (no broken HTML, images load, tables don't overflow)
- `wp post list --post_type=sfwd-courses --allow-root` returns expected course count

**Unattended?** 70% — needs course source documents (Word files) processed to HTML. AI can process, but SME must validate clinical accuracy before final load. Lou must provide course files.

### Phase 4: Payment Setup
**Spec:** Stripe processes payments, PMP manages subscriptions, purchase triggers course access.
**Oracle (pass when ALL true):**
- Stripe test mode: successful test payment creates subscriber
- PMP membership levels: "Founders Red" ($250 one-time), "Founders White" ($9.99/yr), "Founders Blue" ($19.99/yr), "250th Extended" ($25/yr), "RT Standard" ($39.99/yr)
- Each membership level mapped to "RT Unlimited" LearnDash group
- Purchase → auto-enrollment in group → course access granted (verified end-to-end)
- Cancellation → access revoked at end of billing period
- Refund webhook → Stripe handles within 7-day window
- Stripe Tax enabled for multi-state compliance
- Receipt/invoice email sends on purchase

**Unattended?** 60% — needs Stripe API keys from Lou. PMP membership levels need Lou's approval on naming/pricing (already locked but verify). Test payment requires human verification.

### Phase 5: Email Automation
**Spec:** FluentCRM sends automated emails through Amazon SES for all user lifecycle events.
**Oracle (pass when ALL true):**
- FluentCRM → Settings → Email: Amazon SES connected, test email delivers
- 5 email sequences created and active:
  1. Welcome (5 emails over 14 days, triggers on registration)
  2. Onboarding (5 emails over 30 days, triggers on purchase)
  3. Course Completion (4 emails over 7 days, triggers on LearnDash course complete)
  4. Renewal (5 emails starting 60 days before expiry)
  5. Biennium Deadline (4 emails starting 90 days before ARRT deadline)
- Subscriber tags created: profession, subscription tier, courses completed, CQR categories, student status
- Test user journey: register → purchase → complete course → receives all triggered emails

**Unattended?** 85% — needs SES credentials from Lou. Email copy can be AI-generated from marketing brief. Lou reviews copy before activating sequences.

### Phase 6: ASRT Certificate Template
**Spec:** Uncanny CE Credits generates PDF certificates with all 11 mandatory ASRT elements on course completion.
**Oracle (pass when ALL true):**
- Certificate PDF contains ALL 11 elements:
  1. ✅ Sponsor name: "Catalyst Medical Education / TechCElerate"
  2. ✅ Participant name (from user profile)
  3. ✅ Activity title (exact match to ASRT approval letter)
  4. ✅ Reference number (ASRT-assigned, stored in course metadata)
  5. ✅ Number of credits (from course metadata)
  6. ✅ Category (A or A+)
  7. ✅ Approval statement: "Activity approved by ASRT."
  8. ✅ Date completed (auto-populated from LearnDash)
  9. ✅ Authorized representative signature (digital image)
  10. ✅ Participant's ASRT ID (from user profile field)
  11. ✅ Expiration date (from course metadata)
- Certificate auto-downloads on quiz pass (≥75%)
- Certificate emailed via FluentCRM on completion
- Certificate permanently accessible in user dashboard
- Send sample to approval@asrt.org for free compliance check → passes

**Unattended?** 75% — needs Lou's digital signature image, decision on sponsor name format, ASRT reference numbers (available only after approval).

### Phase 7: Full Site Build
**Spec:** All pages built with Kadence blocks, conversion-optimized, brand-compliant, mobile-responsive.
**Oracle (pass when ALL true):**
- All pages built: Home/Landing, Courses Catalog, Membership/Pricing, About, FAQ, Contact, Account Dashboard, Free Course, Privacy Policy, Terms, Refund Policy
- Brand compliance: Cyan #42A4D9, Navy #121531, Playfair Display headings, Montserrat body, TechCElerate logo
- Navigation: Primary menu matches site architecture
- Mobile: all pages render correctly on iPhone/Android viewport (no horizontal scroll, touch-friendly)
- Pricing page: Hormozi value stack, competitor comparison, founding tier CTAs with live counters
- Courses page: filterable grid by topic, credits, CQR category
- Account dashboard: CE credit tracker, certificate downloads, biennium countdown
- Footer: Terms, Privacy, Contact, ASRT badge, accreditation logos
- Page speed: <3 second load time (check via Google PageSpeed Insights)
- SEO: Rank Math shows green for all pages (title, meta, readability)

**Unattended?** 70% — Claude Code builds all pages. Lou reviews design and approves. Brand mark and imagery may need sourcing. Course catalog requires courses loaded first.

## Dependency Graph

```
Phase 0 (Backup/Security)
    │
    ├── Phase 1 (Plugin Swap) ──────── requires .zip files + license keys
    │       │
    │       ├── Phase 2 (LearnDash Config)
    │       │       │
    │       │       ├── Phase 3 (Course Loading) ──── requires processed course HTML
    │       │       │       │
    │       │       │       └── Phase 6 (Certificate) ──── requires ASRT reference numbers
    │       │       │
    │       │       └── Phase 4 (Payment) ──── requires Stripe API keys
    │       │
    │       └── Phase 5 (Email) ──── requires SES credentials
    │
    └── Phase 7 (Site Build) ──── can start after Phase 1, runs parallel with 2-6
```

**Critical path to ASRT submission (April 25):**
Phase 0 → Phase 1 → Phase 2 → Phase 3 (4 courses only) → Phase 6 → ASRT submission packets

**Critical path to July 4 launch:**
All phases + remaining course loading + marketing prep + email list building

## What Claude Code Does Unattended vs. What Requires Lou

### Fully Unattended (Claude Code + SSH)
- Install/remove/update plugins via WP-CLI
- Configure LearnDash settings via WP-CLI + REST API
- Build all pages with Kadence blocks via REST API
- Create quiz question banks from processed course content
- Wire Uncanny Automator triggers
- Set up FluentCRM tags, lists, segmentation rules
- Configure Rank Math SEO for all pages
- Security hardening (file permissions, .htaccess, disable XML-RPC)
- Create course HTML from Word/markdown source files
- Run ASRT compliance checks on all courses
- Generate post-test questions from course content
- Build ASRT submission packets
- Set up AffiliateWP commission structure
- Configure UpdraftPlus backup schedule
- Create all user registration form fields

### Requires Lou's Input
| Input Needed | When | How Long |
|---|---|---|
| Google Drive OAuth for UpdraftPlus | Phase 0 | 5 min |
| Decision on Doug's account | Phase 0 | 2 min |
| Plugin license keys (Uncanny, FluentCRM, Kadence, AffiliateWP) | Phase 1 | 15 min |
| Stripe account + API keys | Phase 4 | 15 min |
| Amazon SES account + credentials | Phase 5 | 20 min |
| Digital signature image for certificates | Phase 6 | 5 min |
| Review/approve certificate template | Phase 6 | 15 min |
| Review/approve page designs (each page) | Phase 7 | 30 min per page |
| Review/approve email sequence copy | Phase 5 | 30 min |
| Course source files (Word docs) if not already in monorepo | Phase 3 | Upload time |
| Approve founding tier names/pricing (already locked) | Phase 4 | 5 min confirmation |
| Send course submission packets to ASRT | After build | 30 min |

**Total Lou time: ~4-5 hours across entire 2-3 day build.** Everything else is autonomous.

---

# SECTION 4: ASRT COMPLIANCE — COMPLETE REQUIREMENTS

## 11 Certificate Elements (Mandatory)

| # | Element | Source | Automation | Risk if Missing |
|---|---|---|---|---|
| 1 | Sponsor's name (exact, from approval) | Static: "Catalyst Medical Education / TechCElerate" | Hardcoded | Certificate invalid |
| 2 | Participant's name | WordPress user profile | Auto-populated | Certificate invalid |
| 3 | Activity title (exact, from approval letter) | Course metadata field | Auto-populated | Certificate invalid |
| 4 | Reference number (preprinted) | ASRT-assigned after approval | Stored in course meta | Certificate invalid |
| 5 | Number of credits (preprinted) | Course metadata | Auto-populated | Certificate invalid |
| 6 | Category (A or A+) | Course metadata | Auto-populated | Certificate invalid |
| 7 | "Activity approved by ASRT." | Static text | Hardcoded | Certificate invalid |
| 8 | Date completed | LearnDash completion timestamp | Auto-populated | Certificate invalid |
| 9 | Signature of instructor or authorized rep | Digital signature image | Embedded in template | Certificate invalid |
| 10 | Participant's ASRT ID or unique identifier | User profile field (collected at registration) | Auto-populated | Certificate invalid |
| 11 | Expiration date of CE activity | From ASRT approval letter (1-3 year term) | Stored in course meta | Certificate invalid |

**Free compliance check available:** Send sample to approval@asrt.org before launch.

## Credit-to-Word-Count Rules

| Credits | Min Words | Min Questions |
|---|---|---|
| 0.25 | 1,600 | 2 |
| 0.50 | 2,450 | 4 |
| 0.75 | 3,700 | 6 |
| 1.00 | 4,900 | 8 |
| 1.50 | 7,375 | 12 |
| 2.00 | 9,850 | 16 |
| 3.00 | 14,750 | 24 |
| 4.00 | 19,700 | 32 |

**Included in word count:** Main text, headings, in-text citations, tables, figures, legends, footnotes, embedded questions (ungraded).
**Excluded:** Title page, TOC, reference list, appendices, post-test questions (counted separately with 1.85x multiplier).

## Question Format Rules

- ≥60% must be multiple choice (4 options, 1 correct)
- ≤10% each: true/false, matching, hotspot, fill-in-blank (40% max combined)
- No "All of the above," "None of the above," "Both a and b"
- Negative wording (NOT, EXCEPT) must be **uppercase, bold, italic**
- Positive emphasis (MOST, ALWAYS, TRUE) similarly highlighted
- All options must be plausible
- Correct answers mapped to specific learning objectives
- 75% passing score required

## Required Course Components (ASRT Checks All)

| Component | Automatable? | Notes |
|---|---|---|
| Title and author with credentials | ✅ 100% | Template-driven |
| Course outline | ✅ 100% | Generated from lesson structure |
| Learning objectives (measurable) | 🟡 90% | AI generates, SME validates "measurable" criterion |
| Highlights box (3-4 key takeaways) | ✅ 100% | AI extracts from content |
| Main body (evidence-based, fair-balanced) | 🟡 80% | AI drafts, SME validates clinical accuracy |
| Tables/figures with citations | 🟡 85% | AI formats, human verifies image permissions |
| References (AMA 11th edition) | ✅ 90% | AI formats, regex validates pattern |
| Post-test with answer key + LO mapping | 🟡 85% | AI generates, SME validates |

## ASRT Submission Format (Confirm on Call)
- Word document (required for reviewer)
- Online test link + username + password for reviewer access
- Application form (pre-filled by submission packet generator)
- Author credentials/CV

## AI Content Policy (UNKNOWN — Ask on Call)
- No known written ASRT policy on AI-generated content
- Mitigation: list SME reviewer as author, disclose AI assistance if asked
- Frame as: "Developed with AI-assisted research tools, reviewed and approved by [SME Name, Credentials]"

## Risks That Commonly Cause ASRT Rejections
1. Word count doesn't meet minimum for claimed credits
2. Learning objectives not measurable (use Bloom's taxonomy verbs)
3. Questions don't map to learning objectives
4. References not in AMA 11th edition format
5. Missing required components (highlights box, outline)
6. Content not evidence-based (opinion vs. clinical evidence)
7. Outdated references (>5 years old without justification)
8. Certificate missing any of the 11 elements

## Minimum Viable Package for April 25

**You need:** 4 courses submitted as General Sponsor. No minimum course count required for General Sponsor status — you can submit 1 course or 100. Each is reviewed independently.

**Recommended first batch:**
| Course | Credits | Submission Fee (3-yr) | Status |
|---|---|---|---|
| RT_24003 Chest Radiography | 3.0 | $365 | FINAL — needs freshness audit |
| RT_23001 MS MRI | 0.5 | $365 | FINAL — needs freshness audit |
| RT_23009 Radiation Physics | ~1.0-2.0 | $365 | FINAL — needs freshness audit + credit verification |
| RT_23016 Radiography Imaging | ~1.0-2.0 | $365 | FINAL — needs freshness audit + credit verification |

**Total: $1,460 for 3-year approval on 4 courses covering ~5-8 credits.**

If all 4 approved, that's enough for a credible launch. Not a full biennium (24 credits) but enough to prove value and collect founding members while remaining courses are completed.

---

# SECTION 5: SPEED AND COMPRESSION

## Ranked by Time Saved

| # | Opportunity | Time Saved | How |
|---|---|---|---|
| 1 | **Claude Code builds all pages unattended** | 10-15 days → 8-12 hrs | REST API + Kadence blocks, not manual page builder |
| 2 | **AI processes all 20 course docs to LearnDash HTML** | 40-80 hrs → 8-10 hrs | Batch process Word → HTML with standard template |
| 3 | **AI generates all post-test questions** | 20-30 hrs → 4-6 hrs | Generate from content, SME validates (not writes) |
| 4 | **ASRT compliance checker catches errors before submission** | 2-4 week rejection delay → 0 | Automated pre-check means first submission is clean |
| 5 | **In-house Medical Director reviews instead of external SME** | 2-4 week contractor scheduling → same day | No dependency on Heidi/Kelli/Jessyca for routine updates |
| 6 | **3-year ASRT approval** | Eliminates 2 resubmission cycles | $105 more upfront saves $300+ and weeks of work over 3 years |
| 7 | **Skip video at launch (text-only courses)** | 4-8 weeks saved | Video adds production complexity with minimal ASRT benefit |
| 8 | **Use Google Site Kit instead of MonsterInsights** | Saves $799/yr and 2 hrs setup | Free, native, does 80% of MonsterInsights |
| 9 | **Dennis handles nginx, you handle WordPress** | Saves days of server config debugging | Clear boundary, Dennis is fast |
| 10 | **Rush fee as insurance** | Buys 5 extra weeks on ASRT deadline | $520 for 4 courses if submission slips past April 25 |

## Fastest Path to 4 Courses ASRT-Ready by April 25

| Week | Action | Output |
|---|---|---|
| **Week 1 (Feb 26 - Mar 4)** | AI freshness audit on 4 FINAL courses. Upload docs to Claude, get clinical accuracy report + reference check + stats update. | 4 audit reports identifying what needs updating |
| **Week 2 (Mar 5 - 11)** | Medical Director reviews AI audit findings, approves or flags corrections. AI applies corrections, re-runs compliance check. | 4 clinically current courses |
| **Week 3 (Mar 12 - 18)** | AI generates post-test questions for all 4 courses. Medical Director validates question quality and clinical accuracy. | 40+ validated post-test questions |
| **Week 4 (Mar 19 - 25)** | Run ASRT compliance checker on all 4 courses. Fix any gaps. Build ASRT submission packets. | 4 submission-ready packets |
| **Week 5 (Mar 26 - Apr 1)** | Build certificate template. Send sample to approval@asrt.org for free pre-check. Load 4 courses into LearnDash (test environment). | Certificate approved, courses live on platform |
| **Week 6 (Apr 2 - 8)** | Create ASRT reviewer test account. Package final submissions. | Ready to submit |
| **Week 7 (Apr 9 - 15)** | Final review. Submit to ASRT. | Submitted ✅ |
| **Buffer (Apr 16 - 25)** | Handle any ASRT questions or corrections. | Deadline met |

**This gives 2+ weeks of buffer.** If timeline slips, rush fee buys 10-day turnaround.

## Zero External Dependency Tasks (Start Today)

| Task | Tool | Time |
|---|---|---|
| Install Claude Code on Mac | Terminal | 5 min |
| Create .env file with all credentials | Text editor | 10 min |
| Write CLAUDE.md for techcelerate-mono | This chat or Claude Code | 1 hr |
| UpdraftPlus → Google Drive backup | Claude in Chrome | 10 min |
| Run AI freshness audit on 4 courses | This chat (upload docs) | 2-4 hrs |
| Build ASRT compliance checker script | Claude Code | 4-6 hrs |
| Process 4 course Word docs → LearnDash HTML | Claude Code | 4-6 hrs |
| Generate post-test questions for 4 courses | Claude Code | 2-3 hrs |
| Create certificate template design | Claude Code | 2 hrs |
| Draft all 5 email sequence copy | This chat | 2 hrs |
| Create Stripe account | Browser | 15 min |
| Create AWS/SES account | Browser | 20 min |
| Cancel Asana | Browser | 2 min |
| Email Heidi Veillette re-contact | Email | 5 min |
| Get E&O insurance quotes | Phone/browser | 30 min |
| Register DMCA agent | copyright.gov | 10 min |

## Hidden Time Bombs

| Bomb | Why It's Dangerous | Mitigation |
|---|---|---|
| **LearnDash license expiry** | Showed July 2021 in docs. If expired, can't update or get support. Plugin works but no updates = security risk. | Verify license status in LearnDash → Settings → LMS License NOW |
| **Uncanny Owl All Access renewal** | Annual $499/yr. If lapsed, plugins won't activate. | Check account status at uncannywl.com before downloading .zips |
| **ASRT rejects AI content** | No written policy. If ASRT takes a stance against AI-generated content, entire pipeline is at risk. | Ask on call. If hostile, frame as "AI research assistant, human-authored." |
| **Subdomain migration breaks SEO** | Old URLs (radiology.techcelerate-ce.com/*) must 301 redirect to new paths. If not, any existing links/bookmarks break. | Install Redirection plugin. Map all old URLs. Test after migration. |
| **Dennis unavailability** | Dennis controls nginx and is the only person who can rebuild the server. No redundancy. | Document all server config. Consider Cloudways as hot-standby ($45/mo). |
| **Kadence child theme compatibility** | Child theme "Techcelerate CE for LearnDash" is from Learning Templates. After theme updates, child theme could break. | Test after every Kadence parent theme update. Keep UpdraftPlus backup current. |
| **WooCommerce removal breaks existing data** | WooCommerce created database tables. Removing plugin leaves orphan tables. WordPress still works but DB is messy. | Run `wp db query "SHOW TABLES LIKE '%woocommerce%'" --allow-root` after removal. Clean orphan tables. |
| **Multi-state sales tax** | Selling digital education across 50 states. Some states exempt CE, some don't. Non-compliance = back taxes + penalties. | Stripe Tax handles this automatically. Enable at launch. |
| **FERPA applicability** | CE transcripts may be considered educational records. If FERPA applies, data handling requirements increase. | Likely NOT FERPA-covered (professional CE, not K-12/higher ed). Confirm with attorney. |
| **PHP 8.3 compatibility** | Server was on PHP 7.4 until 3 days ago. Some plugins may have stored serialized data that breaks on PHP 8.3. | Run `wp db repair --allow-root` and check error logs after every major action. |
| **Email deliverability cold start** | New domain + new SES account = zero email reputation. First emails may land in spam. | Request SES production access early. Warm up domain with low-volume sends before launch blast. |

---

# SECTION 6: WHAT YOU DON'T KNOW THAT YOU SHOULD KNOW

## Technical Risks

1. **LearnDash 5.x is a major rewrite.** Version 5 rewrote significant parts of the plugin. Uncanny plugins designed for LearnDash 4.x may have compatibility issues. Test every Uncanny plugin against LearnDash 5.0.1.1 before going live.

2. **WP REST API rate limiting.** Claude Code will make hundreds of API calls to create courses, pages, quizzes. WordPress has no built-in rate limiting but the server might. If Claude Code hits 429 errors, add delays between calls.

3. **WordPress Multisite vs. Single-site.** Your current setup is single-site. If you ever need true multi-tenant (separate admin for each vertical), you'd need WordPress Multisite. This is a one-way migration — decide now if single-site is final. **Recommendation: stay single-site.** Subdirectories handle multi-vertical fine.

4. **LearnDash Groups + PMP integration.** This is the most complex piece — a membership purchase must auto-enroll the user in the correct LearnDash Group. PMP has a LearnDash integration plugin but it may need custom code. Test this early.

5. **Image optimization at scale.** 20 courses with clinical images. WebP format, lazy loading, proper alt text for accessibility. Claude Code should batch-convert all images during course loading.

## ASRT Accreditation Risks

6. **First-time sponsor scrutiny.** ASRT may review first-time General Sponsors more carefully. Your first batch sets the tone. Make it perfect.

7. **Clinical image permissions.** Many courses use published clinical images with "Reproduced for educational purposes only." ASRT may require explicit permission from original publishers. Review image sources in all 4 courses.

8. **Learning objectives must be measurable.** ASRT rejects vague objectives like "understand MRI." Use Bloom's taxonomy verbs: "explain," "identify," "compare," "analyze." AI can rewrite, but SME must validate.

9. **AMA 11th edition is strict.** Reference formatting must be exact. No issue numbers in journal citations. No access dates on website references. No periods at end of URLs. AI compliance checker must implement every rule.

## Business Risks

10. **340,000 RTs sounds like a big market, but conversion matters.** No existing competitor has cracked 2% penetration. The market is real but fragmented. Don't assume "if we build it, they will come." Marketing execution (not product quality) determines Year 1 success.

11. **Price may be TOO low.** At $39.99/yr, you're 58% below the cheapest unlimited competitor ($44.99 GetYourCEU). Some buyers equate low price with low quality. The founding tiers at $9.99-$19.99 are brilliant for acquisition but monitor whether standard-price conversion is harder because the anchoring is too low.

12. **Procrastination-driven demand.** Most RT CE purchases happen in the 30-60 days before biennium deadlines. Revenue will be extremely seasonal. Plan cash flow accordingly — don't panic if Month 1 is slow and Month 6 spikes.

13. **ASRT is both regulator and competitor.** ASRT sells its own CE ($125/yr membership includes 17 credits). They have mixed incentives to approve a platform that undercuts them on price. Be respectful in all interactions.

## Legal/Compliance Risks

14. **E&O insurance for AI content is a new category.** Many insurers don't have standard policies for AI-generated clinical education. You may need a specialized broker. Ask specifically about AI content coverage — some policies have explicit AI exclusions.

15. **FTC and AI personas.** The AI character program (Jasmine, Marcus, etc.) needs clear disclosure. FTC guidance on AI-generated personas is evolving. Current safe standard: clearly branded as "TechCElerate Learning Guides," not claiming to be real people. Do NOT fabricate credentials for AI characters — say "15 years experience" only if you're comfortable defending that the character represents aggregate expertise.

16. **Course content is copyrightable but AI authorship is gray.** Content authored by your contracted writers is clearly work-for-hire owned by Catalyst. AI-generated content has unsettled copyright status. Having a human SME review and approve creates stronger IP claims.

## Competitive Risks

17. **The social media gap won't last forever.** You correctly identified that no RT CE competitor has social media presence. Once you prove it works, competitors will copy within 6-12 months. Move fast, build community, make switching painful.

18. **AI content pipeline is replicable.** Your cost advantage (75-90% content production savings) comes from AI. Competitors can adopt the same approach. Your moat is: ASRT-approved library size, subscriber base, community, student pipeline, brand trust — not the production method.

19. **Large health systems may build their own.** If hospitals realize they can use AI to generate internal CE content, the B2B channel shrinks. Mitigated by: they still need ASRT accreditation, which is expensive and slow for each institution to obtain individually.

---

# SECTION 7: GEMINI REVIEW QUESTIONS (Answered from TechCElerate perspective)

## Top 5 Before ASRT Submission (Apr 25)
1. Course freshness audit (4 FINAL courses)
2. Post-test question generation (0 questions exist)
3. ASRT compliance checker (automated validation)
4. Certificate template (11 elements)
5. ASRT call to confirm 3-year approval + AI content policy

## Top 5 Before Launch (Jul 4)
1. Full plugin swap + configuration
2. Payment setup (Stripe + PMP + founding tiers)
3. Email automation (FluentCRM + SES + 5 sequences)
4. Site build (all pages, mobile-responsive, conversion-optimized)
5. Remaining course loading (20 courses total)

## Top 3 Things to NEVER Build
1. **Custom LMS from scratch.** LearnDash + Uncanny handles everything. Building custom wastes months.
2. **Mobile app.** Progressive web app (responsive site) serves mobile RTs perfectly. Native app adds App Store maintenance, review process, and development cost for zero CE delivery benefit.
3. **Community forum.** RTs already have Facebook groups with 10k-50k members. Building a forum creates a ghost town. Join existing communities instead.

## Single Most Differentiating Feature
**ARRT Credit Reporting Auto-Generator.** No competitor does this well. The moment a RT completes a course, they get a one-click pre-filled ARRT reporting package (copy-paste text + PDF + direct portal link + biennium tracker). This turns a 20-minute administrative chore into 30 seconds. It's zero-cost to build (uses existing LearnDash + Uncanny data) and creates massive switching friction.

## Biggest Untracked Risk to July 4 Launch
**Email deliverability cold start.** New domain (techcelerate-ce.com) + new SES account = zero sender reputation. Your founding member launch campaign emails could land in spam for 30-50% of recipients. Mitigation: request SES production access by April, start sending low-volume (free course signups, newsletter) in May to warm the domain, so July 4 blast has established reputation.

## Is the Pricing Right?
Yes, with one caveat: the $9.99 White tier locked forever creates a permanent drag on ARPU. Model shows it's fine at 250 subscribers, but if those 250 become your most vocal evangelists and every referral expects $9.99, you've anchored the perceived value too low. Consider: White tier price lock expires after 5 years (still an incredible deal — 5 years at $9.99).

## Is LearnDash the Right LMS?
**Yes, don't switch.** LearnDash is the market leader for WordPress LMS, has direct ASRT-compliant certificate support via Uncanny CE Credits, REST API for automation, and you already own 2 licenses with a working installation. Alternatives (Tutor LMS, LifterLMS, Teachable, Thinkific) would require starting over and losing the Uncanny ecosystem integration. The only scenario to switch is if LearnDash development stalls — but version 5 is a major active rewrite, so development is clearly ongoing.

---

# SECTION 8: CLAUDE.MD AND BUILD ORACLES

## Draft: `techcelerate-mono/CLAUDE.md`

```markdown
# TechCElerate Build — Claude Code Behavioral Contract
# Last updated: 2026-02-26
# Repo: techcelerate-mono

## SERVER ACCESS
- Read credentials from .env (NEVER hardcode passwords in scripts or commits)
- SSH: root@45.59.100.119
- WordPress radiology site: /var/www/html/radiology.techcelerate-ce.com/
- WordPress main site: /var/www/html/techcelerate-ce.com/
- WP-CLI: always use --allow-root flag
- Webmin: https://45.59.100.119:10000

## BOUNDARIES
- NEVER modify nginx configuration. Dennis (support@learning-templates.com) handles all nginx changes.
- ONLY work in /var/www/html/ directory. Do not touch other server directories.
- ALWAYS take UpdraftPlus backup before destructive operations (plugin removal, database changes).
- Commit to GitHub after each completed phase.

## WORDPRESS CONVENTIONS
- WP-CLI commands: always --allow-root
- REST API base: https://radiology.techcelerate-ce.com/wp-json/
- Authentication: Application Password for REST API calls
- File ownership: www-data:www-data for all WordPress files
- Permissions: 644 for files, 755 for directories

## BRAND STANDARDS
- Cyan Blue: #42A4D9 (RGB: 66, 164, 217)
- Navy Blue: #121531 (RGB: 18, 21, 49)
- H1: Playfair Display, Bold, Navy
- H2: Playfair Display, Regular, Navy
- H3: Montserrat Semi Bold, ALL CAPS, Cyan Blue
- Body: Montserrat Regular, 15pt, Navy
- Logo font: Zanna
- Tone: Innovative, Simple, Medical, Credible, Approachable, Intelligent, Sophisticated, Reliable
- Imagery: Warm environments, modern not sterile, diverse technicians, bright lighting, depth of field

## ASRT COMPLIANCE RULES
- Credit-to-word-count: 0.25 CE = 1,600 words minimum, scaling to 4.0 CE = 19,700 words
- Questions: 2 per 0.25 credits. ≥60% multiple choice (4 options, 1 correct)
- No "All of the above" / "None of the above" / "Both a and b"
- Negative wording (NOT, EXCEPT): uppercase, bold, italic
- References: AMA 11th edition. No issue numbers. No access dates on URLs. No period at end of URL.
- Certificate: 11 mandatory elements (see ASRT brief)
- Passing score: 75%

## PLUGIN TARGET STATE (Active)
sfwd-lms, kadence-blocks, kadence-blocks-pro, kadence-pro, kadence-reading-time,
uncanny-automator, uncanny-ce-credits, uncanny-owl-toolkit-pro, uncanny-groups,
fluentcrm-pro, fluent-forms-pro, fluentsmtp, paid-memberships-pro, rank-math-seo,
affiliatewp, updraftplus, wordfence, kadence-starter-templates (remove post-build)

## COURSE HTML STRUCTURE
- Each lesson: H2 title, body paragraphs (3-4 sentences max), Clinical Pearl callout boxes (cyan accent),
  Key Takeaways at end (3-5 bullets), reference superscripts linking to anchor list at bottom
- Images: WebP format, lazy loading, alt text, max-width 100%, centered
- Tables: responsive HTML (no horizontal scroll on mobile)
- "Quick Complete" single-page format for ≤1.0 credit courses

## ERROR HANDLING
- Two failed fix attempts on same component = rewrite, not a third attempt
- Log all errors to trace file: /home/claude/techcelerate-build-log.md
- On fatal error: stop, restore from UpdraftPlus backup, report to Lou

## BUILD PHASE ORACLES
See build spec for pass/fail definitions per phase.
```

---

# RECOMMENDED SPRINT SEQUENCE

## Week 1 (Feb 26 - Mar 4): Foundation + Content Prep

**Claude Code (Server):**
- Phase 0: Backup + security
- Phase 1: Plugin swap
- Phase 2: LearnDash configuration (partial — certificate template after Uncanny installed)

**Parallel (Lou + AI):**
- Upload 4 FINAL course docs → AI freshness audit
- Create Stripe account
- Create AWS + SES account (start 24-hr sandbox approval)
- Cancel Asana
- Email Heidi Veillette
- Get E&O insurance quotes
- Call/email ASRT (follow up on pending call)

## Week 2 (Mar 5 - 11): Course Processing

**Claude Code (Server):**
- Phase 7: Site build (pages — can run parallel with course work)
- Begin Phase 3: Course loading (start with 4 FINAL courses)

**Parallel (Lou + AI):**
- Medical Director reviews freshness audit findings
- AI generates post-test questions → Medical Director validates
- AI runs ASRT compliance checker on all 4 courses

## Week 3 (Mar 12 - 18): Payment + Email

**Claude Code (Server):**
- Phase 4: Payment setup (Stripe + PMP + founding tiers)
- Phase 5: Email automation (FluentCRM + SES + sequences)
- Phase 6: Certificate template

**Parallel:**
- Send certificate sample to approval@asrt.org
- Continue processing remaining courses (5-16)

## Week 4 (Mar 19 - 25): Polish + Submission Prep

**Claude Code (Server):**
- Phase 8: Automation wiring (Uncanny Automator triggers)
- Mobile testing and fixes
- Performance optimization (caching, image optimization)

**Parallel:**
- Build ASRT submission packets for 4 courses
- Final compliance check
- Dennis: nginx migration (subdomain → main site)

## Week 5-6 (Mar 26 - Apr 8): Testing + Submission

- End-to-end user journey testing (register → purchase → course → certificate → email)
- Beta testers (writer network, personal contacts)
- Fix issues
- Submit 4 courses to ASRT

## Week 7-10 (Apr 9 - May 15): ASRT Review Period + Soft Launch

- ASRT reviewing courses (up to 9 weeks)
- Continue loading remaining courses
- Soft launch site (~May 15)
- Free course + email list building begins
- Social media accounts created, first content posted

## Week 11-14 (May 16 - Jul 3): Pre-Launch Marketing

- Email list building: "Get notified when founding tiers open July 4"
- Free course funnel live
- Social media content (Case of the Week, CE tips)
- ASRT approval received (target: mid-June)
- Final testing and polish

## Week 15: 🎆 LAUNCH (July 4, 2026)

- Founding tiers go live
- Email blast to list
- Social media campaign
- Monitor systems under load

---

## WHAT STARTS TODAY

**Claude Code:** `npm install -g @anthropic-ai/claude-code` → `cd ~/Projects/techcelerate-mono` → `claude` → Phase 0 + Phase 1

**Lou:** Create Stripe account, Create SES account, Cancel Asana, Email Heidi, Get E&O quotes

**This Chat:** Upload 4 FINAL course docs for AI freshness audit

**Cowork:** Download plugin .zips from vendor accounts to ~/Projects/techcelerate-mono/plugins/
