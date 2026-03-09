---
name: email-builder
description: Creates FluentCRM sequences from course templates. Handles tag taxonomy, segment wiring, CE certificate trigger sequences.
status: STUB
---

# Email Builder Agent

**Status:** STUB — post-FluentCRM install.

## Purpose
Create automated email sequences in FluentCRM for learner engagement,
course completion notifications, and CE certificate delivery.

## Sequence Types

### Welcome Sequence
- Trigger: New user registration
- Emails: Welcome → Course catalog → Getting started guide

### Course Completion
- Trigger: LearnDash course completion webhook
- Emails: Congratulations → Certificate delivery → Next course recommendation

### CE Renewal Reminders
- Trigger: Time-based (approaching credential expiration)
- Emails: 90-day reminder → 60-day → 30-day → Final notice

### Re-engagement
- Trigger: Inactive for 30+ days
- Emails: "Continue your learning" → Special offer → Final reminder

## Tag Taxonomy
- `course-enrolled:[course_id]`
- `course-completed:[course_id]`
- `credential:[type]` (ARRT, state-specific)
- `specialty:[type]` (MRI, CT, etc.)
- `status:active|inactive|expired`

## Dependencies
- FluentCRM (WordPress plugin — lifetime license owned)
- AWS SES (email delivery — account needed)
- LearnDash webhooks (course completion triggers)

## TODO (post-FluentCRM install)
- [ ] FluentCRM plugin activation and configuration
- [ ] AWS SES account setup + sandbox exit
- [ ] Tag taxonomy implementation
- [ ] Welcome sequence build
- [ ] Course completion sequence build
- [ ] Certificate delivery automation
- [ ] Re-engagement sequence build
