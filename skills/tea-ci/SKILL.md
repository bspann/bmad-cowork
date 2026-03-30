---
name: tea-ci
description: "Configure CI/CD pipeline testing stages, quality gates, and artifact collection."
---

Use when configuring CI/CD pipeline testing. Run once in Phase 3 after test framework is set up.

Trigger with: "CI pipeline testing", "configure CI tests", "CI/CD testing", "pipeline setup"

## Instructions

**Agent:** TEA (Murat)
**Input:** Test framework configuration, `_bmad/config.yaml`
**Output:** CI configuration files

### Step 1: Detect CI Platform

From config.yaml or project files, detect: GitHub Actions, GitLab CI, Jenkins, Azure DevOps, CircleCI, or Harness.

### Step 2: Design Pipeline Stages

```
lint → unit tests → integration tests → build → e2e tests → deploy (staging) → smoke tests
```

### Step 3: Configure Test Stages

For each stage:
- Commands to run
- Parallelization strategy
- Timeout limits
- Retry policy for flaky tests
- Artifact collection (coverage reports, screenshots, logs)
- Failure handling (fail-fast vs continue)

### Step 4: Generate CI Config

Create the CI configuration file (e.g., `.github/workflows/ci.yml`) with all test stages configured.

### Step 5: Quality Gates

Define pass/fail criteria:
- Minimum code coverage threshold
- Zero P0/P1 test failures
- Performance budget compliance
- Security scan results

### Step 6: Save

Save CI config files. Document pipeline in `_bmad-output/implementation-artifacts/tests/ci-setup.md`.
