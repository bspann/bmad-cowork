---
name: architect
description: "Design system architecture from an approved PRD. Phase 3 (Solutioning)."
---

Use when designing the system architecture based on an approved PRD. This is Phase 3 (Solutioning) of the BMad Method.

Trigger with: "create architecture", "system design", "tech stack", "data model", "Phase 3"

## Instructions

**Agent:** Architect (Archie)
**Input:** `_bmad-output/planning-artifacts/prd.md`, `_bmad-output/planning-artifacts/project-brief.md`
**Output:** `_bmad-output/planning-artifacts/architecture.md`

### Step 1: Load Context

Read the PRD and project brief. Read `_bmad/config.yaml` for any pre-selected stack preferences. Read `_bmad/context.md` for accumulated decisions.

### Step 2: Identify Architecturally Significant Requirements

From the PRD, extract:
- High-traffic endpoints or features
- Data consistency requirements
- Security-critical flows
- Integration points
- Performance targets
- Scale targets

### Step 3: Tech Stack Selection

Propose the tech stack with justification. Consider:
- Team familiarity (from config.yaml if specified)
- Ecosystem maturity and community support
- Licensing and cost implications
- Performance characteristics
- Hiring market

Create **ADR-001: Tech Stack Selection** with: Context, Decision, Consequences, Alternatives Considered.

### Step 4: System Architecture

Design high-level architecture:
- Component diagram (describe textually with clear boundaries)
- Communication patterns (sync/async, REST/GraphQL/events)
- Deployment topology (monolith, microservices, serverless)
- Authentication/authorization flow
- Error handling strategy

### Step 5: Data Architecture

Design the data model:
- Entity-relationship descriptions
- Key fields, types, and constraints
- Indexes and query patterns
- Migration strategy
- Data validation rules

### Step 6: API Design

Define the API surface:
- Endpoint inventory with methods, paths, request/response shapes
- Authentication mechanism
- Rate limiting strategy
- Versioning approach
- Error response format

### Step 7: Infrastructure

Define:
- Deployment environments (dev, staging, production)
- CI/CD pipeline approach
- Monitoring and alerting strategy
- Backup and disaster recovery
- Cost estimation

### Step 8: Security Architecture

Address:
- Authentication flow (OAuth, JWT, sessions)
- Authorization model (RBAC, ABAC)
- Data encryption (at rest, in transit)
- Input validation and sanitization
- Secrets management
- OWASP Top 10 mitigations

### Step 9: Draft the Architecture Document

Use this structure:

```markdown
# Architecture Document: [Project Name]

## Overview
[High-level architecture summary]

## Architecture Decision Records
### ADR-001: Tech Stack Selection
### ADR-002: [Next significant decision]

## Tech Stack
| Layer | Technology | Justification |
|-------|-----------|---------------|

## System Architecture
### Component Diagram
### Communication Patterns
### Deployment Topology

## Data Architecture
### Entity Descriptions
### Key Relationships
### Migration Strategy

## API Design
### Endpoint Inventory
### Authentication
### Error Handling

## Infrastructure
### Environments
### CI/CD
### Monitoring

## Security Architecture
### Authentication Flow
### Authorization Model
### Data Protection

## Performance Considerations

## Open Architecture Questions
```

### Step 10: Review and Finalize

Present to user. Iterate until approved. Architecture MUST be approved before epics/stories can be created.

### Step 11: Save and Update Status

1. Save to `_bmad-output/planning-artifacts/architecture.md`
2. Update `_bmad/bmm-workflow-status.yaml`: set `phase_3_solutioning.architecture` to `"complete"`
3. Append key ADRs to `_bmad/context.md`
4. Announce next steps: "Architecture complete. Options: UX design (`/bmad-cowork:ux-design`), TEA test design (`/bmad-cowork:tea-test-design`), or create epics (`/bmad-cowork:epics`)"
