---
name: create-story
description: "Prepare a detailed story file for implementation with tasks and acceptance criteria."
---

Use when preparing a specific story for implementation. Creates a detailed story file that serves as the developer's blueprint.

Trigger with: "create story", "prepare story", "story file for [ID]"

## Instructions

**Agent:** Scrum Master (Sam)
**Input:** `_bmad-output/planning-artifacts/epics-and-stories.md`, `_bmad-output/planning-artifacts/architecture.md`
**Output:** `_bmad-output/implementation-artifacts/stories/[STORY-ID].md`

### Step 1: Identify the Story

Ask which story to prepare, or read from sprint-status.yaml to find the next todo story.

### Step 2: Load Context

Read the story from epics-and-stories.md. Read relevant sections of architecture.md. Read UX design if applicable.

### Step 3: Create Detailed Story File

```markdown
# [STORY-ID]: [Story Title]

## Description
As a [user type], I want [capability], so that [benefit].

## Status: TODO

## Architecture Context
[Relevant architecture decisions, patterns, and components for this story]

## Acceptance Criteria
1. Given [context], When [action], Then [result]
2. Given [context], When [action], Then [result]
3. Given [context], When [action], Then [result]

## Tasks
### Task 1: [Title]
- Description: [What to implement]
- Files: [Expected files to create/modify]
- Tests: [What tests to write]

### Task 2: [Title]
- Description: [What to implement]
- Files: [Expected files to create/modify]
- Tests: [What tests to write]

### Task 3: [Title]
- Description: [What to implement]
- Files: [Expected files to create/modify]
- Tests: [What tests to write]

## Dependencies
- [STORY-XX-XX or "none"]

## Definition of Done
- [ ] All tasks implemented
- [ ] All acceptance criteria verified
- [ ] All tests written and passing
- [ ] Code reviewed and approved
- [ ] No console errors or warnings
- [ ] Documentation updated (if applicable)

## Dev Notes
[Any additional context the developer needs]
```

### Step 4: Save and Update Status

1. Save to `_bmad-output/implementation-artifacts/stories/[STORY-ID].md`
2. Update sprint-status.yaml: keep status as `"todo"` (dev-story will change to `"in_progress"`)
3. Announce: "Story [ID] ready for implementation. Next: `/bmad-cowork:dev` for [STORY-ID]"
