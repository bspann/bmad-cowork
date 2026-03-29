# Architecture Document: [Project Name]

> Created by: Architect Agent (Archie)
> Date: [Date]
> Status: DRAFT | APPROVED
> Based on: prd.md

## Overview

[High-level summary: what we're building, the architectural approach, and key technical decisions.]

## Architecture Decision Records

### ADR-001: Tech Stack Selection
- **Status:** Accepted
- **Context:** [Why this decision was needed]
- **Decision:** [What was decided]
- **Consequences:** [Positive and negative impacts]
- **Alternatives Considered:** [What else was evaluated and why it was rejected]

### ADR-002: [Decision Title]
[Same structure]

## Tech Stack

| Layer | Technology | Version | Justification |
|-------|-----------|---------|---------------|
| Frontend | [e.g., Next.js] | [version] | [Why this choice] |
| UI Library | [e.g., Tailwind + ShadCN] | | |
| Backend | [e.g., Node.js + Express] | | |
| Database | [e.g., PostgreSQL] | | |
| Auth | [e.g., Clerk, NextAuth] | | |
| Hosting | [e.g., Vercel] | | |
| CI/CD | [e.g., GitHub Actions] | | |

## System Architecture

### Component Diagram

[Describe components and their relationships textually:]

```
[Client] → [API Gateway] → [Application Server] → [Database]
                                    ↓
                            [Background Jobs]
                                    ↓
                          [External Services]
```

### Component Descriptions

| Component | Responsibility | Technology | Communication |
|-----------|---------------|-----------|---------------|
| [Name] | [What it does] | [Tech] | [How it talks to others] |

### Communication Patterns
- Synchronous: [REST/GraphQL for X]
- Asynchronous: [Message queue for Y]
- Real-time: [WebSocket for Z]

## Data Architecture

### Entity Descriptions

#### [Entity Name]
- **Purpose:** [What this entity represents]
- **Key Fields:**
  - `id` (UUID, PK)
  - `[field]` ([type], [constraints])
  - `created_at` (timestamp)
  - `updated_at` (timestamp)

#### [Entity Name]
[Same structure]

### Key Relationships
- [Entity A] has many [Entity B]
- [Entity B] belongs to [Entity A]
- [Entity C] has many-to-many with [Entity D] through [Join Table]

### Migration Strategy
[How database migrations will be managed: tool, versioning, rollback approach]

## API Design

### Endpoint Inventory

| Method | Path | Description | Auth | Request Body | Response |
|--------|------|-------------|------|-------------|----------|
| POST | /api/auth/login | User login | No | {email, password} | {token, user} |
| GET | /api/[resource] | List resources | Yes | - | {data: [...]} |

### Authentication
[Auth mechanism: JWT, session, OAuth — flow description]

### Error Response Format
```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Human-readable message",
    "details": [{"field": "email", "issue": "required"}]
  }
}
```

### Rate Limiting
[Strategy and limits per endpoint category]

### Versioning
[API versioning approach: URL, header, or none for v1]

## Infrastructure

### Environments
| Environment | Purpose | URL | Config |
|------------|---------|-----|--------|
| Development | Local dev | localhost:3000 | .env.local |
| Staging | Pre-production testing | staging.example.com | .env.staging |
| Production | Live users | example.com | .env.production |

### CI/CD Pipeline
[Pipeline stages and triggers]

### Monitoring and Alerting
[Tools, key metrics, alert thresholds]

### Backup and Recovery
[Backup frequency, retention, recovery procedure]

## Security Architecture

### Authentication Flow
[Step-by-step auth flow description]

### Authorization Model
[RBAC/ABAC — roles, permissions, enforcement points]

### Data Protection
- At rest: [Encryption method]
- In transit: [TLS configuration]
- Secrets: [Secrets management approach]

### Input Validation
[Validation strategy: where, how, what gets validated]

### OWASP Top 10 Mitigations
| Risk | Mitigation |
|------|-----------|
| Injection | [Approach] |
| Broken Auth | [Approach] |
| XSS | [Approach] |

## Performance Considerations

[Key performance decisions: caching strategy, query optimization, CDN, lazy loading, etc.]

## Open Architecture Questions

| # | Question | Impact | Resolution Plan |
|---|---------|--------|----------------|
| 1 | [Question] | [High/Med/Low] | [Plan] |
