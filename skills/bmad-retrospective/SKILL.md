# BMad Retrospective

Use at the end of a sprint to reflect on what went well, what didn't, and what to improve.

Trigger with: "retrospective", "retro", "sprint review", "sprint retrospective"

## Instructions

**Agent:** Scrum Master (Sam)
**Input:** `_bmad/sprint-status.yaml`, completed story files
**Output:** Retrospective entry appended to sprint-status.yaml

### Step 1: Load Sprint Data

Read `_bmad/sprint-status.yaml`. Identify:
- Sprint number and goal
- Stories completed vs planned
- Any blocked or carried-over stories
- Time spent (if tracked)

### Step 2: Gather Feedback

Ask the user about:

1. **What went well?** — Processes, tools, patterns that worked
2. **What didn't go well?** — Friction points, blockers, quality issues
3. **What should we change?** — Concrete improvements for next sprint

### Step 3: Analyze Patterns

Based on sprint data and feedback, identify:
- Recurring blockers or issues
- Stories that took longer than expected (and why)
- Agent workflows that need adjustment
- Quality trends (code review pass rate, test coverage)

### Step 4: Create Action Items

For each improvement area, create a specific action:
- What to do differently
- Who/what is responsible
- How to measure success

### Step 5: Record Retrospective

Append to `_bmad/sprint-status.yaml` under `retrospectives`:

```yaml
retrospectives:
  - sprint: 1
    date: "[date]"
    goal_met: true/false
    stories_completed: 4
    stories_planned: 5
    carried_over:
      - STORY-02-03
    went_well:
      - "[item]"
    needs_improvement:
      - "[item]"
    action_items:
      - action: "[what to change]"
        owner: "[agent or user]"
```

### Step 6: Plan Next Sprint

If more stories remain:
1. Update `current_sprint` in sprint-status.yaml
2. Assign stories to the next sprint
3. Set the new sprint goal
4. Announce: "Sprint [N+1] planned. Start with `/bmad-cowork:create-story` for [next story]"

If all stories complete:
- Announce: "All epics and stories complete! Project implementation finished."
