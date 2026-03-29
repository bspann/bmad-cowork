# BMad Init

Use when setting up a new project for BMad workflows. Creates the directory structure, config, and status tracking files.

Trigger with: "init bmad", "initialize project", "set up bmad", "start new project"

## Instructions

### Step 1: Create Directory Structure

Create the following directories and files in the project root:

```
_bmad/
├── config.yaml              # Project configuration
├── bmm-workflow-status.yaml  # Workflow tracking (Phase 1-3)
└── context.md                # Accumulated project context

_bmad-output/
├── planning-artifacts/       # Briefs, PRDs, architecture, UX, epics
└── implementation-artifacts/
    ├── stories/              # Individual story files
    ├── quick-specs/          # Quick Flow tech specs
    └── tests/                # Test artifacts (TEA)

docs/                         # Project documentation
```

### Step 2: Create Config File

Create `_bmad/config.yaml` with this template (ask the user to fill in):

```yaml
project:
  name: "[PROJECT NAME]"
  description: "[Brief description]"
  type: "greenfield"  # greenfield | brownfield

stack:
  frontend: ""    # e.g., "Next.js, Tailwind, ShadCN"
  backend: ""     # e.g., "Supabase, Node.js"
  language: ""    # e.g., "TypeScript"
  database: ""    # e.g., "PostgreSQL"
  hosting: ""     # e.g., "Vercel, AWS"

planning:
  track: "bmad-method"  # quick-flow | bmad-method | enterprise
  
modules:
  bmm: true       # Core development lifecycle
  tea: false      # Test Engineering Architect
  bmb: false      # BMad Builder
```

### Step 3: Create Workflow Status

Create `_bmad/bmm-workflow-status.yaml`:

```yaml
version: "1.0"
project_key: "default"
current_phase: 1
planning_track: "bmad-method"

phases:
  phase_1_analysis:
    status: "not_started"
    project_brief: "not_started"
  phase_2_planning:
    status: "not_started"  
    prd: "not_started"
  phase_3_solutioning:
    status: "not_started"
    architecture: "not_started"
    ux_design: "not_started"
    epics_and_stories: "not_started"
    readiness_check: "not_started"
  phase_4_implementation:
    status: "not_started"
    sprint_planning: "not_started"

completed_workflows: []
active_workflow: null
blockers: []
```

### Step 4: Create Context File

Create `_bmad/context.md`:

```markdown
# Project Context

This file accumulates key decisions and context as you progress through BMad workflows.
Agents read this file to stay informed about project-wide decisions.

## Key Decisions

(Updated automatically as workflows complete)

## Open Questions

(Track unresolved questions here)
```

### Step 5: Ask About Modules

Ask the user which modules they want to enable:
- **BMM** (always on) — core development lifecycle
- **TEA** — test engineering architect (recommended for projects with testing needs)
- **BMB** — BMad builder (for teams who want to create custom agents/workflows)

### Step 6: Announce Completion

Tell the user:
1. Project is initialized
2. Recommend running `bmad-help` to see what to do next
3. Or jump straight to `/bmad-cowork:brief` to start with a project brief
