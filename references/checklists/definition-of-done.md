# BMad Definition of Done Checklists

## Phase 1: Analysis — Project Brief

- [ ] Problem statement is specific and validated
- [ ] Target users identified with key characteristics
- [ ] Value proposition articulated clearly
- [ ] 3-5 key features identified at high level
- [ ] Success metrics defined with measurable targets
- [ ] Competitive landscape analyzed
- [ ] Constraints documented (timeline, budget, technical, regulatory)
- [ ] Risks and open questions listed
- [ ] Recommended planning track selected with justification
- [ ] User has reviewed and approved the brief

## Phase 2: Planning — PRD

- [ ] Executive summary written for stakeholder audience
- [ ] Product vision extends beyond v1
- [ ] Key differentiators articulated
- [ ] User personas have goals, frustrations, and context
- [ ] User journeys cover happy path, alternates, and errors
- [ ] All functional requirements have unique IDs
- [ ] Requirements prioritized (MoSCoW)
- [ ] Every requirement has acceptance criteria (Given/When/Then)
- [ ] Non-functional requirements cover performance, security, scalability, accessibility
- [ ] MVP scope clearly defined — explicit in/out
- [ ] Dependencies and assumptions documented
- [ ] Open questions tracked with owners
- [ ] User has reviewed and approved the PRD

## Phase 3: Solutioning — Architecture

- [ ] Tech stack selected with ADR justification
- [ ] System architecture components and boundaries defined
- [ ] Communication patterns specified (sync, async, real-time)
- [ ] Data model with entities, relationships, and key fields
- [ ] API design with endpoint inventory
- [ ] Authentication and authorization flow defined
- [ ] Security architecture addresses OWASP Top 10
- [ ] Infrastructure and deployment approach defined
- [ ] CI/CD pipeline approach specified
- [ ] Performance considerations documented
- [ ] User has reviewed and approved the architecture

## Phase 3: Solutioning — Epics & Stories

- [ ] All PRD requirements map to at least one story
- [ ] All stories trace to architecture components
- [ ] Every story has Given/When/Then acceptance criteria
- [ ] Stories are Independent, Negotiable, Valuable, Estimable, Small, Testable
- [ ] Dependencies between stories identified
- [ ] Stories ordered by dependency, risk, and value
- [ ] Effort estimates assigned (S/M/L)

## Phase 3: Solutioning — Readiness Check

- [ ] All required planning artifacts exist and are approved
- [ ] Traceability verified: requirements → stories → architecture
- [ ] No unresolved blocking questions
- [ ] Config.yaml has stack defined
- [ ] GO decision recorded

## Phase 4: Implementation — Per Story

- [ ] All tasks implemented following red-green-refactor
- [ ] All acceptance criteria verified
- [ ] All tests written and passing
- [ ] Code reviewed — 3-10 issues found and addressed
- [ ] No blockers remain (BLOCKERs resolved)
- [ ] Sprint status updated
- [ ] No console errors or warnings
- [ ] Error handling comprehensive
- [ ] No hardcoded values or secrets

## Phase 4: Implementation — Sprint Completion

- [ ] All sprint stories complete or explicitly carried over
- [ ] Sprint goal assessed (met / partially met / not met)
- [ ] Retrospective conducted
- [ ] Action items for next sprint defined
- [ ] Sprint status file updated
- [ ] Next sprint planned (if work remains)
