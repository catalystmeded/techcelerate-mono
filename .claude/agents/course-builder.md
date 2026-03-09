---
name: course-builder
description: Processes source docs → HTML → LearnDash. Owns course loading pipeline.
status: STUB
---

# Course Builder Agent

**Status:** STUB — logic pending shared-services vendor copy in May sprint.

## Purpose
Process source documents through the content pipeline and load them into LearnDash.

## Pipeline
1. Read source document (DOCX/PDF) from `courses/[course_id]/source/`
2. Extract structured content (title, objectives, body, references, post-test)
3. Apply HTML template via `CourseTemplater` from shared-services
4. Validate structure and content completeness
5. Upload to LearnDash via `WPClient` from shared-services
6. Configure course settings (credit hours, category, passing score 75%)

## Dependencies (from shared-services)
```python
from tools.shared.wp_client import WPClient
from tools.shared.course_templater import CourseTemplater
```

## File Ownership
- `tools/courses/` — course processing scripts
- `tools/shared/wp_client/` — WordPress API client (vendor copy)
- `tools/shared/course_templater/` — HTML templating (vendor copy)

## Inputs
- Source document path
- Course ID (e.g., RT_24003)
- Credit hours and category

## Outputs
- LearnDash course created with:
  - Lessons and topics structured
  - Quiz with post-test questions
  - Certificate template linked
  - Completion tracking enabled

## TODO (May sprint)
- [ ] Vendor copy wp_client from shared-services
- [ ] Vendor copy course_templater from shared-services
- [ ] Implement document extraction logic
- [ ] Build LearnDash upload pipeline
- [ ] Test with 4 priority courses
