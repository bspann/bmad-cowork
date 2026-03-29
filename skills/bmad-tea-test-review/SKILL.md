# BMad TEA Test Review

Use when auditing test quality and identifying gaps in test coverage. Optional Phase 4 workflow.

Trigger with: "test review", "audit tests", "test quality", "review test coverage"

## Instructions

**Agent:** TEA (Murat)
**Input:** Existing test files, test design documents
**Output:** Test quality audit report

### Step 1: Inventory Tests

Scan the codebase for test files. Categorize by: unit, integration, e2e, performance, security.

### Step 2: Assess Test Quality

For each test file, evaluate:
- **Meaningful assertions** — do tests verify actual behavior or just not-crashing?
- **Independence** — can tests run in any order without shared state?
- **Determinism** — do tests always produce the same result?
- **Speed** — are unit tests fast? Are slow tests properly categorized?
- **Readability** — can someone understand intent from the test name and structure?
- **Coverage** — do tests cover happy path, edge cases, and error cases?

### Step 3: Gap Analysis

Compare existing tests against:
- Test design document risk areas
- Acceptance criteria from story files
- Architecture-significant components

Identify uncovered risk areas.

### Step 4: Generate Report

```markdown
# Test Quality Audit: [Date]

## Summary
- Total tests: [N]
- Unit: [N] | Integration: [N] | E2E: [N]
- Quality score: [A-F]

## Issues Found
### [BLOCKER/WARNING/SUGGESTION]: [Title]
...

## Coverage Gaps
- [Gap 1: description and risk level]

## Recommendations
1. [Recommendation with priority]
```

### Step 5: Save

Save report to `_bmad-output/implementation-artifacts/tests/test-review-[date].md`.
