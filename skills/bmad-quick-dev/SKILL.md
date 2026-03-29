# BMad Quick Dev

Use for bug fixes, small features, or rapid prototyping that doesn't need full planning phases. Combines spec + build + review in one workflow.

Trigger with: "quick dev", "quick fix", "bug fix", "small feature", "rapid prototype", "quick flow"

## Instructions

**Agent:** Quick Flow Solo Dev (Barry)
**Input:** User's description of the work
**Output:** Quick spec + implemented code + self-review

### Step 1: Assess Scope

Ask the user to describe the work. Classify:
- **Bug fix** (2-4 hours) → skip spec, go straight to fix
- **Small feature** (1-2 days) → lightweight spec first
- **Performance optimization** (1 day) → benchmark first, then optimize
- **API addition** (2-3 days) → spec the contract, then implement

If the work seems larger than 3 days, recommend escalating to full BMad Method.

### Step 2: Quick Spec (skip for bug fixes)

Write a lightweight spec (not a full PRD):

```markdown
# Quick Spec: [Title]

## What
[What needs to be built/fixed]

## Why
[Why this is needed now]

## How
[Technical approach in 3-5 bullet points]

## Acceptance Criteria
- [ ] [Criterion 1]
- [ ] [Criterion 2]
- [ ] [Criterion 3]

## Risks
- [Any risks or edge cases to watch for]
```

Save to `_bmad-output/implementation-artifacts/quick-specs/[date]-[slug].md`

### Step 3: Implement

Build it following red-green-refactor:
1. Write failing test
2. Make it pass
3. Refactor
4. Run full test suite
5. Repeat for each piece of functionality

### Step 4: Self-Review

Review your own code:
- [ ] All acceptance criteria met
- [ ] Tests passing
- [ ] Error handling in place
- [ ] No security issues
- [ ] No hardcoded values
- [ ] Performance acceptable

### Step 5: Announce Completion

Summarize what was done, what was tested, and any follow-up items.

### Escalation

If at any point the work grows beyond Quick Flow scope:
1. Stop
2. Save what you've learned as a project brief
3. Recommend: "This needs full BMad Method planning. Start with `/bmad-cowork:brief`"
