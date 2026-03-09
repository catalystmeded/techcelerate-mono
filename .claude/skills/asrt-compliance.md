---
name: asrt-compliance
description: Run ASRT compliance validation on course content
triggers: ["compliance check", "ASRT validate", "check course"]
status: STUB
---

# ASRT Compliance Check

**Status:** STUB — wire logic when compliance_engine vendored from shared-services.

## Usage
```
/asrt-compliance [course_id]
/asrt-compliance RT_24003
```

## What It Does
Runs the full 20-rule ASRT compliance engine against a course and reports pass/fail per rule.

## Implementation (when wired)
```python
from tools.shared.compliance_engine import ComplianceEngine
from tools.shared.reference_validator import AMA11Validator

engine = ComplianceEngine()
result = engine.validate(course_id)

for rule in result.rules:
    status = "PASS" if rule.passed else "FAIL"
    print(f"  [{status}] Rule {rule.id}: {rule.description}")
    if not rule.passed:
        print(f"         Fix: {rule.remediation}")
```

## Output
- Per-rule pass/fail report
- Overall compliance score
- Remediation instructions for failures
- Human review items flagged separately

## Dependencies
- `tools/shared/compliance_engine/` (vendor copy from shared-services)
- `tools/shared/reference_validator/` (vendor copy from shared-services)
