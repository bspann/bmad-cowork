---
name: builder-create-module
description: "Create a complete BMad module packaging agents, workflows, and knowledge together."
---

Use when creating a complete BMad module — a coherent package of agents, workflows, and knowledge for a specific domain.

Trigger with: "create module", "build module", "new module", "custom module"

## Instructions

**Agent:** BMad Builder (Brix)
**Input:** User's description of the domain and needs
**Output:** Complete module directory structure with agents, skills, and references

### Step 1: Interview

Ask the user:
1. **Domain** — What domain does this module serve? (e.g., game dev, DevOps, compliance)
2. **Agents** — What specialist personas are needed?
3. **Workflows** — What workflows does the domain require?
4. **Knowledge** — What domain-specific knowledge, templates, or checklists are needed?
5. **Integration** — How does this module interact with BMM core workflows?

### Step 2: Design Module Architecture

Plan the module structure:
```
module-name/
├── agents/
│   ├── [agent-1].md
│   └── [agent-2].md
├── skills/
│   ├── [workflow-1]/SKILL.md
│   └── [workflow-2]/SKILL.md
├── references/
│   ├── templates/
│   └── checklists/
└── README.md
```

### Step 3: Create Agents

For each agent, follow the Create Agent workflow to build a complete agent definition.

### Step 4: Create Workflows

For each workflow, follow the Create Workflow process to build SKILL.md files.

### Step 5: Create Knowledge Base

Build templates, checklists, and reference documents specific to the domain.

### Step 6: Integration Points

Define how the module integrates with BMM:
- Which BMM phases does it participate in?
- Which BMM agents does it collaborate with in party mode?
- Does it add new menu items to existing agents?

### Step 7: Create Module README

Document the module: purpose, agents, workflows, installation, usage.

### Step 8: Save and Test

Save all files. Test each agent and workflow in a Cowork session.
