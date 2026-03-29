# BMad TEA Automate

Use when implementing test automation for features. The most commonly used TEA workflow.

Trigger with: "automate tests", "test automation", "write tests", "implement tests"

## Instructions

**Agent:** TEA (Murat)
**Input:** Test design document, story files, existing codebase
**Output:** Automated test files

### Step 1: Load Context

Read the relevant test design document. Read the story file if automating for a specific story. Detect the test framework from `_bmad/config.yaml` or project files (package.json, etc.).

### Step 2: Select Tests to Automate

From the test design, select tests by priority:
1. P0 (Critical) — automate first, no exceptions
2. P1 (High) — automate in current sprint
3. P2 (Medium) — automate if time permits
4. P3 (Low) — defer or manual test

### Step 3: Implement Tests

For each test scenario:

1. **Set up test structure** — describe block, test fixtures, data factories
2. **Implement Given** — preconditions, test data, mocks/stubs
3. **Implement When** — actions, API calls, user interactions
4. **Implement Then** — assertions, expected outcomes, cleanup
5. **Run and verify** — test passes with correct implementation, fails without it

Follow test architecture patterns:
- Page Object Model for e2e tests
- Data factories for test data
- Fixtures for reusable setup
- Proper test isolation (no shared state between tests)

### Step 4: Verify Coverage

Check that automated tests cover the risk areas identified in the test design. Report any coverage gaps.

### Step 5: Save and Report

Save test files alongside the implementation code. Report: tests created, coverage achieved, any gaps remaining.
