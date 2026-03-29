---
name: epics
description: "Break architecture into implementable epics and stories with acceptance criteria. Phase 3."
---

Use when breaking architecture into implementable epics and stories with acceptance criteria. This is a Phase 3 workflow that must run AFTER architecture is complete.

Trigger with: "create epics", "create stories", "break down work", "story breakdown", "epics and stories"

## Instructions

**Agent:** Scrum Master (Sam)
**Input:** `_bmad-output/planning-artifacts/architecture.md`, `_bmad-output/planning-artifacts/prd.md`, optionally `_bmad-output/planning-artifacts/ux-design.md`
**Output:** `_bmad-output/planning-artifacts/epics-and-stories.md`

### Step 1: Load Context

Read architecture (required), PRD (required), and UX design (if exists). The architecture is the primary driver — V6 creates epics AFTER architecture so technical decisions inform story breakdown.

### Step 2: Identify Epics

Group work into epics based on:
- Feature areas from the PRD
- Technical layers from the architecture
- Dependencies and delivery order

Each epic needs:
- Epic ID (EPIC-01, EPIC-02, etc.)
- Title and description
- Business value statement
- Dependencies on other epics
- Estimated story count

### Step 3: Break Epics into Stories

For each epic, create stories that are:
- **Independent** — can be implemented without other incomplete stories
- **Negotiable** — details can be discussed
- **Valuable** — delivers user or technical value
- **Estimable** — small enough to estimate
- **Small** — completable in 1-3 days
- **Testable** — has clear acceptance criteria

Each story needs:
- Story ID (STORY-[epic]-[number], e.g., STORY-01-01)
- Title
- Description (As a [user], I want [feature], so that [benefit])
- Acceptance criteria (Given/When/Then format)
- Tasks (implementation steps)
- Dependencies
- Estimated effort (S/M/L)

### Step 4: Order Stories

Arrange stories considering:
1. Dependencies (what must come first)
2. Risk (high-risk items early for fast feedback)
3. Value (high-value items early)
4. Foundation (infrastructure and setup stories first)

### Step 5: Draft the Document

```markdown
# Epics and Stories: [Project Name]

## Epic Overview

| Epic ID | Title | Stories | Dependencies | Priority |
|---------|-------|---------|-------------|----------|

## EPIC-01: [Title]
### Description
### Business Value
### Stories

#### STORY-01-01: [Title]
**As a** [user type]
**I want** [capability]
**So that** [benefit]

**Acceptance Criteria:**
- Given [context], When [action], Then [result]
- Given [context], When [action], Then [result]

**Tasks:**
1. [Task 1]
2. [Task 2]

**Dependencies:** [none / STORY-XX-XX]
**Effort:** [S/M/L]

---
(repeat for each story)
```

### Step 6: Review and Finalize

Present to user. Verify: every PRD requirement maps to at least one story. Every story traces to architecture.

### Step 7: Save and Update Status

1. Save to `_bmad-output/planning-artifacts/epics-and-stories.md`
2. Update `_bmad/bmm-workflow-status.yaml`: set `phase_3_solutioning.epics_and_stories` to `"complete"`
3. Announce: "Epics and stories created. Next: run readiness check (`/bmad-cowork:ready`) or go straight to sprint planning (`/bmad-cowork:sprint-plan`)"
