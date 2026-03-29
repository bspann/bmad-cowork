# BMad Method for Claude Cowork

A Claude Cowork plugin that brings the [BMad Method](https://github.com/bmad-code-org/BMAD-METHOD) to Anthropic's desktop agent. Ship production-quality software with specialized AI agents — Analyst, PM, Architect, Developer, Code Reviewer, Test Architect, and more — all orchestrated from Claude Cowork or Claude Code.

## What Is This?

The BMad Method is a structured, AI-driven approach to software development. It uses specialized agent personas to take a product idea through a complete lifecycle:

**Brief → PRD → Architecture → Stories → Implementation → Review → Ship**

This plugin adapts BMad to run natively as a **Claude Code / Cowork plugin**, using:

- **Sub-agents** for parallel work (Cowork spins up specialist agents automatically)
- **Skills** that fire contextually based on what you're doing
- **Slash commands** for explicit workflow invocation
- **File-based state** so sessions can crash and resume without losing context

## Modules Included

| Module | Agents | Workflows | Purpose |
|--------|--------|-----------|---------|
| **BMM** (Core) | 8 agents | 16 workflows | Full development lifecycle: analysis → planning → architecture → implementation |
| **TEA** | 1 agent (Murat) | 9 workflows | Risk-based test strategy, automation, CI, release gates |
| **BMB** | 1 agent (Brix) | 3 workflows | Create custom agents, workflows, and modules |

## Quick Start

### Prerequisites

- [Claude Desktop](https://claude.com/download) with Cowork enabled (Pro, Max, Team, or Enterprise plan)
- OR [Claude Code](https://code.claude.com) CLI installed

### Install

**Option A: From a marketplace (when published)**
```bash
claude plugin install bmad-cowork
```

**Option B: Local install from GitHub**
```bash
git clone https://github.com/YOUR_USERNAME/bmad-cowork.git
cd your-project
claude --plugin-dir /path/to/bmad-cowork
```

**Option C: Test locally during development**
```bash
claude --plugin-dir ./bmad-cowork
```

### First Run

1. Open Cowork or Claude Code in your project
2. Type `/bmad-cowork:init` to scaffold your project
3. Type `/bmad-cowork:help` to see what to do next

## Usage

### Start a New Project (Full BMad Method)

```
/bmad-cowork:init          # Set up project structure
/bmad-cowork:brief         # Create project brief (Phase 1)
/bmad-cowork:prd           # Create PRD (Phase 2)
/bmad-cowork:architect     # Design architecture (Phase 3)
/bmad-cowork:ux-design     # UX design spec (Phase 3, optional)
/bmad-cowork:epics         # Create epics & stories (Phase 3)
/bmad-cowork:ready         # GO/NO-GO readiness check
/bmad-cowork:sprint-plan   # Plan Sprint 1 (Phase 4)
/bmad-cowork:dev           # Implement a story
/bmad-cowork:review        # Code review
/bmad-cowork:retro         # Sprint retrospective
```

### Quick Fix or Small Feature

```
/bmad-cowork:quick-dev     # Spec → Build → Review in one workflow
```

### Check Status Anytime

```
/bmad-cowork:status        # Where am I? What's next?
/bmad-cowork:help          # Interactive guidance
```

## Agents

| Agent | Name | Specialty |
|-------|------|-----------|
| Analyst | Alex | Market analysis, project briefs, discovery research |
| PM | Patricia | PRDs, requirements, user journeys, MVP scoping |
| Architect | Archie | System design, tech stack, data models, APIs, security |
| UX Designer | Uma | Screen specs, user flows, component libraries, accessibility |
| Scrum Master | Sam | Epics, stories, sprint planning, status tracking, retrospectives |
| Developer | Devon | TDD implementation, red-green-refactor, task-by-task coding |
| Code Reviewer | Cora | Adversarial review (3-10 issues minimum), APPROVE/REQUEST_CHANGES |
| TEA | Murat | Test strategy, automation, frameworks, CI, release gates |
| Quick Flow | Barry | Rapid bug fixes and small features without full planning |
| BMad Builder | Brix | Create custom agents, workflows, and modules |
| Tech Writer | Tanya | API docs, user guides, README, project documentation |

## Architecture

```
bmad-cowork/
├── .claude-plugin/
│   └── plugin.json              # Plugin manifest
├── agents/                      # Sub-agent definitions (11 agents)
│   ├── analyst.md
│   ├── pm.md
│   ├── architect.md
│   ├── ux-designer.md
│   ├── sm.md
│   ├── dev.md
│   ├── code-reviewer.md
│   ├── tea.md
│   ├── quick-flow-solo-dev.md
│   ├── bmad-builder.md
│   └── tech-writer.md
├── commands/                    # Slash commands (14 commands)
│   ├── init.md
│   ├── brief.md
│   ├── prd.md
│   ├── architect.md
│   ├── ux-design.md
│   ├── epics.md
│   ├── ready.md
│   ├── sprint-plan.md
│   ├── dev.md
│   ├── review.md
│   ├── status.md
│   ├── help.md
│   ├── retro.md
│   └── quick-dev.md
├── skills/                      # Workflow skills (28 skills)
│   ├── bmad-help/SKILL.md
│   ├── bmad-init/SKILL.md
│   ├── bmad-create-project-brief/SKILL.md
│   ├── bmad-create-prd/SKILL.md
│   ├── bmad-create-architecture/SKILL.md
│   ├── bmad-create-ux-design/SKILL.md
│   ├── bmad-create-epics-and-stories/SKILL.md
│   ├── bmad-check-implementation-readiness/SKILL.md
│   ├── bmad-sprint-planning/SKILL.md
│   ├── bmad-create-story/SKILL.md
│   ├── bmad-dev-story/SKILL.md
│   ├── bmad-code-review/SKILL.md
│   ├── bmad-quick-dev/SKILL.md
│   ├── bmad-retrospective/SKILL.md
│   ├── bmad-workflow-status/SKILL.md
│   ├── bmad-correct-course/SKILL.md
│   ├── bmad-tea-test-design/SKILL.md
│   ├── bmad-tea-automate/SKILL.md
│   ├── bmad-tea-framework/SKILL.md
│   ├── bmad-tea-atdd/SKILL.md
│   ├── bmad-tea-ci/SKILL.md
│   ├── bmad-tea-test-review/SKILL.md
│   ├── bmad-tea-trace/SKILL.md
│   ├── bmad-tea-nfr/SKILL.md
│   ├── bmad-tea-teach-me/SKILL.md
│   ├── bmad-builder-create-agent/SKILL.md
│   ├── bmad-builder-create-workflow/SKILL.md
│   └── bmad-builder-create-module/SKILL.md
├── references/
│   ├── templates/               # Document templates
│   │   ├── project-brief-template.md
│   │   ├── prd-template.md
│   │   ├── architecture-template.md
│   │   ├── story-template.md
│   │   └── ux-design-template.md
│   └── checklists/
│       └── definition-of-done.md
├── hooks/
│   └── hooks.json
├── README.md
├── WORKFLOW-MAP.md
└── LICENSE
```

## How It Works

### State Management

All state lives in files — not in memory:

- `_bmad/bmm-workflow-status.yaml` — tracks Phase 1-3 progress
- `_bmad/sprint-status.yaml` — tracks Phase 4 sprint/story progress
- `_bmad/config.yaml` — project configuration
- `_bmad/context.md` — accumulated decisions and context

This means Cowork sessions can end and resume without losing progress.

### Planning Tracks

| Track | When to Use | Phases |
|-------|------------|--------|
| **Quick Flow** | Bug fixes, small features, prototyping | Phase 4 only |
| **BMad Method** | Standard greenfield/brownfield projects | Phases 1-4 |
| **Enterprise** | Complex projects with compliance/security needs | Phases 1-4 (deeper) |

### Story Lifecycle

Each story follows this cycle:
```
create-story → dev-story (red-green-refactor) → code-review → complete
                                                      ↓
                                              REQUEST_CHANGES → fix → re-review
```

## Comparison with Original BMad

| Feature | BMad (Claude Code) | BMad Cowork |
|---------|-------------------|-------------|
| Runtime | Claude Code CLI | Claude Cowork Desktop + Claude Code |
| Agent execution | Single session with persona switching | Plugin sub-agents (isolated) |
| Installation | `npx bmad-method install` | `claude plugin install` |
| Workflow format | YAML + step files | SKILL.md (markdown native) |
| Non-developer friendly | No (CLI required) | Yes (Cowork GUI) |
| Parallel work | Sequential | Sub-agents can run in parallel |

## Credits

- [BMad Method](https://github.com/bmad-code-org/BMAD-METHOD) by BMad Code — the original framework
- [BMad Method TEA](https://github.com/bmad-code-org/bmad-method-test-architecture-enterprise) — Test Engineering Architect module
- [BMad Builder](https://github.com/bmad-code-org/bmad-builder) — agent and workflow creation tools
- Inspired by [ErwanLorteau/BMAD_Openclaw](https://github.com/ErwanLorteau/BMAD_Openclaw) — the OpenClaw adaptation

## Contributing

Contributions welcome! See the plugin structure above. To add a new agent, workflow, or module:

1. Fork this repo
2. Add your agent in `agents/`, skill in `skills/`, and command in `commands/`
3. Test with `claude --plugin-dir ./bmad-cowork`
4. Submit a PR

## License

MIT — see [LICENSE](LICENSE)
