# UX Design Specification: [Project Name]

> Created by: UX Designer Agent (Uma)
> Date: [Date]
> Status: DRAFT | APPROVED
> Based on: prd.md, architecture.md

## Design System Foundations

### Color Palette
| Token | Value | Usage |
|-------|-------|-------|
| `--primary` | [hex] | Primary actions, links |
| `--secondary` | [hex] | Secondary actions |
| `--background` | [hex] | Page backgrounds |
| `--surface` | [hex] | Card/panel backgrounds |
| `--text-primary` | [hex] | Primary text |
| `--text-secondary` | [hex] | Secondary/muted text |
| `--success` | [hex] | Success states |
| `--warning` | [hex] | Warning states |
| `--error` | [hex] | Error states |

### Typography Scale
| Token | Size | Weight | Usage |
|-------|------|--------|-------|
| `heading-1` | 2rem | 700 | Page titles |
| `heading-2` | 1.5rem | 600 | Section titles |
| `heading-3` | 1.25rem | 600 | Subsections |
| `body` | 1rem | 400 | Body text |
| `caption` | 0.875rem | 400 | Labels, captions |

### Spacing
Base unit: 4px. Scale: 4, 8, 12, 16, 24, 32, 48, 64.

## Navigation Structure

[Describe the navigation hierarchy:]

```
├── [Top Nav Item 1]
│   ├── [Sub Item]
│   └── [Sub Item]
├── [Top Nav Item 2]
└── [Top Nav Item 3]
```

## Screen Specifications

### Screen: [Screen Name]
**URL:** `/[path]`
**Purpose:** [What the user accomplishes here]
**User Journey:** [Which journey this belongs to]

**Layout:**
```
┌─────────────────────────────────┐
│ [Header / Nav Bar]              │
├─────────┬───────────────────────┤
│ [Side]  │ [Main Content Area]   │
│ [bar]   │                       │
│         │ [Component 1]         │
│         │ [Component 2]         │
│         │                       │
├─────────┴───────────────────────┤
│ [Footer]                        │
└─────────────────────────────────┘
```

**Components:**
1. [Component Name] — [description, data displayed, interactions]
2. [Component Name] — [description]

**States:**
- **Loading:** [skeleton/spinner description]
- **Empty:** [empty state message and CTA]
- **Populated:** [normal state]
- **Error:** [error state and recovery action]

**Interactions:**
- [Click X] → [navigates to / opens modal / triggers action]
- [Submit form] → [validation rules, success/error behavior]

**Responsive Behavior:**
- Desktop (>1024px): [layout description]
- Tablet (768-1024px): [adaptations]
- Mobile (<768px): [adaptations]

### Screen: [Next Screen]
[Same structure]

## Component Library

### Component: [Component Name]
**Purpose:** [When and why to use this component]
**Variants:** [primary, secondary, outline, ghost]
**Props:**
- `variant`: primary | secondary | outline
- `size`: sm | md | lg
- `disabled`: boolean

**States:**
- Default: [description]
- Hover: [description]
- Active/Pressed: [description]
- Focused: [description + focus ring]
- Disabled: [description]

**Accessibility:**
- Role: [ARIA role]
- Keyboard: [Tab to focus, Enter/Space to activate]
- Screen reader: [Announcement text]

### Component: [Next Component]
[Same structure]

## User Flows

### Flow: [Flow Name]
```
[Screen A] → [Action] → [Screen B] → [Action] → [Screen C]
                                         ↓
                                    [Error State]
                                         ↓
                                    [Recovery Action]
```

## Accessibility Checklist

- [ ] All interactive elements keyboard accessible
- [ ] Focus order matches visual order
- [ ] Color contrast meets WCAG AA (4.5:1 text, 3:1 large text)
- [ ] All images have alt text
- [ ] Form inputs have labels
- [ ] Error messages associated with inputs
- [ ] Skip navigation link present
- [ ] Heading hierarchy logical (no skipped levels)
