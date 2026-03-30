---
name: ux-design
description: "Create UX design specifications including screens, flows, and components. Phase 3 (optional)."
---

Use when creating UX design specifications including screen layouts, user flows, and component definitions. Optional Phase 3 workflow — recommended for projects with user interfaces.

Trigger with: "create UX design", "design screens", "wireframes", "user flows", "component library"

## Instructions

**Agent:** UX Designer (Uma)
**Input:** `_bmad-output/planning-artifacts/prd.md`, `_bmad-output/planning-artifacts/architecture.md`
**Output:** `_bmad-output/planning-artifacts/ux-design.md`

### Step 1: Load Context

Read the PRD (for user journeys and requirements) and architecture (for technical constraints). Identify all screens and flows needed.

### Step 2: Information Architecture

Define:
- Navigation structure (primary nav, secondary nav, breadcrumbs)
- Screen inventory (every distinct screen/page)
- User flow diagrams (how screens connect)

### Step 3: Screen-by-Screen Specifications

For each screen, define:
- **Purpose** — what the user accomplishes here
- **Layout** — component hierarchy and spatial arrangement
- **Components** — what UI elements appear (forms, tables, cards, etc.)
- **States** — loading, empty, populated, error
- **Interactions** — what happens on click, hover, submit
- **Responsive behavior** — how layout adapts to mobile/tablet/desktop

### Step 4: Component Library

Define reusable components:
- Component name and purpose
- Props/variants
- States (default, hover, active, disabled, error)
- Accessibility requirements (aria labels, keyboard nav, focus management)

### Step 5: Design System Foundations

Define:
- Color palette (primary, secondary, semantic colors)
- Typography scale (headings, body, captions)
- Spacing system (4px/8px grid)
- Border radius, shadow, and elevation patterns

### Step 6: Accessibility Requirements

For each screen:
- Color contrast compliance (WCAG 2.1 AA minimum)
- Keyboard navigation order
- Screen reader annotations
- Focus management for modals and dynamic content

### Step 7: Save and Update Status

1. Save to `_bmad-output/planning-artifacts/ux-design.md`
2. Update `_bmad/bmm-workflow-status.yaml`: set `phase_3_solutioning.ux_design` to `"complete"`
3. Announce: "UX design complete. Next: create epics (`/bmad-cowork:epics`) or run readiness check (`/bmad-cowork:ready`)"
