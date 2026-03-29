---
name: dev
description: "Implement a story using red-green-refactor TDD. Task-by-task with test verification."
---

Use when implementing a prepared story. Follows red-green-refactor TDD methodology, completing tasks one at a time with test verification.

Trigger with: "implement story", "dev story", "develop [STORY-ID]", "start coding"

## Instructions

**Agent:** Developer (Devon)
**Input:** `_bmad-output/implementation-artifacts/stories/[STORY-ID].md`
**Output:** Implemented code + tests

### Step 1: Load Story

Read the story file. If not specified, read `_bmad/sprint-status.yaml` to find the next `"todo"` story. Load the story file from `_bmad-output/implementation-artifacts/stories/`.

Verify all dependencies are complete (status `"complete"` in sprint-status.yaml). If not, HALT.

### Step 2: Update Status

Update sprint-status.yaml: set story status to `"in_progress"`.

### Step 3: Implement Task by Task

For each task in the story file:

**RED** — Write a failing test that describes the expected behavior.
```
Run the test. Verify it fails for the right reason.
```

**GREEN** — Write the minimum code to make the test pass.
```
Run the test. Verify it passes.
Run the full test suite. Verify nothing else broke.
```

**REFACTOR** — Improve the code without changing behavior.
```
Run the full test suite. Verify everything still passes.
```

Commit after each task with a descriptive message: `feat(STORY-ID): task N - [description]`

### Step 4: Verify Acceptance Criteria

After all tasks are complete, verify every acceptance criterion from the story file:

For each criterion:
1. Read the Given/When/Then
2. Verify the implementation satisfies it
3. If a criterion is not met, implement the missing piece
4. Mark each criterion as verified

### Step 5: Final Checks

- [ ] All tasks implemented
- [ ] All tests passing
- [ ] All acceptance criteria verified
- [ ] No console errors or warnings
- [ ] No hardcoded values or secrets
- [ ] Error handling in place

### Step 6: Handle Blockers

If at any point you cannot proceed:

```
HALT: [What is blocking you]
Context: [What you need to continue]
Recommendation: [Suggested resolution]
```

Update sprint-status.yaml: set story status to `"blocked"` with blocker description.

### Step 7: Announce Completion

1. Update sprint-status.yaml: set story status to `"review"`
2. Update the story file: set Status to `REVIEW`
3. Announce: "Story [ID] implementation complete. Ready for code review: `/bmad-cowork:review` for [STORY-ID]"
