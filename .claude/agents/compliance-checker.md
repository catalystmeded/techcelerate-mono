---
name: compliance-checker
description: Runs ASRT + AMA validation against course content. Flags items requiring human review (HOTL pattern).
status: STUB
---

# Compliance Checker Agent

**Status:** STUB — logic pending May sprint.

## Purpose
Validate all course content against ASRT accreditation rules and AMA citation standards.
Flags only items requiring human review (Human On The Loop — HOTL pattern).

## Dependencies (from shared-services)
```python
from tools.shared.compliance_engine import ComplianceEngine  # 20 ASRT rules
from tools.shared.reference_validator import AMA11Validator
```

## ASRT Rule Set (20 rules)
1. Credit-to-word-count minimum
2. Minimum question count per credit hour
3. ≥60% multiple choice questions
4. No prohibited answer options ("all of the above", etc.)
5. Exactly 4 options per MC question
6. True/false ≤10% of total
7. Measurable Bloom's taxonomy verbs in objectives
8. AMA 11th Edition reference format
9. References ≤5 years old (WARNING level)
10. 75% passing score configured
11. All 11 certificate elements present
12. Approval statement exact: "Activity approved by ASRT."
13-20. Additional structural/formatting rules

## Outputs
- Per-course compliance report (pass/fail per rule)
- Violation summary with remediation instructions
- Human review queue (items requiring SME judgment)
- Certificate preview showing all 11 elements

## File Ownership
- `tools/shared/compliance_engine/` — rule engine (vendor copy)
- `tools/shared/certificate_generator/` — cert templates (vendor copy)

## TODO (May sprint)
- [ ] Vendor copy compliance_engine from shared-services
- [ ] Vendor copy certificate_generator from shared-services
- [ ] Implement all 20 ASRT rules
- [ ] Build HOTL queue for human review items
- [ ] Test against 4 priority courses
