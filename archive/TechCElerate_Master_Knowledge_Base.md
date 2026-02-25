# TechCElerate Master Knowledge Base
## Last Updated: 2026-02-22
## Status: INGESTION COMPLETE — PENDING DECISIONS

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

### Pricing Confirmed (from CE Approval Information_ASRT.docx)
**Institutional Provider Agreement (recommended):**
- 1-year: $325 (1-12 submissions), $500 (13-24), $750 (25+)
- 2-year: $600 (1-12), $950 (13-24), $1,400 (25+)

**Per-Activity Self-Learning Costs:**
- 0.25-3.25 hrs: $150/yr, $260/2yr, $365/3yr
- 3.5-9.25 hrs: $300/yr, $520/2yr, $730/3yr
- 9.5+ hrs: $450/yr, $780/2yr, $995/3yr

**Priority Handling**: IPs: $45/lecture; Others: 50% of total
**Re-review Fee**: 50% of original cost

### Process Intelligence (from _ASRT Questions_230505.docx)
- **Contact**: 800-444-2778, Ext. 1906 (CE Approval dept, "Daniel")
- **Review timeline**: Up to 9 weeks (varies by volume)
- **Rush fee**: 10-day turnaround, 50% surcharge
- **Busy seasons**: Spring and Fall (universities in session)
- **Best time to submit**: Summer (slower volume)
- **Author requirements**: "Any writer is okay" — no credential requirement for author, just knowledge
- **Batch submissions**: Can submit multiple courses for staggered review but same launch date
- **Content licensing question raised**: "If content is already accredited, do we need separate review?" — UNANSWERED

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

### ⚠️ STATUS: APPLICATION NOT YET SUBMITTED
- Lou has researched the process thoroughly
- Contact has been made with ASRT (Daniel, May 2023)
- No evidence of submitted application in file inventory

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
