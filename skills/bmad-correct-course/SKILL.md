# BMad Correct Course

Use when a story needs significant changes mid-implementation, requirements shift, or an architectural issue is discovered during development.

Trigger with: "correct course", "scope change", "requirements changed", "story needs changes", "architectural issue"

## Instructions

**Agent:** Scrum Master (Sam) — may involve Architect (Archie) or PM (Patricia)

### Step 1: Assess the Change

Ask the user to describe what changed and why. Classify:

- **Minor adjustment** — acceptance criteria tweak, task reordering → update story file, continue
- **Story scope change** — new tasks or removed tasks → update story file, re-estimate
- **Architecture impact** — new pattern needed, data model change → involve Architect
- **Requirements change** — new user needs, changed priorities → involve PM
- **Full pivot** — fundamental direction change → pause sprint, return to planning

### Step 2: Impact Analysis

For the identified change:
1. Which stories are affected?
2. Does the architecture need updating?
3. Does the PRD need updating?
4. Are there dependency impacts on other stories?
5. Does the sprint goal change?

### Step 3: Route to Resolution

**Minor adjustment:**
1. Update the story file directly
2. Continue implementation
3. No status change needed

**Story scope change:**
1. Update the story file with new/modified tasks
2. Re-estimate effort
3. Assess if sprint goal is still achievable
4. If not, consider moving stories to next sprint

**Architecture impact:**
1. Invoke Architect agent to assess and update architecture.md
2. Create new ADR for the architectural change
3. Update affected story files
4. Re-run readiness check if significant

**Requirements change:**
1. Invoke PM agent to update PRD
2. Cascade changes to architecture and stories
3. Re-assess sprint plan

**Full pivot:**
1. Mark current sprint as paused in sprint-status.yaml
2. Return to appropriate planning phase
3. Preserve all work done so far

### Step 4: Update Status Files

Update sprint-status.yaml and bmm-workflow-status.yaml as appropriate. Document the course correction in `_bmad/context.md`.

### Step 5: Resume

Announce the updated plan and next action.
