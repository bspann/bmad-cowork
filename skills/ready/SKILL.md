---
name: ready
description: "GO/NO-GO readiness check before starting implementation. Gate between planning and building."
---

Use when all Phase 3 artifacts are complete and you need a GO/NO-GO decision before starting implementation. This is the gate between planning and building.

Trigger with: "readiness check", "ready to implement", "GO/NO-GO", "implementation readiness"

## Instructions

**Agent:** Any (typically Architect or SM)
**Input:** All planning artifacts
**Output:** GO or NO-GO decision with rationale

### Step 1: Load All Planning Artifacts

Read and verify existence of:
- `_bmad-output/planning-artifacts/project-brief.md` (required)
- `_bmad-output/planning-artifacts/prd.md` (required)
- `_bmad-output/planning-artifacts/architecture.md` (required)
- `_bmad-output/planning-artifacts/epics-and-stories.md` (required)
- `_bmad-output/planning-artifacts/ux-design.md` (optional)
- `_bmad-output/planning-artifacts/test-strategy.md` (optional, from TEA)

### Step 2: Verify Traceability

Check that:
- Every PRD requirement maps to at least one story
- Every story traces to an architecture component
- If UX design exists, every screen maps to at least one story
- No orphaned requirements or stories

### Step 3: Check Completeness

Verify each artifact has:
- [ ] Project brief: problem statement, users, value prop, constraints
- [ ] PRD: user journeys, functional requirements, NFRs, MVP scope
- [ ] Architecture: tech stack ADR, data model, API design, security
- [ ] Epics/Stories: all stories have acceptance criteria and tasks
- [ ] Config: `_bmad/config.yaml` has stack defined

### Step 4: Identify Risks and Gaps

Flag:
- Ambiguous acceptance criteria
- Missing error handling specifications
- Unclear data ownership or privacy requirements
- Unresolved open questions from any artifact
- Missing dependency specifications
- Architecture decisions that conflict with requirements

### Step 5: Render Decision

**GO** — All required artifacts complete, traceability verified, no blocking gaps. Proceed to sprint planning.

**CONDITIONAL GO** — Minor gaps that can be resolved during implementation. List conditions that must be addressed in Sprint 1.

**NO-GO** — Blocking gaps that must be resolved before implementation. List specific issues and which agent/workflow should fix them.

### Step 6: Save and Update Status

1. Append decision summary to `_bmad/context.md`
2. Update `_bmad/bmm-workflow-status.yaml`: set `phase_3_solutioning.readiness_check` to `"complete"` (if GO), set `phase_3_solutioning.status` to `"complete"`, set `current_phase` to `4`
3. If GO: "Ready for implementation! Next: sprint planning (`/bmad-cowork:sprint-plan`)"
4. If NO-GO: specify exactly which workflows to re-run
