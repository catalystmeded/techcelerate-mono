---
name: course-builder
description: Build and load a course from source document to LearnDash
triggers: ["build course", "load course", "create course"]
status: STUB
---

# Course Builder

**Status:** STUB — wire when course_templater + wp_client vendored from shared-services.

## Usage
```
/course-builder RT_24003
/course-builder --source courses/RT_24003/source/chest_radiography.docx
```

## What It Does
Reads a source document, processes it through the content pipeline, and loads it into LearnDash.

## Pipeline
1. Read source document from `courses/[course_id]/source/`
2. Extract: title, objectives, content sections, references, post-test questions
3. Apply HTML template via CourseTemplater
4. Run ASRT compliance check (auto-triggers /asrt-compliance)
5. Upload to LearnDash via WPClient
6. Configure: credit hours, category, passing score (75%), certificate

## Implementation (when wired)
```python
from tools.shared.course_templater import CourseTemplater
from tools.shared.wp_client import WPClient
from tools.shared.compliance_engine import ComplianceEngine

templater = CourseTemplater()
wp = WPClient(site="radiology.techcelerate-ce.com")
compliance = ComplianceEngine()

# Extract → Template → Validate → Upload
content = templater.extract(source_path)
html = templater.render(content)
report = compliance.validate(html)

if report.passed:
    wp.create_course(html, settings)
else:
    print("Compliance failures — fix before upload")
    print(report.summary())
```

## Dependencies
- `tools/shared/course_templater/` (vendor copy)
- `tools/shared/wp_client/` (vendor copy)
- `tools/shared/compliance_engine/` (vendor copy)
