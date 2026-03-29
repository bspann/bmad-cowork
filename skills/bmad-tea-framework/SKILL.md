---
name: tea-framework
description: "Set up test framework and infrastructure. Run once in Phase 3 after architecture."
---

Use when setting up the test framework and infrastructure for a project. Run once in Phase 3 after architecture is defined.

Trigger with: "test framework setup", "configure testing", "set up test infrastructure"

## Instructions

**Agent:** TEA (Murat)
**Input:** Architecture doc, `_bmad/config.yaml`
**Output:** Test framework configuration files, helper utilities

### Step 1: Detect Stack

Read architecture.md and config.yaml. Identify:
- Frontend framework (React, Vue, Next.js, etc.)
- Backend framework (Express, FastAPI, Django, etc.)
- Language (TypeScript, Python, Go, etc.)
- Existing test files (if brownfield)

### Step 2: Select Test Framework

Based on stack, recommend and configure:

| Stack | Unit Tests | Integration | E2E | API |
|-------|-----------|-------------|-----|-----|
| Next.js/React | Vitest | Vitest + Testing Library | Playwright | Supertest |
| Node/Express | Jest/Vitest | Supertest | Playwright | Supertest |
| Python/FastAPI | pytest | pytest + httpx | Playwright | pytest + httpx |
| Python/Django | pytest-django | pytest | Playwright | pytest |

### Step 3: Configure Framework

1. Install dependencies (show commands, don't auto-run)
2. Create configuration files (vitest.config.ts, playwright.config.ts, etc.)
3. Set up test directory structure
4. Create base test utilities (custom matchers, helpers)
5. Create initial fixture/factory patterns
6. Configure test reporters

### Step 4: CI Integration Notes

Provide guidance for CI pipeline integration (detailed setup via `bmad-tea-ci`):
- Test commands for each test type
- Parallelization recommendations
- Artifact collection (screenshots, videos, reports)

### Step 5: Save Configuration

Save all configuration files. Document setup in `_bmad-output/implementation-artifacts/tests/framework-setup.md`.
