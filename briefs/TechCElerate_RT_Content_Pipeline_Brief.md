# TechCElerate: Content Pipeline & Automation Brief — RT Launch Vertical
## Prepared: 2026-02-22
## Purpose: Drop this into the dedicated Content Pipeline chat as context
## Scope: RADIOLOGIC TECHNOLOGISTS (RT) — Launch Vertical Only
## Note: The pipeline ARCHITECTURE (Stages 1-8) is vertical-agnostic and will be reused for all future verticals. The course inventory, ASRT compliance rules, writer roster, and CQR mapping are RT-specific. When expanding, duplicate this brief and swap in the new vertical's accreditation body, compliance rules, SME roster, and content specifications.

---

## WHAT THIS CHAT NEEDS TO PRODUCE

1. **Course audit results** for all 20 existing drafts (freshness, compliance, completeness)
2. **AI-assisted content generation pipeline** — from topic selection to LMS-ready course
3. **ASRT compliance checker** — automated validation against all formatting/content rules
4. **SME review workflow** — "click approve" interface for licensed RT reviewers
5. **LMS packaging automation** — course content → LearnDash via API
6. **Course refresh monitoring** — automated flagging when clinical guidelines change

---

## EXISTING COURSE INVENTORY (20 Courses)

### Status Assessment
| ID | Topic | Writer | Latest Version | Status | Priority |
|----|-------|--------|---------------|--------|----------|
| RT_23001 | MS MRI Imaging | Heidi Veillette | v3 (Jun 2023) | **FINAL** — Ready for audit | HIGH |
| RT_23002 | Shielding | Kelli Haynes | Unknown | In development | MEDIUM |
| RT_23003 | Fluoroscopy Pediatrics | Jessyca Wagner | Unknown | In development | MEDIUM |
| RT_23004 | Dual Energy CT | Heidi Veillette | Unknown | In development | MEDIUM |
| RT_23005 | Geriatric Imaging | Kelli Haynes | v2 (May 2023) | Near-final — needs audit | HIGH |
| RT_23006 | Pediatric Imaging | Kelli Haynes | v2 (Jun 2023) | Near-final — needs audit | HIGH |
| RT_23007 | Forensic Radiology | Mark Bowes | Unknown | In development | LOW |
| RT_23008 | LDCT Lung Cancer | Jessyca Wagner | Unknown | In development | MEDIUM |
| RT_23009 | Rad Physics & Radiobiology | Kelli Haynes | v3 (Jul 2023) | **FINAL** — Ready for audit | HIGH |
| RT_23010 | Radiation Safety | Kelli Haynes | v2 (Jul 2023) | Near-final — needs audit | HIGH |
| RT_23011 | Mammography A&P | Heidi Veillette | Unknown | In development | MEDIUM |
| RT_23012 | Portable MRI Intro | Jessyca Wagner | Unknown | In development | LOW |
| RT_23013 | Prostate MRI | Heidi Veillette | Unknown | In development | MEDIUM |
| RT_23014 | Portable MRI Neuroimaging | Jessyca Wagner | Unknown | In development | LOW |
| RT_23015 | CT Stroke | Heidi Veillette | v1 (Sep 2023) | Early draft — needs work | MEDIUM |
| RT_23016 | Radiography Imaging & Acquisition | Heidi Veillette | FINAL | **FINAL** — Ready for audit | HIGH |
| RT_23017 | Neuroimaging AD-DMTs | Mark Bowes | Unknown | In development | LOW |
| RT_24001 | Liver Imaging | Heidi Veillette | Unknown | In development | MEDIUM |
| RT_24002 | Osteoporosis DEXA | Mark Bowes | Unknown | In development | LOW |
| RT_24003 | Chest Radiography | Heidi Veillette | FINAL (Mar 2024) | **FINAL** — Ready for audit | HIGH |

**Launch target**: 4-6 FINAL courses audited and submitted to ASRT first. Remaining courses completed via AI-assisted pipeline.

### Content Quality Benchmarks (from 3 sample courses reviewed)

**RT_24003 Chest Radiography** (Heidi Veillette, Mar 2024):
- 6 learning objectives, 6 major content sections
- 14+ MC questions with answer key
- Clinical images with reference citations
- Professional formatting, AMA style references
- Estimated 3.0 CE credits based on word count
- **Assessment: Publication-ready after freshness check**

**RT_23001 MS MRI** (Heidi Veillette, Jun 2023):
- 2,579 words, 0.5 credits
- 4 MC questions (minimum for 0.5 credit)
- Highlights box, learning objectives, AMA references
- **Assessment: Publication-ready after freshness check**

**RT_23009 Radiation Physics** (Kelli Haynes, Jul 2023):
- CQR-aligned (follows ARRT content specifications for Radiography SSA)
- Well-structured outline following official content specs
- 8+ post-test questions
- **Assessment: Publication-ready after freshness check**

---

## ASRT COMPLIANCE RULES (Automation Targets)

### Credit-to-Word-Count Table (from CatalystWriterProcedures_Techv2_052523.docx)
| Credits | Min Word Count | Min Post-Test Questions |
|---------|---------------|----------------------|
| 0.25 | 1,600 | 2 |
| 0.50 | 2,450 | 4 |
| 0.75 | 3,700 | 6 |
| 1.00 | 4,900 | 8 |
| 1.25 | 6,125 | 10 |
| 1.50 | 7,375 | 12 |
| 1.75 | 8,600 | 14 |
| 2.00 | 9,850 | 16 |
| 2.25 | 11,075 | 18 |
| 2.50 | 12,300 | 20 |
| 2.75 | 13,550 | 22 |
| 3.00 | 14,750 | 24 |
| 3.25 | 16,000 | 26 |
| 3.50 | 17,250 | 28 |
| 3.75 | 18,450 | 30 |
| 4.00 | 19,700 | 32 |

### Word Count Rules
**Included**: Main text, headings, sub-headings, in-text citations, tables, figures, charts, graphs, legends, footnotes, embedded interactive questions (not graded)
**Excluded**: Title page, table of contents, reference list, appendices, post-test questions (counted separately with 1.85x multiplier)

### Post-Test Question Rules
- 60% minimum must be multiple choice (4 options, 1 correct answer)
- Up to 10% each: true/false, matching, hotspot, fill-in-the-blank (40% max combined)
- Avoid: "All of the above," "None of the above," "Both a and b"
- Negative wording (NOT, EXCEPT) must be uppercase, bold, italic
- Positive emphasis (MOST, ALWAYS, TRUE) similarly highlighted
- All options must be plausible
- Correct answers linked to learning objectives

### Formatting Standards
- AMA 11th edition style
- No issue numbers in journal references
- Drop access dates from website references
- Check that URLs work
- No live URLs in references
- No period at end of URL (unless multiple references on same line)
- Key takeaways highlighted YELLOW in source doc
- Correct answers highlighted GREEN in source doc
- Calibri 11pt, single-spaced, 1" margins, 0pt before/after

### Required Course Components
1. Title and author with credentials
2. Outline
3. Learning objectives (linked to content and assessment)
4. Highlights box (3-4 key takeaways)
5. Main body text (evidence-based, fair-balanced)
6. Tables/figures with proper citations ("Reproduced for educational purposes only")
7. References (AMA 11th edition)
8. Post-test questions with answer key and LO mapping

---

## AI-ASSISTED CONTENT PIPELINE (Target Architecture)

### Stage 1: Topic Selection & Scoping
- **Input**: Topic from pipeline list (000_Topics to Develop folder), CQR content specifications, competitor gap analysis
- **AI task**: Generate course outline with learning objectives, estimated word count, credit value, CQR category mapping
- **Human task**: Approve topic and outline (click approve)
- **Automation level**: 90%

### Stage 2: Content Drafting
- **Input**: Approved outline, ARRT content specifications, current clinical guidelines, reference literature
- **AI task**: Generate full course draft with body text, highlights box, tables/figures descriptions, properly formatted AMA references
- **Human task**: None at this stage
- **Automation level**: 95%

### Stage 3: Compliance Check
- **Input**: AI-generated draft
- **AI task**: Automated validation against ALL ASRT rules:
  - Word count vs. credit value (Table 1 compliance)
  - Word count inclusion/exclusion rules (Table 2)
  - Post-test question count vs. credit value
  - Question type distribution (60% MC, 10% T/F, etc.)
  - Learning objective coverage (each LO addressed in content AND assessment)
  - Reference formatting (AMA 11th edition)
  - Required components present (outline, LOs, highlights, body, references, post-test)
- **Human task**: None
- **Automation level**: 100% (rule-based)

### Stage 4: Post-Test Generation
- **Input**: Completed course content
- **AI task**: Generate post-test questions with:
  - 4-option MC questions (60%+ of total)
  - Distractor analysis (all options plausible)
  - Answer key with learning objective mapping
  - Correct answer citations (location in course text)
  - Confidence scoring per question
- **Human task**: Review flagged low-confidence questions (click approve for high-confidence batch)
- **Automation level**: 85%

### Stage 5: SME Clinical Review
- **Input**: Complete course + post-test + compliance report
- **AI task**: Present in review dashboard with side-by-side: course content (left), compliance checklist + AI confidence scores (right)
- **Human task**: Licensed RT reads course, verifies clinical accuracy, approves or flags sections
- **Automation level**: 20% (this is the mandatory human step)
- **Target**: SME reviews 1 course in 2-4 hours, clicks "Approve" or highlights specific corrections

### Stage 6: Correction & Re-validation
- **Input**: SME feedback (highlighted corrections)
- **AI task**: Apply corrections, re-run compliance check, re-validate
- **Human task**: SME verifies corrections (quick re-review, typically 15-30 min)
- **Automation level**: 80%

### Stage 7: LMS Packaging
- **Input**: Approved course content
- **AI task**: Convert to LearnDash-compatible format:
  - Create course structure (lessons, topics)
  - Format content as HTML for block editor
  - Create quiz with question bank
  - Set passing score (75%)
  - Configure CE credit value
  - Generate certificate template data
  - Deploy to LearnDash via REST API
- **Human task**: Spot-check final rendering in staging
- **Automation level**: 95%

### Stage 8: ASRT Submission Preparation
- **Input**: LMS-packaged course
- **AI task**: Generate submission packet:
  - Pre-fill ASRT application form fields
  - Compile course description, LOs, faculty credentials
  - Generate Word version for ASRT review
  - Create test account credentials for ASRT reviewer access
  - Draft cover email
- **Human task**: Review packet, click "Send"
- **Automation level**: 70%

---

## WRITER/SME ROSTER

### Active Writers (Contracted)
| Writer | Credentials | Rate (1 CE) | Best Use in AI Pipeline |
|--------|------------|-------------|------------------------|
| Heidi Veillette | BSc, MRT(R)(MR), 17yr clinical | $2,500 | **Primary SME reviewer** — best value, excellent quality, RT credentials. Review rate: ~$200-500/course (2-4 hrs at $85/hr) |
| Kelli Haynes | Ed.D., RT(R), FASRT, FAEIRS | $2,000 | SME reviewer for education/CQR-aligned content. Fast turnaround. |
| Jessyca Wagner | RT(R), researcher, ASRT reviewer | $6,000 | High-value SME for complex clinical topics. ASRT editorial board experience adds credibility. |
| Mark Bowes | — | $6,000 | SME reviewer for specialized topics (forensic, neuro, DEXA). |

### Cost Comparison: Traditional vs. AI-Assisted
| Approach | Cost per 1-CE Course | Production Time | Annual Capacity |
|----------|---------------------|-----------------|-----------------|
| Traditional (writer drafts from scratch) | $2,000-$6,000 | 4-8 weeks | 12-20 courses/year |
| AI-assisted (AI drafts, SME reviews) | $250-$600 | 1-2 weeks | 50-100+ courses/year |
| **Savings** | **75-90%** | **75%** | **4-5x throughput** |

### Additional Writer Leads (from Writers.xlsx)
- Katie Faguy (former ASRT) — Lou reached out via LinkedIn 2/7/23
- Amanda Huynh (imaging: ultrasound, PET/CT, MRI) — emailed 3/27/23
- Kevin Clark (educator, editorial board member) — Lou reached out via LinkedIn 2/7/23
- Tara Rachinsky (Valence Biomed) — emailed 3/27/23
- ERAD contributors: Kim Mylan, George Tsoukatos, Steven Marks, Cheryl DuBose

---

## COURSE FRESHNESS AUDIT PROTOCOL

All 20 courses are 1-3 years old. Before publication, each needs:

1. **Clinical accuracy check**: Have guidelines, protocols, or equipment standards changed since the course was written?
2. **Reference validation**: Are all cited references still accessible? Any retracted? Any major new studies that should be included?
3. **Regulatory compliance**: Have ASRT/ARRT requirements changed since 2023?
4. **Statistics update**: Are prevalence/incidence figures still current?
5. **Technology update**: Has imaging technology advanced in ways that affect the content?

**AI can automate 80% of this**: Web search for guideline updates, reference URL checking, citation freshness scoring. SME validates the AI's findings.

---

## CONTENT EXPANSION STRATEGY

### Phase 1: Audit & Launch (20 existing courses)
- Freshness audit all 20 courses
- Prioritize 4-6 FINAL courses for immediate ASRT submission
- Complete "in development" courses via AI-assisted pipeline
- Target: All 20 courses published within 8 weeks

### Phase 2: AI-Generated Expansion (10-20 new courses)
- Topics from 000_Topics to Develop pipeline
- CQR-aligned content to fill gaps in ARRT content specifications
- Competitor gap analysis (topics covered by eRADIMAGING/GetYourCEU that we don't have)
- Target: 10-20 additional courses within 12 weeks

### Phase 3: Multi-Vertical Content (when second audience launches)
- Content overlap analysis (which RT courses translate to other verticals?)
- Vertical-specific content generation pipeline
- New SME recruitment per vertical

---

## AI COURSE UPDATE PIPELINE (Annual Refresh Cycle)

Keeps course library clinically current without traditional rewriting costs:

### Workflow
1. **Annual trigger** (or on-demand): Claude scans each course against current clinical guidelines, recent publications, equipment updates, regulatory changes
2. **Update Report generated** per course: what changed in the field, what needs revision, suggested new/replacement text, updated references
3. **SME reviewer** approves/edits updates (15-30 min per course vs. days for a full rewrite)
4. **Updated course pushed to LMS** via API
5. **ASRT re-review** submitted if changes are substantive (50% of original submission fee)

### Cost Comparison
| Approach | 20-Course Annual Update Cost | 50-Course Annual Update Cost |
|---|---|---|
| Traditional writers ($2,000-6,000/course) | $40,000-$120,000 | $100,000-$300,000 |
| AI pipeline + SME review ($150-300/course) | $3,000-$6,000 | $7,500-$15,000 |

### Triggers for Mandatory Update
- New clinical practice guidelines published (e.g., ACR updates)
- FDA equipment clearances or safety alerts
- State regulatory changes (CE requirement updates)
- ARRT content specification revisions
- Course older than 2 years without review
- Learner feedback indicating outdated content

---

## COURSE DESIGN PRINCIPLES (Speed-Optimized for Compliance-Driven Learners)

RTs want to check the box as fast as possible. Design for how they actually behave:

### Content Design
- **Clinical Pearl callout boxes**: Visually distinct (Cyan Blue accent), highlight key takeaways and testable content. Essentially signal "this might be on the test."
- **Key Takeaways summary** at end of each lesson: 3-5 bullet points previewing post-test topics for that section
- **Short paragraphs**: 3-4 sentences max. Generous white space. No wall-of-text.
- **Reference footnotes as hover/tap tooltips**: Superscript number → popup shows full reference. No scrolling to bottom. Keeps reading flow clean.
- **"Quick Complete" format for short courses** (0.5-1.0 credits): Single-page reading experience — all content on one scroll, quiz at the bottom. No clicking through 8 lessons for a 30-minute course.

### Quiz Design
- **Open-book quizzes**: Learners can reference material while taking the test
- **Attempt limits configurable per course/vertical**: RT = unlimited retakes. Other verticals may require max 3 attempts per their accreditation rules.
- **Inline "review material" links**: If someone fails, link them back to the relevant lesson section
- **Target: 80%+ first-attempt pass rate**: If most learners can't pass on first try, the course design is the problem, not the learner

### UX Design
- **Progress bar with time estimate**: "Lesson 3 of 6 — approximately 12 minutes remaining"
- **Mobile-first reading layout**: No horizontal scrolling on tables. Touch-friendly navigation.
- **Instant certificate**: The moment they pass the quiz, certificate generates, downloads, and emails. Zero waiting.
- **"Report My Credits" dashboard tool**: Auto-generates pre-filled ARRT reporting package (copy-pasteable text + PDF summary + direct link to ARRT portal)
- **Biennium countdown timer**: Dashboard widget showing days/credits remaining. iCal download for 90/60/30 day deadline reminders.

### Video (Phase 2 — Not Launch)
- Start text-only at launch. Text is faster to produce, update, and search.
- When video added: ESPN-style format — short video summary at top (5-10 min), full transcript below.
- Transcript IS the course; video is a bonus. Same content asset serves both formats.
- Variable playback speed (0.5x to 2x).
- Caption/subtitle support for accessibility.

---

## REFERENCE DOCUMENTS
- `TechCElerate_Master_Knowledge_Base.md` — canonical project reference
- `CatalystWriterProcedures_Techv2_052523.docx` — complete writer guidelines with credit/word count tables
- `CatalystEditorProcedures_Techv2_052423.docx` — editor style guide (AMA 11th edition)
- `CatalystInternalProcedures_Techv1_230317.docx` — internal workflow procedures
- `CE Approval Information_ASRT.docx` — ASRT pricing and certificate requirements
- `_ASRT Questions_230505.docx` — ASRT process intelligence from May 2023 call
- Sample courses: `Chest Radiography course FINAL Mar 06.docx`, `23001_MS_MRI_v3_060623_hv,lcs,jm.docx`, `RT_23009_RadBio_v3_070523_jm.docx`
