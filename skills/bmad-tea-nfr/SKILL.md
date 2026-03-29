# BMad TEA NFR Assessment

Use when assessing non-functional requirements: performance, security, accessibility, reliability, and scalability.

Trigger with: "NFR assessment", "non-functional requirements", "performance assessment", "security assessment"

## Instructions

**Agent:** TEA (Murat)
**Input:** Architecture doc, PRD (NFR section)
**Output:** NFR assessment report

### Step 1: Load NFR Specifications

Read the NFR section from the PRD and architecture doc. Identify all stated targets.

### Step 2: Assess Each NFR Category

**Performance:**
- Response time targets defined? Measurable?
- Load/stress test approach identified?
- Performance budgets set (bundle size, API latency, DB query time)?

**Security:**
- OWASP Top 10 mitigations in architecture?
- Auth/authz model defined and testable?
- Data encryption approach specified?
- Input validation strategy documented?

**Accessibility:**
- WCAG compliance level stated?
- Automated a11y testing planned?
- Keyboard navigation requirements defined?

**Reliability:**
- Uptime targets defined?
- Error budget established?
- Graceful degradation strategy?
- Backup and recovery plan?

**Scalability:**
- Growth targets quantified?
- Horizontal vs vertical scaling approach?
- Database scaling strategy?
- Caching strategy?

### Step 3: Gap Analysis

For each category, flag:
- Missing targets (no measurable criteria)
- Untestable requirements (vague or subjective)
- Missing test approach (target exists but no way to verify)

### Step 4: Recommendations

Provide specific recommendations for each gap, with priority based on risk.

### Step 5: Save

Save to `_bmad-output/planning-artifacts/nfr-assessment.md`.
