# BMad TEA Trace

Use for traceability matrix creation and evidence-backed release gate (GO/NO-GO) decisions. Two-phase workflow: Phase 1 builds traceability, Phase 2 makes gate decision.

Trigger with: "traceability", "release gate", "go no-go", "release decision", "coverage trace"

## Instructions

**Agent:** TEA (Murat)
**Input:** All planning artifacts, test results, implementation status
**Output:** Traceability matrix + release gate decision

### Phase 1: Traceability Matrix

#### Step 1: Map Requirements to Tests

Create a matrix linking:
- PRD requirements → stories → tests → test results

```markdown
| Req ID | Story | Test File | Test Status | Coverage |
|--------|-------|-----------|-------------|----------|
| FR-001 | STORY-01-01 | auth.test.ts | ✅ Pass | Full |
| FR-002 | STORY-01-02 | api.test.ts | ✅ Pass | Partial |
| FR-003 | STORY-02-01 | - | ❌ No tests | None |
```

#### Step 2: Identify Gaps

Flag requirements with:
- No corresponding tests
- Failing tests
- Partial coverage only

### Phase 2: Release Gate Decision

#### Step 3: Assess Release Readiness

Evaluate:
- P0 requirements: 100% covered and passing (mandatory)
- P1 requirements: 90%+ covered and passing (recommended)
- P2 requirements: coverage documented, gaps accepted
- P3 requirements: no coverage requirement
- All stories complete in sprint-status.yaml
- No open blockers
- Code review passed for all stories

#### Step 4: Render Decision

**GO** — All P0 covered, P1 threshold met, no blocking issues.
**CONDITIONAL GO** — Minor gaps with documented risk acceptance.
**NO-GO** — P0 gaps, critical failures, or unresolved blockers.

#### Step 5: Save

Save traceability matrix and gate decision to `_bmad-output/implementation-artifacts/tests/release-gate-[date].md`.
