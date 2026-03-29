# BMad Workflow Status

Use to check current project status, see what's been completed, and what's next.

Trigger with: "workflow status", "sprint status", "project status", "what's done", "where are we"

## Instructions

### Step 1: Read Status Files

Check for and read:
- `_bmad/bmm-workflow-status.yaml` (Phase 1-3 tracking)
- `_bmad/sprint-status.yaml` (Phase 4 tracking)

If neither exists, report: "Project not initialized. Run `/bmad-cowork:init` first."

### Step 2: Report Phase 1-3 Status

From bmm-workflow-status.yaml, report:
- Current phase
- Completed workflows with dates
- Active workflow (if any)
- Blockers (if any)

Format:
```
📍 Current Phase: [N] ([Phase Name])

✅ Completed:
  - Project Brief
  - PRD

🔄 In Progress:
  - Architecture

⬜ Remaining:
  - UX Design (optional)
  - Epics & Stories
  - Readiness Check
```

### Step 3: Report Phase 4 Status (if applicable)

From sprint-status.yaml, report:
- Current sprint number and goal
- Story status summary (todo/in-progress/review/complete/blocked)
- Any blockers

Format:
```
🏃 Sprint [N]: [Goal]

  ✅ STORY-01-01: [Title] — Complete
  🔄 STORY-01-02: [Title] — In Progress
  ⬜ STORY-01-03: [Title] — Todo
  🚫 STORY-02-01: [Title] — Blocked: [reason]

Progress: 2/4 stories complete
```

### Step 4: Recommend Next Action

Based on current state, recommend the single most important next action with the command to run it.
