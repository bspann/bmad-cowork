# BMad TEA ATDD

Use when writing Acceptance Test-Driven Development specifications before implementation. Run per story when helpful in Phase 4.

Trigger with: "ATDD", "acceptance tests first", "write acceptance tests", "BDD specs"

## Instructions

**Agent:** TEA (Murat)
**Input:** Story file with acceptance criteria
**Output:** Executable acceptance test specifications

### Step 1: Load Story

Read the story file. Extract all acceptance criteria (Given/When/Then).

### Step 2: Expand Acceptance Criteria

For each criterion, expand into detailed test scenarios:
- Happy path (the criterion as stated)
- Edge cases (boundary values, empty inputs, max limits)
- Error cases (invalid input, unauthorized access, network failures)
- Concurrent scenarios (if applicable)

### Step 3: Write Executable Specs

Create test files that express the acceptance criteria as executable tests. Tests should:
- Be written BEFORE implementation (they will fail initially)
- Use descriptive names that read like requirements
- Include all setup, action, and assertion steps
- Be independent and idempotent

### Step 4: Validate with User

Present the expanded test scenarios. Confirm they accurately capture the intended behavior.

### Step 5: Save

Save test spec files alongside the story. These become the contract that dev-story must satisfy.
