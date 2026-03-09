# TECHCELERATE ACCREDITATION SCOUT
## Allied Health CE Market Map & Expansion Strategy
**Created:** 2026-03-01 | **Status:** Strategic exploration

---

## THE ACCREDITATION LANDSCAPE: WHY IT MATTERS

Physician CME has ONE accreditor (ACCME), ONE credit type (AMA PRA Category 1), and relatively uniform rules. Allied health CE has DOZENS of accreditors, credentialing bodies, and state regulators that overlap, conflict, and create confusion. This fragmentation is TechCelerate's advantage — a unified platform that navigates the maze is enormously valuable.

**For each market below, the Scout answers:**
- How many professionals? (= total addressable learners)
- What CE is required? (= guaranteed demand)
- Who accredits CE providers? (= who TechCelerate needs approval from)
- How hard is that approval? (= barrier to entry)
- Who are the existing CE competitors? (= competitive density)
- What's the market trajectory? (= growing or shrinking)
- What data sources feed the intelligence? (= what to scrape/API)

---

## TIER 1: DAY 1 MARKET (Already pursuing)

### Radiologic Technologists (RTs)

| Metric | Data |
|--------|------|
| **Total professionals** | ~216,000 (BLS) |
| **CE requirement** | 24 credits/biennium (ARRT) |
| **Annual CE credits consumed** | ~2.6 million |
| **Credentialing body** | ARRT (American Registry of Radiologic Technologists) |
| **CE approval body** | ASRT (American Society of Radiologic Technologists) |
| **TechCelerate status** | ASRT accreditation submission deadline April 25, 2026 |
| **State variations** | Yes — FL, CA, TX, IL, KY, OR have additional requirements |
| **Vacancy rate** | 18.1% (critical) |
| **Job growth** | 5% (2024-2034), ~15,400 openings/year |
| **Median salary** | $77,660 |
| **Key competitors** | ASRT itself (500+ courses), eRadImaging ($54.95/yr), Pulse Radiology (acquired by Edcetera), CE4RT, X-Ray CE |
| **Market gap** | AI education (84.5% say important, 23.7% teach it), simulation-based learning, specialty pathways |

**Data sources to scrape/API:**
- BLS OES data by state/metro (employment, wages, projections)
- ARRT credential database (aggregate modality counts)
- ASRT enrollment snapshots (annual)
- JRCERT program directory (education programs by state)
- State licensing board databases (state-specific CE rules)
- Indeed/LinkedIn (RT job postings by location/specialty/salary)

**Sub-specialties within RT (each requires separate CE):**
- Radiography (R) — base credential, largest population
- CT (Computed Tomography) — post-primary certification
- MRI (Magnetic Resonance Imaging) — separate credential path
- Mammography — MQSA federal requirements on top of ARRT
- Nuclear Medicine (N) — separate primary credential
- Radiation Therapy (T) — separate primary credential
- Bone Densitometry (BD) — post-primary
- Vascular Interventional Radiography (VI) — post-primary
- Cardiac Interventional Radiography (CI) — post-primary
- Quality Management (QM) — post-primary

Each sub-specialty = separate CE content track on TechCelerate.

---

## TIER 2: ADJACENT MARKETS (Same or overlapping accreditation)

### Diagnostic Medical Sonographers

| Metric | Data |
|--------|------|
| **Total professionals** | ~85,000 (BLS) |
| **CE requirement** | 30 credits/3 years (ARDMS) |
| **Annual CE credits consumed** | ~850,000 |
| **Credentialing body** | ARDMS (American Registry for Diagnostic Medical Sonography) |
| **CE approval** | ARDMS accepts ASRT-approved credits |
| **Accreditation difficulty** | LOW — ASRT approval already covers this |
| **Job growth** | 15% (fastest-growing imaging modality) |
| **Median salary** | $86,490 |
| **Vacancy rate** | High — similar crisis to RTs |
| **Key competitors** | Burwin Institute, SonoSim, ESP Ultrasound, Gulfcoast Ultrasound |
| **Market gap** | POCUS (point-of-care ultrasound) is exploding beyond radiology into ED, primary care, surgery — RTs and sonographers both need education |

**Why Tier 2:** ARDMS accepts ASRT Category A credits. Once TechCelerate has ASRT approval, sonography courses require no additional accreditation. Just content development. Market is growing faster than RT.

**Data sources:**
- ARDMS credential database (aggregate)
- SDMS (Society of Diagnostic Medical Sonography) membership data
- BLS OES for sonographers by state
- CAAHEP-accredited sonography program directory

---

### Nuclear Medicine Technologists

| Metric | Data |
|--------|------|
| **Total professionals** | ~19,000 (BLS) |
| **CE requirement** | 24 credits/biennium (ARRT) OR NMTCB requirements |
| **Credentialing bodies** | ARRT (N) + NMTCB (Nuclear Medicine Technology Certification Board) |
| **CE approval** | ASRT-approved credits accepted by both ARRT and NMTCB |
| **Accreditation difficulty** | LOW — ASRT covers both credential paths |
| **Job growth** | Strong — theranostics revolution driving demand |
| **Market gap** | Theranostics, new radiotracers, PET/CT advances, Lutetium-177 therapy |

**Why Tier 2:** Same ASRT accreditation. Fastest-growing enrollment (903→1,403 from 2023-2024). Theranostics is a massive pharma investment area (Novartis, Bayer) = potential for pharma-funded education via CAMEOS/Catalyst partnership.

---

### Radiation Therapists

| Metric | Data |
|--------|------|
| **Total professionals** | ~17,000 (BLS) |
| **CE requirement** | 24 credits/biennium (ARRT) |
| **Credentialing body** | ARRT (T) |
| **CE approval** | ASRT-approved credits |
| **Accreditation difficulty** | LOW — ASRT covers this |
| **Job growth** | Record enrollment (1,663 in 2024) |
| **Market gap** | AI-assisted treatment planning, proton therapy, IGRT, stereotactic techniques |

**Why Tier 2:** Same ASRT accreditation. Adjacent to RT core knowledge. Record enrollment = growing pipeline of learners.

---

## TIER 3: MODERATE EXPANSION (Additional accreditation needed)

### Medical Assistants (MAs)

| Metric | Data |
|--------|------|
| **Total professionals** | ~743,000 (BLS — one of the largest allied health professions) |
| **CE requirement** | 60 recertification points/5 years (CMA via AAMA) |
| **Credentialing bodies** | AAMA (CMA certification), AMT (RMA certification), NHA (CCMA) |
| **CE approval** | AAMA-approved CE providers (separate from ASRT) |
| **Accreditation difficulty** | MODERATE — need AAMA CE provider approval (different process from ASRT) |
| **Education program accreditor** | CAAHEP (via MAERB) or ABHES |
| **Job growth** | 15% (2023-2033) — one of the fastest-growing occupations |
| **Median salary** | $42,000 |
| **Vacancy rate** | Very high — critical shortages especially in primary care |
| **Key competitors** | NHA (National Healthcareer Association), AAMA itself, local community colleges |
| **Market gap** | EHR/EMR training, clinical procedures updates, AI in clinical practice, CMS quality measure compliance |

**Why Tier 3:** Massive market (743K professionals) but different accreditation path. AAMA CE provider approval is a separate application process. However, the content delivery platform (LearnDash on WordPress) is identical. Once approved, the TAM is enormous.

**Critical CMS development:** CMS now allows certified medical assistants to enter medication and diagnostic orders into EHRs — previously only licensed professionals could do this. This creates immediate, mandatory training need. First platform to offer this CE wins a huge market.

**Data sources:**
- BLS OES for medical assistants by state/metro
- AAMA membership and certification data
- CAAHEP program directory (MA programs)
- ABHES program directory
- NHA certification volume data
- CMS regulatory changes affecting MA scope

---

### Pharmacy Technicians

| Metric | Data |
|--------|------|
| **Total professionals** | ~472,000 (BLS) |
| **CE requirement** | 20 hours/2 years (PTCB) or state-specific |
| **Credentialing bodies** | PTCB (Pharmacy Technician Certification Board), NHA (ExCPT) |
| **CE approval** | ACPE (Accreditation Council for Pharmacy Education) — different system |
| **Accreditation difficulty** | MODERATE-HIGH — ACPE is a completely different accreditation body |
| **Job growth** | 6% (faster than average) |
| **Median salary** | $40,300 |
| **Market gap** | Expanded scope of practice (vaccine administration, point-of-care testing), technology/automation, biosimilar handling |

**Why Tier 3:** Large market but ACPE accreditation is a different universe from ASRT. Worth pursuing but not before Tier 2 markets are captured. Note: University of Tennessee (your accredited provider partner) has a College of Pharmacy — potential accreditation pathway.

---

### Surgical Technologists

| Metric | Data |
|--------|------|
| **Total professionals** | ~119,000 (BLS) |
| **CE requirement** | 30 CE credits/2 years (NBSTSA) |
| **Credentialing body** | NBSTSA (National Board of Surgical Technology and Surgical Assisting) |
| **CE approval** | AST (Association of Surgical Technologists) approved CE |
| **Accreditation difficulty** | MODERATE — AST CE approval is a separate process |
| **Job growth** | 5% |
| **Median salary** | $60,610 |
| **Market gap** | Robotic surgery, minimally invasive techniques, AI in surgical planning |

---

### EMS / Paramedics

| Metric | Data |
|--------|------|
| **Total professionals** | ~270,000 (BLS) |
| **CE requirement** | NREMT recertification: 40 hrs/2 years (Paramedic), 30 hrs/2 years (AEMT), 20 hrs/2 years (EMT) |
| **Credentialing body** | NREMT (National Registry of Emergency Medical Technicians) |
| **CE approval** | CAPCE (Commission on Accreditation for Pre-Hospital Continuing Education) |
| **Accreditation difficulty** | MODERATE — CAPCE has specific provider requirements |
| **Job growth** | 5% |
| **Market gap** | Point-of-care imaging (POCUS in EMS), AI triage decision support, telemedicine integration |

**Why interesting:** POCUS (point-of-care ultrasound) in EMS is an emerging field. TechCelerate could bridge RT imaging expertise with EMS clinical practice — unique content nobody else has.

---

## TIER 4: LARGER OPPORTUNITY, HIGHER BARRIER

### Nurses (RN/LPN)

| Metric | Data |
|--------|------|
| **Total professionals** | ~3.2 million RNs + ~620,000 LPNs |
| **CE requirement** | Varies by state (15-30 hours/1-2 years) |
| **CE approval** | ANCC (American Nurses Credentialing Center) or state-approved |
| **Accreditation difficulty** | HIGH — ANCC accreditation is rigorous and competitive |
| **Market gap** | Imaging-adjacent nursing CE: IR nursing, radiology nursing, CT/MRI patient management |

**Why Tier 4:** Enormous market but highly competitive and different accreditation. However, a NICHE play is viable: radiology/imaging department nurses are underserved by both nursing CE and RT CE. TechCelerate could serve this niche without full ANCC accreditation by partnering with an ANCC-accredited provider (same model as Catalyst + UofT).

---

### Physical Therapists / PTAs

| Metric | Data |
|--------|------|
| **Total professionals** | ~306,000 PTs + ~98,000 PTAs |
| **CE requirement** | Varies by state (typically 20-40 hours/2 years) |
| **Accreditation** | State-specific approval varies widely |
| **Market gap** | Musculoskeletal imaging education for PTs, diagnostic imaging referral patterns, ultrasound-guided interventions |

---

## ACCREDITATION SCOUT: PRIORITY MATRIX

| Market | Professionals | CE Accred. Difficulty | Market Gap | TechCelerate Fit | PRIORITY |
|--------|--------------|----------------------|------------|-----------------|----------|
| **RTs (core)** | 216,000 | ✅ Already pursuing | AI, simulation, pathways | Perfect | **DAY 1** |
| **Sonographers** | 85,000 | ✅ ASRT covers | POCUS, AI | Perfect | **TIER 2 — Q3 2026** |
| **Nuclear Med** | 19,000 | ✅ ASRT covers | Theranostics | Strong | **TIER 2 — Q3 2026** |
| **Rad Therapy** | 17,000 | ✅ ASRT covers | AI planning | Strong | **TIER 2 — Q4 2026** |
| **Medical Assistants** | 743,000 | 🟡 AAMA approval needed | EHR/CMS scope expansion | Good — huge TAM | **TIER 3 — 2027** |
| **Pharmacy Techs** | 472,000 | 🟡 ACPE needed | Expanded scope | Moderate | **TIER 3 — 2027** |
| **Surgical Techs** | 119,000 | 🟡 AST approval | Robotic surgery | Moderate | **TIER 3 — 2027** |
| **EMS/Paramedics** | 270,000 | 🟡 CAPCE needed | POCUS, AI triage | Moderate | **TIER 3 — 2027** |
| **Nurses (niche)** | Subset of 3.8M | 🔴 ANCC or partner | Imaging nursing | Niche fit | **TIER 4 — 2028** |
| **PTs** | 404,000 | 🔴 State-specific | MSK imaging | Niche fit | **TIER 4 — 2028** |

**TOTAL ADDRESSABLE LEARNERS:**
- Tier 1 (Day 1): 216,000
- Tier 1 + 2: 337,000
- Tier 1 + 2 + 3: 1,941,000
- Full expansion: 5,600,000+

---

## DATA SOURCES FOR THE ACCREDITATION SCOUT

### Employment & Market Sizing

| Source | What It Provides | Cost | Update Frequency |
|--------|-----------------|------|-----------------|
| BLS OES | Employment by occupation, state, metro, industry, wage | Free | Annual (May release) |
| BLS Employment Projections | 10-year growth forecasts by occupation | Free | Biennial |
| ASRT Enrollment Snapshot | RT program enrollment by modality | Free (annual report) | Annual |
| ARRT Annual Report | Credential counts by modality and state | Free | Annual |
| ARDMS Annual Report | Sonography credential counts | Free | Annual |
| JRCERT Program Directory | RT education programs: location, type, enrollment | Free | Continuous |
| CAAHEP Program Directory | Allied health programs across 30+ disciplines | Free | Continuous |

### Job Demand (Real-Time)

| Source | What It Provides | Cost | Update Frequency |
|--------|-----------------|------|-----------------|
| Indeed API / Scrape | Job postings: title, location, salary, employer, specialty | Free to scrape | Daily |
| LinkedIn Jobs | Same + employer size, growth signals | API costs | Daily |
| ZipRecruiter | Salary estimates, demand by location | Free data | Daily |
| Glassdoor | Employer reviews, salary data, company ratings | API costs | Daily |
| Health eCareers | Healthcare-specific job board, particularly allied health | Scrape | Daily |
| ASRT Job Board | RT-specific positions | Scrape | Weekly |

**What job data tells TechCelerate:**
- Which employers to target for Employer Dashboard (facilities posting 3+ positions = hot market)
- Which specialties are hottest (CT, MRI, IR trending up = prioritize that CE content)
- Geographic demand (Florida, Texas, California = highest RT employment → market there first)
- Salary trends (rising salaries = employers willing to invest in retention via CE)
- Employer type (hospital vs. outpatient vs. urgent care = different CE needs)

### Accreditation & Compliance Intelligence

| Source | What It Provides | Cost | Update Frequency |
|--------|-----------------|------|-----------------|
| ASRT CE Approval Requirements | Rules for becoming an ASRT-approved CE sponsor | Free | As updated |
| ARRT CE Requirements | Credit types, biennium rules, audit criteria | Free | As updated |
| State Licensing Board Websites (50 states) | State-specific CE requirements, approved topics, approved providers | Free to scrape | Varies |
| AAMA CE Provider Requirements | Rules for MA CE approval | Free | As updated |
| ACPE Provider Requirements | Pharmacy tech CE rules | Free | As updated |
| CAPCE Provider Standards | EMS CE approval requirements | Free | As updated |
| FDA MQSA | Mammography quality standards (additional CE requirements) | Free | As updated |

### Competitive Intelligence

| Source | What It Provides | Cost |
|--------|-----------------|------|
| ASRT CE Library | 500+ courses — the benchmark competitor | ASRT membership |
| eRadImaging | Competitor pricing, content catalog, state coverage | $54.95 (for research) |
| Pulse Radiology / Edcetera | Competitor offering post-acquisition | Public website |
| CE4RT | Competitor pricing, course catalog | Public website |
| X-Ray CE / RadTechBootCamp | Smaller competitors | Public websites |
| SonoSim | Sonography simulation competitor | Public website |
| NHA Learning Center | MA/pharmacy tech CE competitor | Public website |

### Emerging Opportunity Signals

| Source | What It Provides | Why It Matters |
|--------|-----------------|---------------|
| RSNA conference program | Radiology tech advances, AI sessions | Predicts CE topics 6-12 months out |
| ASRT@RSNA course list | What ASRT thinks RTs need to learn | Direct content demand signal |
| FDA 510(k) clearances | New imaging devices approved | Equipment-specific CE opportunity |
| ACR practice guidelines | Standard of care changes | Mandatory training trigger |
| CMS regulatory changes | Scope of practice expansions | New CE demand (MA EHR orders) |
| State legislature tracker | Scope of practice bills | State-specific CE requirements coming |
| ARRT CQR updates | Continuing Qualifications Requirements | New structured education mandates |

---

## EXPANSION PLAYBOOK

### Phase 1: RT Core (Now → July 2026)
- ASRT accreditation (in progress)
- Initial course catalog: AI, dose optimization, digital radiography
- BLS + ARRT data → target top 10 states by employment × vacancy rate
- Launch Employer Dashboard pilot with 3-5 hospitals

### Phase 2: Adjacent Imaging (Q3-Q4 2026)
- Sonography courses (ASRT approval already covers this)
- Nuclear medicine/PET-CT courses (same)
- Radiation therapy courses (same)
- TAM grows from 216K to 337K with ZERO additional accreditation

### Phase 3: Beyond Imaging (2027)
- AAMA CE provider application (medical assistants — 743K professionals)
- CAPCE application (EMS — 270K professionals)
- Explore ACPE pathway via UofT College of Pharmacy (pharmacy techs — 472K)

### Phase 4: Full Allied Health Platform (2028+)
- Nursing niche (imaging nursing) via ANCC-accredited partner
- PT/OT niche (MSK imaging education)
- Surgical tech CE
- Interprofessional education (JA-CEHP accreditation)

**At full expansion: TechCelerate serves 5.6M+ allied health professionals across 10+ disciplines, all on the same WordPress/LearnDash platform, with the same employer dashboard, the same AI-powered recommendation engine, and the same continuous intelligence loops feeding content decisions.**

---

## KEY INSIGHT: ACCREDITATION PARTNERSHIPS

For Tier 3+ markets, TechCelerate doesn't need to get every accreditation directly. The same partnership model Catalyst uses (University of Tennessee as accredited provider) works for allied health:

- **For MAs:** Partner with a CAAHEP-accredited MA program to co-offer CE
- **For Pharmacy Techs:** Partner via UofT College of Pharmacy (ACPE-accredited)
- **For Nursing:** Partner with an ANCC-accredited nursing CE provider
- **For EMS:** Partner with a CAPCE-accredited provider

Each partnership = new market without the 6-12 month accreditation timeline. The ACCREDITATION SCOUT database tracks which providers in each discipline are: (a) currently accredited, (b) have capacity for partnerships, (c) are reasonably priced, and (d) are geographically or strategically aligned with TechCelerate.

**This is the same play that made Catalyst successful — partner with accredited providers rather than maintaining your own accreditation. TechCelerate scales by replicating this model across every allied health discipline.**
