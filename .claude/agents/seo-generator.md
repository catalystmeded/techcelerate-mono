---
name: seo-generator
description: Generates programmatic SEO pages (50 state pages + vertical landing pages). Uses wp_client for loading.
status: STUB
---

# SEO Generator Agent

**Status:** STUB — May sprint.

## Purpose
Generate and publish programmatic SEO landing pages for TechCelerate to drive organic
traffic from radiologic technologists searching for CE credits.

## Page Types

### State Pages (50)
- Template: "[State] Continuing Education for Radiologic Technologists"
- Content: State-specific licensing requirements, CE hour needs, course catalog
- URL pattern: /ce/[state-slug]/

### Vertical Pages
- Template: "[Specialty] CE Courses for Radiologic Technologists"
- Specialties: MRI, CT, Mammography, Radiography, Nuclear Medicine, Radiation Therapy
- URL pattern: /ce/[specialty-slug]/

### Credential Pages
- Template: "ARRT CE Credits" / "[State] RT License Renewal"
- URL pattern: /credentials/[credential-slug]/

## Dependencies
```python
from tools.shared.wp_client import WPClient
```

## File Ownership
- `tools/seo/` (new directory)
- `tools/shared/wp_client/` (shared with course-builder)

## Outputs
- WordPress pages with SEO metadata
- Internal linking structure
- Schema markup (Course, EducationalOrganization)
- RankMath compatibility

## TODO (May sprint)
- [ ] State licensing data collection (50 states)
- [ ] Page templates (state, vertical, credential)
- [ ] SEO metadata generator
- [ ] Schema markup templates
- [ ] WordPress upload pipeline
- [ ] Internal linking logic
