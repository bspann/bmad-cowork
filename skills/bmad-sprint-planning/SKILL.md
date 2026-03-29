# BMad Sprint Planning

Use when transitioning from planning to implementation. Creates sprint-status.yaml — the single source of truth for Phase 4 tracking.

Trigger with: "sprint planning", "plan sprint", "start implementation", "start sprint"

## Instructions

**Agent:** Scrum Master (Sam)
**Input:** `_bmad-output/planning-artifacts/epics-and-stories.md`
**Output:** `_bmad/sprint-status.yaml`

### Step 1: Load Epics and Stories

Read `_bmad-output/planning-artifacts/epics-and-stories.md`. Build the complete inventory of work.

### Step 2: Create Sprint Status File

Create `_bmad/sprint-status.yaml`:

```yaml
project_key: "default"
current_sprint: 1
sprint_goal: "[Goal for Sprint 1]"

epics:
  EPIC-01:
    title: "[Epic Title]"
    status: "in_progress"  # not_started | in_progress | complete
    stories:
      STORY-01-01:
        title: "[Story Title]"
        status: "todo"  # todo | in_progress | review | complete | blocked
        effort: "M"
        assigned_sprint: 1
        blockers: []
      STORY-01-02:
        title: "[Story Title]"
        status: "todo"
        effort: "S"
        assigned_sprint: 1
        blockers: []
  EPIC-02:
    title: "[Epic Title]"
    status: "not_started"
    stories:
      STORY-02-01:
        title: "[Story Title]"
        status: "todo"
        effort: "L"
        assigned_sprint: 2
        blockers: []

retrospectives: []
```

### Step 3: Assign Stories to Sprint 1

Select stories for Sprint 1 based on:
1. Dependencies (foundation stories first)
2. Priority (must-have before nice-to-have)
3. Capacity (don't overload — aim for 3-5 stories per sprint)

### Step 4: Define Sprint Goal

Write a clear sprint goal that describes what will be demonstrable at sprint end.

### Step 5: Announce Sprint Plan

Present the sprint plan to the user:
- Sprint goal
- Stories assigned to Sprint 1 (in order)
- Estimated effort
- First story to implement

Tell the user: "Sprint 1 planned. Start with: `/bmad-cowork:create-story` for [first story ID]"

### Step 6: Update Workflow Status

Update `_bmad/bmm-workflow-status.yaml`: set `phase_4_implementation.sprint_planning` to `"complete"`, `phase_4_implementation.status` to `"in_progress"`
