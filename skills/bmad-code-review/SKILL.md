# BMad Code Review

Use when reviewing implemented code for a completed story. Adversarial review that finds 3-10 issues minimum.

Trigger with: "code review", "review story", "review code", "review [STORY-ID]"

## Instructions

**Agent:** Code Reviewer (Cora)
**Input:** Story file + implemented code
**Output:** Review report with APPROVE or REQUEST_CHANGES

### Step 1: Load Context

Read the story file from `_bmad-output/implementation-artifacts/stories/[STORY-ID].md`. Read architecture from `_bmad-output/planning-artifacts/architecture.md`. Examine all code changes for this story.

### Step 2: Review Against Acceptance Criteria

For each acceptance criterion in the story:
- Verify it is fully implemented
- Verify tests exist that validate it
- Flag any criterion that is partially or not implemented

### Step 3: Architecture Compliance

Verify:
- Patterns from architecture doc are followed
- Data model matches architecture specification
- API contracts match architecture specification
- No unauthorized architectural deviations

### Step 4: Code Quality Review

Check for (find 3-10 issues minimum):
- **Security** — injection risks, auth bypasses, data exposure, XSS
- **Performance** — N+1 queries, unnecessary re-renders, memory leaks, missing indexes
- **Error Handling** — uncaught exceptions, missing error boundaries, silent failures
- **Code Quality** — DRY violations, SOLID violations, unclear naming, excessive complexity
- **Test Quality** — tests that don't test meaningful behavior, missing edge cases, brittle tests
- **Edge Cases** — empty states, boundary values, concurrent access, null handling

### Step 5: Classify Issues

For each issue found:

```markdown
### [BLOCKER/WARNING/SUGGESTION] #N: [Title]

**Location:** [file:line]
**Issue:** [Description of the problem]
**Impact:** [What could go wrong]
**Fix:** [Specific suggested fix with code example]
```

- **BLOCKER** — Must fix before merge. Correctness, security, or data integrity issues.
- **WARNING** — Should fix. Performance, maintainability, or robustness concerns.
- **SUGGESTION** — Could fix. Style, optimization, or best practice improvements.

### Step 6: Render Verdict

**APPROVE** — No blockers. Warnings and suggestions are noted but non-blocking. Story can proceed to complete.

**REQUEST_CHANGES** — One or more blockers found. Developer must address blockers and re-submit for review.

### Step 7: Save and Update Status

If APPROVED:
1. Update sprint-status.yaml: set story status to `"complete"`
2. Update story file: set Status to `COMPLETE`
3. Announce: "Story [ID] approved. Move to next story or run `/bmad-cowork:sprint-status`"

If REQUEST_CHANGES:
1. Keep sprint-status.yaml story status as `"review"`
2. Announce: "Story [ID] needs changes. [N] blockers found. Dev should fix and re-submit."
