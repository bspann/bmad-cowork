---
name: brief
description: "Create a project brief from a product idea. Phase 1 (Analysis) of the BMad Method."
---

Use when the user wants to explore a product idea and create a structured project brief. This is Phase 1 (Analysis) of the BMad Method.

Trigger with: "create brief", "project brief", "explore idea", "analyze concept", "Phase 1"

## Instructions

**Agent:** Analyst (Alex)
**Input:** User's product idea or concept
**Output:** `_bmad-output/planning-artifacts/project-brief.md`

### Step 1: Elicit the Vision

Ask the user about their product idea. Cover these areas — do NOT accept vague answers, probe deeper:

1. **Problem Statement** — What specific problem does this solve? Who has this problem?
2. **Target Users** — Who are the primary users? What are their characteristics?
3. **Value Proposition** — Why would someone use this instead of existing alternatives?
4. **Key Features** — What are the 3-5 most important capabilities? (high-level only)
5. **Success Metrics** — How will you measure if this product succeeds?
6. **Constraints** — Budget, timeline, team size, technical constraints?
7. **Competitive Landscape** — What alternatives exist today?

### Step 2: Research and Validate

Based on the user's answers:
- Identify competitive alternatives and market gaps
- Assess technical feasibility at a high level
- Flag risks, unknowns, and assumptions that need validation
- Identify potential regulatory or compliance considerations

### Step 3: Draft the Brief

Use this structure for the project brief:

```markdown
# Project Brief: [Project Name]

## Problem Statement
[Clear, specific description of the problem being solved]

## Target Users
[Primary and secondary user personas with key characteristics]

## Value Proposition
[Why this product, why now, what's different]

## Key Features (High-Level)
1. [Feature 1]
2. [Feature 2]
3. [Feature 3]

## Success Metrics
- [Metric 1 with target]
- [Metric 2 with target]

## Competitive Landscape
| Competitor | Strengths | Weaknesses | Our Differentiation |
|-----------|-----------|------------|---------------------|

## Constraints
- Timeline: [constraint]
- Budget: [constraint]
- Technical: [constraint]

## Risks and Open Questions
1. [Risk/question 1]
2. [Risk/question 2]

## Recommended Planning Track
[Quick Flow / BMad Method / Enterprise Method] — [justification]
```

### Step 4: Review with User

Present the draft brief. Ask for feedback. Iterate until approved.

### Step 5: Save and Update Status

1. Save to `_bmad-output/planning-artifacts/project-brief.md`
2. Update `_bmad/bmm-workflow-status.yaml`: set `phase_1_analysis.project_brief` to `"complete"` and `phase_1_analysis.status` to `"complete"`. Set `current_phase` to `2`.
3. Append key decisions to `_bmad/context.md`
4. Announce: "Project brief complete. Next: create PRD with `/bmad-cowork:prd`"
