---
name: prd
description: "Create a Product Requirements Document from an approved project brief. Phase 2 (Planning)."
---

Use when creating a Product Requirements Document from an approved project brief. This is Phase 2 (Planning) of the BMad Method.

Trigger with: "create PRD", "product requirements", "requirements document", "Phase 2"

## Instructions

**Agent:** PM (Patricia)
**Input:** `_bmad-output/planning-artifacts/project-brief.md`
**Output:** `_bmad-output/planning-artifacts/prd.md`

### Step 1: Load Context

Read the project brief from `_bmad-output/planning-artifacts/project-brief.md`. Also read `_bmad/context.md` for any accumulated decisions. Identify gaps or ambiguities that need resolution before proceeding.

### Step 2: Define Users and Journeys

Create detailed user personas with:
- Name, role, demographics
- Goals, frustrations, tech savviness
- Primary use cases

Map primary user journeys with Given/When/Then acceptance criteria:
```
Given [precondition]
When [action]
Then [expected result]
```

Cover: happy path, key alternate flows, error states.

### Step 3: Specify Functional Requirements

Organize requirements by feature area. For each requirement:
- Unique ID (FR-001, FR-002, etc.)
- Description
- Priority (Must Have / Should Have / Could Have / Won't Have)
- Acceptance criteria
- Dependencies

### Step 4: Specify Non-Functional Requirements

Cover these categories:
- **Performance** — response times, throughput, concurrent users
- **Security** — authentication, authorization, data protection
- **Scalability** — growth targets and strategy
- **Accessibility** — WCAG compliance level
- **Reliability** — uptime targets, error budgets
- **Compatibility** — browsers, devices, platforms

### Step 5: Vision and Differentiators

Write:
- **Executive Summary** — 2-3 paragraph overview for stakeholders
- **Product Vision** — where this product is going long-term
- **Key Differentiators** — what sets this apart from competitors

### Step 6: Define MVP Scope

Draw a clear line:
- **MVP (v1.0)** — ships first, minimum viable
- **v1.1** — fast follow improvements
- **Future** — explicitly deferred

### Step 7: Draft the PRD

Use this structure:

```markdown
# Product Requirements Document: [Project Name]

## Executive Summary

## Product Vision

## Key Differentiators

## User Personas
### Persona 1: [Name]
### Persona 2: [Name]

## User Journeys
### Journey 1: [Name]
### Journey 2: [Name]

## Functional Requirements
### Feature Area 1
### Feature Area 2

## Non-Functional Requirements
### Performance
### Security
### Scalability
### Accessibility

## MVP Scope
### In Scope (v1.0)
### Deferred (Future)

## Dependencies and Assumptions

## Open Questions
```

### Step 8: Review and Finalize

Present to user. Iterate until approved.

### Step 9: Save and Update Status

1. Save to `_bmad-output/planning-artifacts/prd.md`
2. Update `_bmad/bmm-workflow-status.yaml`: set `phase_2_planning.prd` to `"complete"`, `phase_2_planning.status` to `"complete"`, `current_phase` to `3`
3. Append key decisions to `_bmad/context.md`
4. Announce: "PRD complete. Next: create architecture with `/bmad-cowork:architect`"
