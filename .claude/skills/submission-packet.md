---
name: submission-packet
description: Generate ASRT submission packet for accreditation review
triggers: ["submission packet", "ASRT submission"]
status: STUB
---

# ASRT Submission Packet Generator

**Status:** STUB — May sprint.

## Usage
```
/submission-packet RT_24003
/submission-packet --all    # Generate for all 4 priority courses
```

## What It Does
Generates a complete ASRT submission packet including the application form,
course content, reviewer credentials, and supporting documentation.

## Packet Contents
1. **Application Form** — ASRT standard template with all fields populated
2. **Course Content** — Full course in required format
3. **Post-Test** — Questions with answer key and rationales
4. **Learning Objectives** — Mapped to Bloom's taxonomy
5. **References** — AMA 11th Edition formatted, currency verified
6. **Certificate Template** — Showing all 11 mandatory elements
7. **Reviewer Credentials** — SME qualifications and disclosure
8. **Compliance Report** — Output from /asrt-compliance showing all rules pass

## Output Format
- Word document (.docx) — main application
- PDF bundle — all supporting documents
- Saved to: `submissions/[course_id]/ASRT_SUBMISSION_[date].docx`

## Priority Courses
| Course ID | Title | Writer | Status |
|---|---|---|---|
| RT_24003 | Chest Radiography | Heidi Veillette | FINAL |
| RT_23001 | MS MRI Imaging | Heidi Veillette | FINAL |
| RT_23009 | Radiation Physics | Kelli Haynes | FINAL |
| RT_23016 | Radiography Imaging | Heidi Veillette | FINAL |

## Dependencies
- Compliance engine must pass all 20 rules before packet generation
- SME review (Stage 5) must be complete — human gate, cannot be automated
- Certificate template must have all 11 ASRT elements verified

## TODO (May sprint)
- [ ] ASRT application template
- [ ] Auto-population logic
- [ ] PDF bundle generator
- [ ] Compliance gate enforcement
- [ ] Batch generation (--all flag)
