# TechCElerate Master Knowledge Base
## Last Updated: 2026-02-23 — ASRT sponsor type corrected (General Sponsor, not IP); Jan 2026 pricing verified; Catalyst fee locked
## Status: INGESTION COMPLETE — DECISIONS IN PROGRESS

---

## 1. ENTITY & INFRASTRUCTURE

### Legal / Financial
- **Entity exists**: PNC bank account set up (June 2023), verification letters on file
- **Domain**: techcelerate-ce.com (owned via Name.com)
- **Hosting**: Learning Templates (IP: 194.233.102.135) — nginx visible, WordPress-ready
- **Relationship to Catalyst**: Catalyst MedEd is the parent/operating entity. Catalyst email (subscription@catalystmeded.com) used for all plugin purchases. Writer contracts are "Catalyst Medical Education Consulting Agreements."

### Hosting Assessment
- **Provider**: Learning Templates (https://learning-templates.com/)
- **IP**: 194.233.102.135
- **Status**: Server shows nginx welcome page — WordPress not yet installed
- **⚠️ EVALUATE**: Learning Templates is a niche LearnDash hosting provider. Need to assess: performance specs, scalability, CDN, caching, auto-backups, staging environments, SSH/WP-CLI access (required for automation). Compare against Cloudways/Kinsta/GridPane for automation-first architecture.

---

## 2. TECH STACK (OWNED — CONFIRMED FROM SPREADSHEET)

### Core Stack (All Purchased, Most Lifetime Licenses)
| Plugin | Purpose | License Type | Purchase Date | Cost |
|--------|---------|-------------|---------------|------|
| LearnDash Plus + ProPanel | LMS | Annual ($160/yr) | 2020 | 2x 10-site licenses |
| Kadence WP Pro + Blocks Pro | Theme/Builder | Lifetime | Sep 2020 | $389 |
| Uncanny Owl All Access | CE Credits, Toolkit Pro, Groups, Codes, Tin Canny Reporting | Annual ($499/yr) | Nov 2020 | $499/yr |
| Uncanny Automator | Workflow Automation | Lifetime (Unlimited) | Sep 2020 | $599 |
| FluentCRM Pro | CRM | Lifetime | Oct 2020 | $599 |
| Fluent Forms Pro | Form Builder | Lifetime | Jun 2021 | $499 |
| AffiliateWP Ultimate | Affiliate Marketing | Lifetime | Nov 2020 | $559 |
| MonsterInsights Pro | Analytics | Annual ($799/yr) | — | $799/yr |
| WP Rocket | Caching | Annual ($180/yr) | Nov 2023 | $180/yr |
| Iubenda | Legal/Privacy | Annual | Nov 2020 | $159/yr |
| Social Ninja Pro | Social Media | Lifetime | Oct 2021 | $299 |
| Happy Scribe | Transcription | Subscription | — | $690 |
| Jasper (Jarvis) | AI Content | Subscription | — | — |
| MailChimp | Email Marketing | Monthly ($370/mo) | — | **⚠️ REDUNDANT with FluentCRM** |

### Evaluated But Not Purchased
| Plugin | Decision | Notes |
|--------|----------|-------|
| H5P | Undecided | Interactive content — evaluate necessity |
| BuddyBoss | No | Too heavy for CE platform |
| Elementor/Divi | No | Kadence selected |
| CartFlows | No | Evaluate PMP or native Stripe instead |
| HubSpot | No | FluentCRM selected |
| Gamification | Undecided | Evaluate for engagement |

### ⚠️ LICENSE RENEWAL STATUS UNKNOWN
- LearnDash licenses show expiry July 2021 — **NEED TO VERIFY CURRENT STATUS**
- MonsterInsights annual renewal — **VERIFY**
- Uncanny Owl annual renewal — **VERIFY**
- WP Rocket annual renewal — **VERIFY**
- Iubenda annual renewal — **VERIFY**

### 💰 COST SAVINGS OPPORTUNITY
- **MailChimp at $370/mo is completely redundant.** FluentCRM (lifetime, already owned) + Amazon SES ($0.10/1000 emails) replaces it entirely. **Savings: ~$4,440/year.**

---

## 3. CONTENT INVENTORY

### Courses Developed (20 total, RT focus)
| ID | Topic | Writer | Status | Credits |
|----|-------|--------|--------|---------|
| RT_23001 | MS MRI Imaging | Heidi Veillette | v3 FINAL (Jun 2023) | 0.5 |
| RT_23002 | Shielding | Kelli Haynes | In development | — |
| RT_23003 | Fluoroscopy Pediatrics | Jessyca Wagner | In development | — |
| RT_23004 | Dual Energy CT | Heidi Veillette | In development | — |
| RT_23005 | Geriatric Imaging | Kelli Haynes | v2 (May 2023) | — |
| RT_23006 | Pediatric Imaging | Kelli Haynes | v2 (Jun 2023) | — |
| RT_23007 | Forensic Radiology | Mark Bowes | In development | — |
| RT_23008 | LDCT Lung Cancer | Jessyca Wagner | In development | — |
| RT_23009 | Radiation Physics & Radiobiology | Kelli Haynes | v3 FINAL (Jul 2023) | — |
| RT_23010 | Radiation Safety | Kelli Haynes | v2 (Jul 2023) | — |
| RT_23011 | Mammography A&P | Heidi Veillette | In development | — |
| RT_23012 | Portable MRI Intro | Jessyca Wagner | In development | — |
| RT_23013 | Prostate MRI | Heidi Veillette | In development | — |
| RT_23014 | Portable MRI Neuroimaging | Jessyca Wagner | In development | — |
| RT_23015 | CT Stroke | Heidi Veillette | v1 (Sep 2023) | — |
| RT_23016 | Radiography Imaging & Acquisition | Heidi Veillette | FINAL | — |
| RT_23017 | Neuroimaging AD-DMTs | Mark Bowes | In development | — |
| RT_24001 | Liver Imaging | Heidi Veillette | In development | — |
| RT_24002 | Osteoporosis DEXA | Mark Bowes | In development | — |
| RT_24003 | Chest Radiography | Heidi Veillette | FINAL (Mar 2024) | 3.0 (est) |

Plus: `000_Topics to Develop (Tech_GSP)` folder exists — future pipeline topics already identified.

### Content Quality Assessment (from 3 sample courses)
**Chest Radiography (RT_24003)**: Professional quality. 6 learning objectives, structured outline with 6 major sections, 14+ MC questions, images with references. Author: Heidi Veillette, BSc, MRT(R)(MR). Adheres to ASRT format requirements.

**MS MRI (RT_23001)**: 2,579 words, 0.5 credits, 4 MC questions (minimum for 0.5 credit). Complete with highlights box, learning objectives, AMA-style references. Ready for submission.

**Radiation Physics (RT_23009)**: CQR-aligned content following ARRT content specifications for Radiography. Well-structured, follows SSA content outline. Post-test has 8+ questions.

**Overall**: Content is professional-grade, written by credentialed RTs and researchers. Formatting follows ASRT requirements. Some courses are 2+ years old and will need freshness review for clinical accuracy.

---

## 4. WRITER/SME PIPELINE

### Contracted Writers (Confirmed from Writers.xlsx + Contracts folder)
| Writer | Credentials | Rate (1 CE) | Quality | Speed | Contract Status |
|--------|------------|-------------|---------|-------|-----------------|
| Heidi Veillette | BSc, MRT(R)(MR), 17yr clinical | $2,500 | Excellent | 1/month | Signed (multiple SOWs) |
| Kelli Haynes | Ed.D., RT(R), FASRT, FAEIRS | $2,000 | Moderate-Good | Fast | Signed |
| Jessyca Wagner | RT(R), researcher, ASRT reviewer | $6,000 | Excellent | Medium | Signed |
| Mark Bowes | — | $6,000 | Excellent | Medium | Signed (W-9 on file) |

### Cost Economics
- **With existing writers**: $2,000-$6,000 per 1-credit course
- **With AI-assisted pipeline**: Estimated $250-$600 per course (AI drafts, SME reviews)
- **Automation savings**: 75-90% cost reduction per course

### Additional Writer Leads (from Writers.xlsx)
- Katie Faguy (former ASRT), Amanda Huynh (imaging specialist), Kevin Clark (educator), Tara Rachinsky, plus ERAD imaging contributors identified

---

## 5. ASRT ACCREDITATION (CRITICAL PATH)

### Sponsor Type: GENERAL SPONSOR (CONFIRMED — NOT IP)
**Institutional Provider (IP) is not applicable to TechCElerate.** IP is exclusively for hospitals/health care institutions providing CE to their own employees. TechCElerate is a commercial platform selling to external customers. Confirmed from prior ASRT call. No annual IP fee applies.

### Pricing (Verified Jan 1, 2026 — asrt.org)
**TechCElerate pays per-course self-learning fees only. No annual agreement fee.**

| Course Length | 1-Year | 2-Year | 3-Year |
|---|---|---|---|
| 0.25–3.25 hrs | $150 | $260 | $365 |
| 3.5–9.25 hrs | $300 | $520 | $730 |
| 9.5–15.75 hrs | $450 | $780 | $995 |
| 16–23.75 hrs | $600 | $1,040 | $1,260 |
| 24+ hrs | $750 | $1,300 | $1,520 |

*16hr+ and 24hr+ tiers added August 2024.*
**Model assumption**: $225/course blended average (conservative; most courses are 0.25–3.25 hrs at $150–$260).
**Recommendation**: Submit for 2-year approval on stable clinical content courses.

**Priority Handling (General Sponsor)**: 50% of total cost (not the $45 flat IP rate)
**Re-review Fee**: 50% of original cost

### Process Intelligence (from _ASRT Questions_230505.docx)
- **Contact**: 800-444-2778, Ext. 1906 (CE Approval dept, "Daniel" — verify still current)
- **Review timeline**: Up to 9 weeks (varies by volume)
- **Rush fee**: 10-day turnaround, 50% surcharge (expensive for General Sponsor — avoid)
- **Busy seasons**: Spring and Fall (universities in session)
- **Best time to submit**: Summer (slower volume)
- **Author requirements**: "Any writer is okay" — no credential requirement for author, just knowledge
- **Batch submissions**: Can submit multiple courses for staggered review but same launch date
- **Content licensing question raised**: "If content is already accredited, do we need separate review?" — UNANSWERED
- **⚠️ Submit by April 25, 2026** for 9-week review to clear before July 4 launch

### Certificate Requirements (11 mandatory elements):
1. Sponsor's name (as on Request for Approval)
2. Participant's name
3. Activity title (exact, from approval letter)
4. Reference number (preprinted, not handwritten)
5. Number of credits (preprinted)
6. Category (A or A+)
7. Approval statement: "Activity approved by ASRT."
8. Date completed (preprinted)
9. Signature of instructor or authorized rep
10. Participant's ASRT ID or unique identifier
11. Expiration date of CE activity

**Free certificate review**: Send final certificate to [email protected] for complimentary compliance check.

### ⚠️ STATUS: APPLICATION NOT YET SUBMITTED
- Sponsor type confirmed (General Sponsor, not IP)
- 2026 pricing verified from ASRT website
- Call still needed to ask: AI content policy, content licensing transfer question, confirm contact
- No courses submitted for ASRT approval
- Submit first batch (4 courses) by April 25, 2026

---

## 6. OPERATIONAL PROCEDURES (DOCUMENTED)

### Writer Procedures (CatalystWriterProcedures_Techv2_052523.docx)
- Complete credit-to-word-count table (0.25 CE = 1,600 words through 4.0 CE = 19,700 words)
- Question minimums per credit (2 questions per 0.25 credits, scaling up)
- Question format rules: 60% MC required, 10% each T/F, matching, hotspot, fill-in-blank
- AMA style formatting required
- Correct answers highlighted GREEN, key takeaways highlighted YELLOW
- Cross-referencing via Microsoft Word endnotes

### Editor Procedures (CatalystEditorProcedures_Techv2_052423.docx)
- Full style guide: AMA 11th edition
- Number formatting, abbreviation rules, reference formatting
- Image permission language: "Reproduced for educational purposes only"
- Tracked changes required for all content edits

### Internal Procedures (CatalystInternalProcedures_Techv1_230317.docx)
- Channel naming: YY###_YYMMDD_Topic_mm_Writer
- Kick-off procedures, content review checklist, ASRT compliance verification
- Word count checking, question type/count verification, formatting standards

### Laura Notes (Production/Posting Guidance)
- Tables/figures need production work (redrawing, adding titles/footnotes)
- ASRT needs to review posted content (test link, username, password required)
- Word version of course needed for ASRT review
- Key questions about LMS content formatting still open

---

## 7. WEBSITE ARCHITECTURE (PLANNED)

### Domain Structure
- **Main**: techcelerate-ce.com
- **RT subdomain**: radiology.techcelerate-ce.com
- **Future**: [profession].techcelerate-ce.com for each vertical

### Planned Pages
- Home (hero + course grid + CTA)
- CE Courses (filterable grid, searchable)
- Membership (funnel page, Free Course Friday concept)
- About
- Blog (deferred — evaluate for SEO)
- FAQs (minimize support calls, email-only support)
- Account/Dashboard

### Site Copy
- Detailed copy drafted for all pages (in WebDev docs)
- Brand positioning: "Accelerating learning for medical techs"
- RT-specific: "Accelerating learning for radiologic technologists"
- Key messaging: ASRT approved, ARRT® renewal accepted, CQR-applicable

### Competitor Sites Referenced
- eradimaging.com, scrubsce.com, gagece.com, fastcecredits.com, xrayce.com, x-raylady.com

---

## 8. MARKET SEGMENTS RESEARCHED (from directory structure)

### Active Research (folders with content)
| Segment | Folder | Research Depth |
|---------|--------|---------------|
| Radiologic Technologists | RT_Articles/ + 03_CE_ASRT/ | Deep — 20 courses, contracts, ASRT process |
| Medical Assistants | _Segments/111 - Medical Assistants/ | BLS data collected |
| Dental Hygienists | _Segments/Dental Hygenists/ | CE requirements by state, ADHA membership info, program data |
| Pharmacy Technicians | _Segments/Pharmacy Techs/ | Basic research |
| Home Health Aides/CNAs | _Segments/Home Health Aids/ | Extensive — pricing, CE requirements, state-by-state, competitor research |
| Respiratory Therapists | _Segments/999 - Respiratory Therapists/ | AARC info, CRCE requirements, competitor research |

### Deprioritized/Exploratory (marked "999")
- PT/OT (tuition-based, different model)
- Vet Techs (tuition-based)
- Employee Education
- Medical Cannabis (interesting but tangential)
- New Tech AI/Blockchain (tangential)

### BLS Data Downloaded
- Full occupational employment statistics (2018 vintage — **NEEDS UPDATE**)

---

## 9. OPEN QUESTIONS / BLOCKERS

### Critical (blocks launch)
1. **ASRT application status** — not submitted
2. **License renewal status** — LearnDash, Uncanny, MonsterInsights, WP Rocket all may be expired
3. **Hosting evaluation** — Learning Templates capabilities unknown for automation requirements
4. **Pricing decision** — $19 vs $49-59 not locked
5. **SME availability** — writers contracted but status of relationships after 2+ year gap unknown

### Important (blocks optimization)
6. **Course freshness audit** — 20 courses need clinical accuracy review (2-3 years old)
7. **WordPress not installed** — server shows nginx only
8. **Payment processor** — Stripe vs WooCommerce vs PMP not decided
9. **Multi-state sales tax** — not addressed
10. **E&O insurance** — not mentioned in any documents

### Strategic (blocks scaling)
11. **Vertical expansion order** — no decision beyond "RT first"
12. **B2B/enterprise channel** — identified but not developed
13. **Content licensing** — ASRT question about licensing pre-approved content unanswered

---

## 10. PRICING & LAUNCH DECISIONS (LOCKED)

### Subscription Model
- **Annual only** at launch. No monthly option (biennium cycle aligns to annual).
- **Per-course** option deferred to Phase 2.

### Red / White / Blue Founding Member Campaign (July 4, 2026 Launch)
| Tier | Name | Price | Cap | Lock |
|------|------|-------|-----|------|
| 🔴 Red | Founders for Life | $250 one-time | 250 | Lifetime |
| ⚪ White | Independence Rate | $9.99/yr | 250 | Locked forever |
| 🔵 Blue | Patriot Rate | $19.99/yr | 250 | Locked 2 years |

- **Soft launch**: ~May 15, 2026 (site live, beta testing)
- **Email list building**: June 1+ (free course lead magnet live)
- **Founding tiers open**: July 4, 2026
- **Post-founding**: $25/yr through Dec 31, 2026 ("250th Birthday Extended")
- **Standard pricing**: $39.99/yr from Jan 1, 2027

### Other Pricing Decisions
- **Free tier**: One permanently free 1-credit course (always available). "Free Course Friday" retired.
- **Students/new grads**: Free Year 1 (.edu email or graduation within 12 months)
- **Refund policy**: 7-day / 2-course-completion cap. Fully automated via Stripe.
- **Referral**: Friend 50% off Year 1, referrer $5 credit. Managed via AffiliateWP.
- **Affiliate**: 20-30% commission. RT faculty, department leads, influencers.
- **B2B pricing**: Deferred to Phase 2.

### Revenue Goals (from Financial Model v2)
| Year | Scenario | Revenue | Op. Income |
|------|----------|---------|------------|
| Y1 (6 mo) | Mid (Operating Plan) | $74k | $27k |
| Y2 | Mid | $92k | $32k |
| Y3 | Mid | $220k | $95k |

---

## 11. STUDENT & NEW GRAD PIPELINE (DECIDED — HIGH PRIORITY)

### Market Size
- ~14,000 new RTs enter workforce annually from ~680 JRCERT-accredited programs
- Zero platform loyalty at credential — first-mover wins 40-year relationship

### Unit Economics
- Student LTV:CAC = **13.3x** vs. 6.3x standard acquisition
- CAC ~$20 (mostly organic/viral) vs. ~$35 standard; annual churn 15% vs. 18%

### Funnel
1. **ARRT Registry Exam Prep Tool** — free practice questions, email gate. Repurposes existing post-test banks. CRM tags as `student-exam-prep`.
2. **Free Year 1** — full platform access for .edu or new grads within 12 months of graduation
3. **Year 2 Paid Conversion** — 28% target. 3-email sequence at 11-month mark.

### Viral Mechanics
- RT programs are tight cohorts. 2.5 referrals/student assumed.
- "Share with your cohort" = referrer gets 3 extra months free
- LinkedIn: target new ARRT credential announcements with congratulations + free year link
- Faculty partnerships: free final-semester access → faculty assigns → entire cohort loyalty

### 5-Year Projections (Financial Model v2, Student Pipeline tab)
- 495 free students acquired H2 2026; 990/year from 2027
- 735 cumulative paying converted students by 2030 → $29k/yr from this channel

---

## 12. AI LEARNING CHARACTERS (DECIDED — PHASE 1 BUILD)

### Concept
3-4 AI-generated RT characters narrating courses, presenting cases on social, and serving as the consistent face of TechCElerate. Chosen content (not interruption). No competitor is doing this.

### Character Roster
| Character | Profile | Primary Role |
|-----------|---------|-------------|
| **Jasmine** | Mid-career female RT, 38, MRI specialist, 15 yrs, multicultural | Lead — courses, email voice, social Case of Week |
| **Marcus** | Male RT, 26, 3 yrs in, radiography + CT | Exam prep mascot, new grad content |
| **Dr. Patricia Chen** | Senior RT educator, 54, former ASRT board | Complex clinical/CQR, B2B positioning |
| **Zoe** (Phase 2) | Specialty RT, interventional/nuclear medicine | Subspecialty courses |

### Disclosure Standard
"TechCElerate Learning Guides." Clearly branded, not claiming to be real people. No need to lead with "this is AI."

### Pipeline
Claude API script → HeyGen/Synthesia AI avatar → Wave.video (owned) editing → deploy. Cost: ~$5-20/video.

### Launch Sequence
Build Jasmine first → test in RT Facebook groups ("Case of the Week") → 30-day engagement test → Marcus before July 4 launch → full roster Q1 2027.

---

## 13. COMPETITIVE INTELLIGENCE (MARKET SCALE)

### Competitor Subscriber Estimates (Feb 2026)
| Competitor | Est. Active Subs | Est. Annual Revenue |
|------------|-----------------|---------------------|
| X-RayCE | 3,000-5,000 | $180k-300k |
| TakeCE (per-course) | 18,000+/yr | $600k-900k |
| GetYourCEU | 4,000-6,000 | $180k-270k |
| Medical Professionals | 5,000-8,000 | $250k-400k |
| eRADIMAGING | 3,000-6,000 | $165k-330k |

Market insight: Nobody has cracked scale. Best subscription players at 1-2% penetration of 340k market. Enormous ceiling.

### Social Media Gap (UNCONTESTED)
All major competitors effectively invisible on social. RT community highly active on Facebook (groups 10k-50k+ members), Reddit, Instagram. First brand to own this channel owns organic CAC at near-zero cost.

---

## 14. SUBSCRIPTION AUDIT & COST DECISIONS

### Immediate Cancellations
| Subscription | Annual Cost | Deadline |
|-------------|-------------|----------|
| Jasper.AI | $1,188/yr | Before Feb 28, 2026 |
| Asana | $324/yr | Immediately |
| MailChimp | $4,440/yr | After FluentCRM + SES configured |

**Total identified savings: ~$5,952/yr**

### At Renewal
- LearnDash Legacy duplicate: Cancel at Nov 2026 renewal
- Dropbox: Evaluate vs. Google Workspace Drive consolidation

### Catalyst Management Fee (LOCKED — 2026-02-23)
- **Tiered**: $0/mo until $5k MRR → $1,500/mo at $5k MRR → $2,500/mo at $15k MRR
- Catalyst is profitable parent entity; fee adjustable as needed
- Modeled in financial model as $18k-$30k/yr at steady state

### Licenses Verified Active
- Uncanny Owl All Access: Active (renewed)
- LearnDash Plus: Active on primary license (verify secondary)
