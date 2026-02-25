# TechCElerate Command Post Dashboard
## Updated: February 24, 2026 — 7:30 AM EST
## Days to July 4 Launch: **130 days**
## Days to ASRT Submission Deadline (Apr 25): **60 days**

---

## 🚦 PROJECT STATUS: ON TRACK (with blockers)

---

## CRITICAL PATH TIMELINE

```
TODAY ──────── Mar 15 ──────── Apr 25 ──────── May 15 ──────── Jun 1 ──────── Jul 4
  │               │               │               │              │              │
  ▼               ▼               ▼               ▼              ▼              ▼
Platform      ASRT Call      ASRT Submit     Soft Launch     Email List    🎆 LAUNCH
Cleanup       + Entity       4-6 Courses     Site Live       Building      Founding
Started       Setup          for Review      Beta Test       Free Course   Tiers Open
```

---

## WORKSTREAM STATUS

### 1. 🔴 PLATFORM & WEBSITE BUILD — IN PROGRESS
| Item | Status | Owner | Blocker? |
|---|---|---|---|
| WordPress installed (radiology subdomain) | ✅ Done | Dennis | — |
| PHP 8.3 upgrade | ✅ Done (Feb 23) | Dennis | — |
| LearnDash + Kadence installed | ✅ Done | Dennis/Doug | — |
| MS MRI course loaded (proof of concept) | ✅ Done | Doug | — |
| Brand colors/fonts/logo in Kadence | ✅ Done | Doug | — |
| Site audit (Claude in Chrome) | ✅ Done (Feb 24) | Claude | — |
| Plugin cleanup pass | 🔄 Running now | Claude in Chrome | — |
| SSH/cPanel access | 🔴 **BLOCKED** | Dennis/Doug | Firewall IP whitelist needed |
| Subdomain → subdirectory migration | 🔴 **BLOCKED** | — | Needs SSH |
| Plugin installs (Uncanny, FluentCRM, etc.) | 🔴 **BLOCKED** | — | Needs SSH or wp-admin upload |
| LearnDash 5.x update | 🟡 Attempting now | Claude in Chrome | May need license key |
| Stripe + PMP setup | ⬜ Not started | — | Needs pricing locked |
| FluentCRM + SES email setup | ⬜ Not started | — | Needs SSH + SES account |
| Certificate template (ASRT 11 elements) | ⬜ Not started | — | Needs Uncanny CE Credits |
| Full page build (landing, pricing, courses) | ⬜ Not started | — | Needs SSH for Claude Code |
| Course content loading (20 courses) | ⬜ Not started | — | Needs content audit first |

**Next action:** Get SSH credentials from Dennis or Doug. Email sent to both.

---

### 2. ✅ PRICING & UNIT ECONOMICS — LOCKED
| Decision | Status | Detail |
|---|---|---|
| Subscription model | ✅ Locked | Annual only at launch |
| Red tier (Founders for Life) | ✅ Locked | $250 one-time, 250 cap, lifetime |
| White tier (Independence Rate) | ✅ Locked | $9.99/yr, 250 cap, locked forever |
| Blue tier (Patriot Rate) | ✅ Locked | $19.99/yr, 250 cap, locked 2 years |
| 250th Birthday Extended | ✅ Locked | $25/yr through Dec 31, 2026 |
| Standard pricing | ✅ Locked | $39.99/yr from Jan 1, 2027 |
| Free tier | ✅ Locked | 1 permanently free course |
| Student/new grad | ✅ Locked | Free Year 1 (.edu or <12 mo grad) |
| Refund policy | ✅ Locked | 7-day / 2-course cap, auto via Stripe |
| Referral program | ✅ Locked | 50% off Year 1 for friend, $5 credit referrer |
| Affiliate program | ✅ Locked | 20-30% commission via AffiliateWP |
| Financial model v2 | ✅ Complete | Mid scenario: Y1 $74k, Y2 $92k, Y3 $220k |

**No open items.** Pricing feeds into Platform Build (checkout config) and Marketing (messaging).

---

### 3. 🟡 ASRT ACCREDITATION — CRITICAL PATH
| Item | Status | Deadline | Detail |
|---|---|---|---|
| Sponsor type confirmed | ✅ Done | — | General Sponsor (not IP) |
| 2026 pricing verified | ✅ Done | — | $150-$750/course, $225 blended avg |
| ASRT call prep doc | ✅ Done | — | 6 questions ready |
| ASRT call scheduled | 🔴 **NOT DONE** | ASAP | Call 800-444-2778 ext 1906 |
| Application submitted | 🔴 **NOT DONE** | **Apr 25** | 9-week review = Jul 4 approval |
| First batch (4 courses) submitted | ⬜ Not started | Apr 25 | RT_24003, RT_23001, RT_23009, RT_23016 |
| Course freshness audit | ⬜ Not started | Mar 15 | 4 FINAL courses need clinical review |
| Certificate template built | ⬜ Not started | Apr 15 | 11 ASRT-required elements |
| ASRT certificate review | ⬜ Not started | Apr 20 | Free review: approval@asrt.org |

**ASRT Call Questions (6):**
1. Confirm General Sponsor is correct category
2. AI-generated content policy?
3. Content licensing/transfer from prior sponsor?
4. Volume discounts for 10+ courses/year?
5. Batch submission process?
6. Platform review requirements?

**Next action:** Call ASRT this week. This is the #1 timeline risk.

---

### 4. 🟡 CONTENT PIPELINE — READY TO START
| Item | Status | Detail |
|---|---|---|
| Course inventory documented | ✅ Done | 20 courses: 4 FINAL, 4 near-final, 12 in dev |
| Writer roster confirmed | ✅ Done | 4 writers contracted (Heidi, Kelli, Jessyca, Mark) |
| AI pipeline architecture designed | ✅ Done | 8-stage pipeline, 75-90% cost reduction |
| ASRT compliance rules documented | ✅ Done | Credit/word count table, question rules, formatting |
| Course freshness audit | ⬜ Not started | 4 FINAL courses need clinical accuracy check |
| SME re-contact | ⬜ Not started | 2+ year gap — need to confirm availability |
| AI compliance checker built | ⬜ Not started | Automated ASRT rule validation |
| Post-test generation | ⬜ Not started | 0 quizzes, 0 questions currently in LearnDash |

**Priority courses for launch:**

| Course | Writer | Status | Est. Credits |
|---|---|---|---|
| RT_24003 Chest Radiography | Heidi Veillette | FINAL (Mar 2024) | 3.0 |
| RT_23001 MS MRI Imaging | Heidi Veillette | FINAL (Jun 2023) | 0.5 |
| RT_23009 Radiation Physics | Kelli Haynes | FINAL (Jul 2023) | TBD |
| RT_23016 Radiography Imaging | Heidi Veillette | FINAL | TBD |

**Next action:** Re-contact Heidi Veillette first (best value, highest quality).

---

### 5. ⬜ MARKETING & GROWTH — PLANNED (Not Started)
| Item | Status | Detail |
|---|---|---|
| Marketing strategy designed | ✅ Done | Full brief with email sequences, social, SEO, paid |
| AI character roster designed | ✅ Done | Jasmine (lead), Marcus (student), Dr. Chen, Zoe |
| FluentCRM configured | ⬜ Not started | Needs plugin install |
| Email sequences built | ⬜ Not started | 5 sequences designed (welcome, onboard, completion, renewal, biennium) |
| Social media accounts created | ⬜ Not started | Facebook, Instagram, LinkedIn, TikTok |
| SEO (Rank Math) configured | ⬜ Not started | Needs plugin install |
| Affiliate program (AffiliateWP) configured | ⬜ Not started | Needs plugin install |
| Paid ads | ⬜ Not started | Phase 3+ (after organic foundation) |

**Next action:** Starts after platform build + pricing are live. ~April timeframe.

---

### 6. 🟡 LEGAL, TAX & INSURANCE — OPEN
| Item | Status | Detail |
|---|---|---|
| Entity confirmed | ✅ Done | Catalyst Medical Education, LLC |
| PNC bank account | ✅ Done | Established June 2023 |
| Jasper AI canceled | ✅ Done | $1,188/yr saved |
| MailChimp cancellation | 🟡 Pending | Cancel after FluentCRM + SES configured ($4,440/yr savings) |
| E&O insurance | 🔴 **NOT STARTED** | Get quotes ASAP — don't launch without this |
| Entity structure review | ⬜ Not started | Catalyst vs TechCElerate liability isolation |
| Multi-state sales tax | ⬜ Not started | Stripe Tax recommended ($0.245/txn) |
| Writer contracts updated | ⬜ Not started | Need AI pipeline SME reviewer terms |
| Terms of Service | ⬜ Not started | CE-specific provisions needed |

**Next action:** Get E&O insurance quotes this week.

---

### 7. ⬜ B2B / ENTERPRISE — DEFERRED (Phase 2)
Planned but not starting until DTC launch is stable. Brief complete.

---

## ACTIVE BLOCKERS

| # | Blocker | Impact | Owner | ETA |
|---|---|---|---|---|
| 1 | **SSH/cPanel access** | Blocks Claude Code build, plugin installs, migration | Dennis or Doug | Waiting on email reply |
| 2 | **ASRT call not made** | Blocks course submission, April 25 deadline at risk | Lou | This week |
| 3 | **SME writers not re-contacted** | Blocks content audit, course freshness review | Lou | This week |
| 4 | **E&O insurance not started** | Blocks launch (liability risk) | Lou | This week |

---

## COMPLETED MILESTONES (Last 72 Hours)

| Date | Milestone |
|---|---|
| Feb 22 | Full project data ingestion (749 files, 1.5GB analyzed) |
| Feb 22 | 7 workstream briefs created and loaded to project |
| Feb 22 | Master Knowledge Base + Chat Index created |
| Feb 22 | Competitive landscape mapped (10 RT CE providers) |
| Feb 22 | All pricing tiers locked (Red/White/Blue + standard) |
| Feb 22 | Financial Model v2 completed |
| Feb 23 | ASRT sponsor type corrected (General Sponsor, not IP) |
| Feb 23 | ASRT Call Prep doc created (6 questions) |
| Feb 23 | Jasper AI canceled ($1,188/yr saved) |
| Feb 23 | July 4 = LAUNCH day (not close day) — timeline restructured |
| Feb 23 | Catalyst management fee locked (tiered: $0/$1.5k/$2.5k/mo) |
| Feb 23 | PHP 8.3 upgrade completed (Dennis) |
| Feb 23 | Server confirmed: separate WP installs for main + radiology |
| Feb 24 | Full wp-admin audit completed (Claude in Chrome, 207 steps) |
| Feb 24 | Plugin cleanup pass launched (Claude in Chrome) |
| Feb 24 | SSH/cPanel requests sent to Dennis + Doug |

---

## COST SAVINGS IDENTIFIED

| Item | Annual Savings | Status |
|---|---|---|
| Jasper AI cancellation | $1,188/yr | ✅ Done |
| MailChimp → FluentCRM + SES | $4,440/yr | 🟡 Cancel after FluentCRM configured |
| Asana cancellation | $324/yr | ⬜ Cancel now |
| ASRT IP fee removed (was never applicable) | $450/yr | ✅ Removed from model |
| **Total identified savings** | **$6,402/yr** | |

---

## THIS WEEK'S PRIORITIES (Feb 24-28)

| Priority | Task | Status |
|---|---|---|
| 1 | Get SSH access (Dennis/Doug response) | Waiting |
| 2 | Claude in Chrome: plugin cleanup pass | Running now |
| 3 | Call ASRT (800-444-2778 x1906) | **Do this today or tomorrow** |
| 4 | Email Heidi Veillette (SME re-contact) | Not started |
| 5 | Get E&O insurance quotes (Hartford, Hiscox) | Not started |
| 6 | Cancel Asana subscription | Not started |
| 7 | Once SSH received: Claude Code full build begins | Blocked |

---

## FINANCIAL SNAPSHOT

| Metric | Value |
|---|---|
| Platform fixed costs (annual) | ~$2,300/yr (after savings) |
| Catalyst management fee | $0/mo until $5k MRR |
| First batch ASRT submission | ~$1,040 (4 × $260 at 2-year) |
| Year 1 content investment | ~$15,000-$25,000 |
| **Y1 Revenue (Mid, 6 mo)** | **$74,000** |
| **Y1 Operating Income (Mid)** | **$27,000 (36.5% margin)** |
| Break-even subscribers (at $39.99) | 96 |
| Target market | 340,000+ ARRT-registered RTs |
| Market penetration needed | 0.19% |
