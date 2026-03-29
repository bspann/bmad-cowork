---
name: tea-test-design
description: "Create risk-based test designs at system level (Phase 3) or per-epic (Phase 4)."
---

Use when creating risk-based test designs at the system level (Phase 3) or per-epic level (Phase 4).

Trigger with: "test design", "test strategy", "test plan", "risk-based testing"

## Instructions

**Agent:** TEA (Murat)
**Input:** Architecture doc, PRD, optionally epics/stories
**Output:** `_bmad-output/planning-artifacts/test-strategy.md` or `_bmad-output/implementation-artifacts/tests/test-design-[scope].md`

### Step 1: Determine Scope

- **System-level** (Phase 3): Run once after architecture. Covers the entire system.
- **Epic-level** (Phase 4): Run per epic during implementation. Covers specific feature areas.

### Step 2: Load Context

Read architecture.md and PRD. For epic-level, also read the specific epic from epics-and-stories.md.

### Step 3: Risk Assessment

For each feature area or component, assess:
- **Probability** of defects (High/Medium/Low) based on complexity, integrations, novelty
- **Impact** of defects (Critical/High/Medium/Low) based on user impact, data integrity, security
- **Risk Priority** = Probability × Impact → P0 (Critical), P1 (High), P2 (Medium), P3 (Low)

### Step 4: Test Design

For each risk area, define:
- Test type (unit, integration, e2e, performance, security)
- Test scenarios with Given/When/Then
- Data requirements (fixtures, factories, mocks)
- Environment requirements
- Priority based on risk assessment

### Step 5: Coverage Matrix

Create a traceability matrix:

| Requirement | Risk | Test Type | Test Scenarios | Priority |
|-------------|------|-----------|---------------|----------|

### Step 6: Save Output

System-level: save to `_bmad-output/planning-artifacts/test-strategy.md`
Epic-level: save to `_bmad-output/implementation-artifacts/tests/test-design-[epic-id].md`
