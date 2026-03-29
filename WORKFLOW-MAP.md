# BMad Cowork — Workflow Map

The BMad Method follows 4 phases. Each phase produces artifacts that inform the next.

## Phase Overview

```
Phase 1          Phase 2         Phase 3              Phase 4
ANALYSIS    →    PLANNING   →    SOLUTIONING     →    IMPLEMENTATION
                                                      (repeat per story)
```

## Phase 1: Analysis (Optional)

```
┌─────────────────────────────┐
│  /bmad-cowork:brief         │
│  Agent: Analyst (Alex)      │
│  Output: project-brief.md   │
└──────────────┬──────────────┘
               ▼
         [Phase 2]
```

**Skip when:** Using Quick Flow track for small tasks.

## Phase 2: Planning

```
┌─────────────────────────────┐
│  /bmad-cowork:prd           │
│  Agent: PM (Patricia)       │
│  Output: prd.md             │
└──────────────┬──────────────┘
               ▼
         [Phase 3]
```

## Phase 3: Solutioning

```
┌─────────────────────────────┐
│  /bmad-cowork:architect     │
│  Agent: Architect (Archie)  │
│  Output: architecture.md    │
└──────────────┬──────────────┘
               │
     ┌─────────┼──────────┐
     ▼         ▼          ▼
┌─────────┐ ┌─────────┐ ┌──────────────┐
│ UX      │ │ TEA     │ │ TEA          │
│ Design  │ │ Test    │ │ Framework    │
│ (opt.)  │ │ Design  │ │ + CI (opt.)  │
└────┬────┘ └────┬────┘ └──────┬───────┘
     └─────────┬─┘             │
               ▼               │
┌─────────────────────────────┐│
│  /bmad-cowork:epics         ││
│  Agent: SM (Sam)            ││
│  Output: epics-and-stories  ││
└──────────────┬──────────────┘│
               ▼               │
┌─────────────────────────────┐│
│  /bmad-cowork:ready         ││
│  GO / NO-GO gate            ││
└──────────────┬──────────────┘│
               ▼               │
         [Phase 4] ◄───────────┘
```

## Phase 4: Implementation (Sprint Cycle)

```
┌───────────────────────────────────────┐
│  /bmad-cowork:sprint-plan             │
│  Agent: SM (Sam)                      │
│  Output: sprint-status.yaml           │
└──────────────────┬────────────────────┘
                   │
        ┌──────────▼──────────┐
        │  FOR EACH STORY:    │
        │                     │
        │  ┌────────────────┐ │
        │  │ create-story   │ │
        │  │ Agent: SM      │ │
        │  └───────┬────────┘ │
        │          ▼          │
        │  ┌────────────────┐ │
        │  │ dev-story      │ │
        │  │ Agent: Dev     │ │
        │  │ (red-green-    │ │
        │  │  refactor)     │ │
        │  └───────┬────────┘ │
        │          ▼          │
        │  ┌────────────────┐ │
        │  │ code-review    │ │
        │  │ Agent: Cora    │ │
        │  └───────┬────────┘ │
        │          │          │
        │     APPROVE?        │
        │     YES → complete  │
        │     NO → back to    │
        │           dev-story │
        │                     │
        └──────────┬──────────┘
                   │
        ┌──────────▼──────────┐
        │  SPRINT COMPLETE?   │
        │  YES → retro        │
        │  NO → next story    │
        └──────────┬──────────┘
                   ▼
        ┌─────────────────────┐
        │  /bmad-cowork:retro │
        │  Agent: SM (Sam)    │
        │  Plan next sprint   │
        └─────────────────────┘
```

## Quick Flow Track (Skip Phases 1-3)

```
┌─────────────────────────────────────┐
│  /bmad-cowork:quick-dev             │
│  Agent: Quick Flow Solo Dev (Barry) │
│                                     │
│  Step 1: Quick Spec (15-30 min)     │
│  Step 2: Implement (hours-days)     │
│  Step 3: Self-Review                │
│  Step 4: Ship                       │
└─────────────────────────────────────┘
```

## TEA Integration Points

| TEA Workflow | When to Run | Phase |
|-------------|------------|-------|
| `framework` | Once, after architecture | 3 |
| `ci` | Once, after framework | 3 |
| `test-design` (system) | Once, after architecture | 3 |
| `nfr` | Once, after architecture | 3 |
| `test-design` (epic) | Per epic, during implementation | 4 |
| `atdd` | Per story, before dev (optional) | 4 |
| `automate` | Per story, during dev | 4 |
| `test-review` | Per sprint, audit quality (optional) | 4 |
| `trace` | At release gate, for GO/NO-GO | 4 |

## Planning Tracks

| Track | When to Use | Phases Used |
|-------|------------|-------------|
| **Quick Flow** | Bug fixes, small features, prototyping | 4 only |
| **BMad Method** | Standard greenfield/brownfield projects | 1-4 |
| **Enterprise** | Complex projects with compliance/security | 1-4 (deeper) |

## File Locations

| Artifact | Path |
|----------|------|
| Config | `_bmad/config.yaml` |
| Phase 1-3 Status | `_bmad/bmm-workflow-status.yaml` |
| Phase 4 Status | `_bmad/sprint-status.yaml` |
| Project Context | `_bmad/context.md` |
| Project Brief | `_bmad-output/planning-artifacts/project-brief.md` |
| PRD | `_bmad-output/planning-artifacts/prd.md` |
| Architecture | `_bmad-output/planning-artifacts/architecture.md` |
| UX Design | `_bmad-output/planning-artifacts/ux-design.md` |
| Epics & Stories | `_bmad-output/planning-artifacts/epics-and-stories.md` |
| Test Strategy | `_bmad-output/planning-artifacts/test-strategy.md` |
| Story Files | `_bmad-output/implementation-artifacts/stories/` |
| Quick Specs | `_bmad-output/implementation-artifacts/quick-specs/` |
| Test Artifacts | `_bmad-output/implementation-artifacts/tests/` |
