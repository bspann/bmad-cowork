---
name: builder-create-workflow
description: "Design and create a new BMad workflow with steps, templates, and checklists."
---

Use when creating a new workflow (skill) with structured steps, templates, and checklists.

Trigger with: "create workflow", "build workflow", "new skill", "custom workflow"

## Instructions

**Agent:** BMad Builder (Brix)
**Input:** User's description of the workflow
**Output:** SKILL.md file in `skills/[workflow-name]/`

### Step 1: Interview

Ask the user:
1. **Purpose** — What does this workflow accomplish?
2. **Trigger** — When should it activate? What phrases invoke it?
3. **Agent** — Which agent runs this workflow?
4. **Inputs** — What files or information does it need?
5. **Outputs** — What artifacts does it produce?
6. **Steps** — What is the sequence of actions?

### Step 2: Design the Skill

Create a SKILL.md following BMad conventions:

```markdown
# [Workflow Name]

[Description paragraph with trigger phrases]

Trigger with: "[phrases]"

## Instructions

**Agent:** [Agent Name]
**Input:** [Input files/information]
**Output:** [Output artifacts with paths]

### Step 1: [Title]
[Instructions]

### Step 2: [Title]
[Instructions]

...
```

### Step 3: Validate

- [ ] Clear trigger description at the top
- [ ] Agent assignment specified
- [ ] Input/output paths defined
- [ ] Steps are sequential and actionable
- [ ] Each step has clear success criteria
- [ ] Output location follows `_bmad-output/` convention

### Step 4: Save

Create directory `skills/[workflow-name]/` and save SKILL.md. Inform user to run `/reload-plugins`.
