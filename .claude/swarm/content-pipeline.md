# TechCelerate Content Pipeline — Swarm Configuration
# 3 parallel agents
# Created: 2026-03-08

---

## Agent 1: COURSE-BUILDER

**Owner:** Course loading pipeline
**Files owned:**
- tools/courses/
- tools/shared/wp_client/
- tools/shared/course_templater/

**Task:** Source doc → HTML templater → LearnDash via wp_client.

**Pipeline:**
1. Read source document (DOCX/PDF)
2. Extract sections: title, objectives, content body, references
3. Apply HTML template via CourseTemplater
4. Validate structure
5. Upload to LearnDash via WPClient
6. Configure course settings (credit hours, category, passing score)

**Acceptance criteria:**
- End-to-end source doc to LearnDash course
- All 4 priority courses (RT_24003, RT_23001, RT_23009, RT_23016) processable
- Course structure matches LearnDash best practices
- Lesson/topic hierarchy correct

---

## Agent 2: COMPLIANCE

**Owner:** ASRT validation
**Files owned:**
- tools/shared/compliance_engine/
- tools/shared/certificate_generator/

**Task:** Run all 20 ASRT rules on every course, flag violations,
generate certificate preview.

**ASRT Rules (must ALL pass):**
1. Credit-to-word-count minimum met
2. Minimum question count met
3. ≥60% questions are multiple choice
4. No "all of the above" / "none of the above" / "both A and B"
5. Each MC question has exactly 4 options
6. True/false ≤10% of total questions
7. All objectives use measurable Bloom's taxonomy verbs
8. AMA 11th Edition references (via AMA11Validator)
9. References ≤5 years old (WARNING for older)
10. 75% passing score configured
11. All 11 certificate elements present
12. Approval statement exact text: "Activity approved by ASRT."
13-20. Additional structural and formatting rules

**Acceptance criteria:**
- Compliance report per course with pass/fail per rule
- Certificate preview showing all 11 mandatory elements
- Violation summary with specific remediation instructions
- Human review items flagged separately (HOTL pattern)

---

## Agent 3: SEO-FACTORY

**Owner:** Programmatic SEO
**Files owned:**
- tools/seo/ (new)
- tools/shared/wp_client/

**Task:** Generate state-specific landing pages, vertical pages,
load to WordPress.

**Page types:**
1. **State pages (50):** "[State] Continuing Education for Radiologic Technologists"
2. **Vertical pages:** CE by specialty (MRI, CT, Mammography, Radiography, etc.)
3. **Credential pages:** CE by credential type (ARRT, state-specific)

**Acceptance criteria:**
- 50 state landing pages generated and loaded
- Vertical landing pages for each specialty
- SEO metadata (title, description, schema markup) per page
- Internal linking structure between pages
- RankMath compatibility verified

---

## Governance Rules (ALL AGENTS)

1. **SEPARATE COMPANY:** TechCelerate is NOT Catalyst/CAMEOS — never mix branding
2. **Server:** root@45.59.100.119 — NEVER modify nginx (Dennis only)
3. **Plugin installs:** Never install WordPress plugins without Lou approval
4. **ASRT deadline:** April 25, 2026 — prioritize compliance-blocking work
5. **Branching:** Each agent commits to its own branch: `agent/tc-[name]`
6. **Human gates:** SME review (Stage 5) cannot be automated
7. **Source docs are read-only:** Never modify files in courses/*/source/
