---
name: builder-create-agent
description: "Design and create a new custom BMad agent with persona, expertise, and workflows."
---

Use when creating a new custom BMad agent with persona, expertise, workflows, and menu.

Trigger with: "create agent", "build agent", "new agent", "custom agent"

## Instructions

**Agent:** BMad Builder (Brix)
**Input:** User's description of the agent they want
**Output:** Agent markdown file in `agents/` directory

### Step 1: Interview

Ask the user:
1. **Domain** — What area does this agent specialize in? (e.g., DevOps, data engineering, marketing)
2. **Purpose** — What workflows will this agent run?
3. **Persona** — Name, personality traits, communication style
4. **Expertise** — What specific skills and knowledge should this agent have?
5. **Workflows** — What menu items should be available?

### Step 2: Design the Agent

Using BMad agent conventions, design:

```yaml
---
name: bmad-[kebab-case-name]
description: |
  Use when [trigger conditions].
  Trigger with: "[trigger phrases]"
model: sonnet
maxTurns: [appropriate limit]
---
```

Followed by:
- Agent name and persona description
- Expertise list
- Personality traits
- Operating rules (5-8 rules)
- Workflow description (if applicable)
- Menu table with commands and descriptions

### Step 3: Validate

Check the agent against BMad standards:
- [ ] Has a unique, descriptive name
- [ ] Description includes trigger phrases
- [ ] Persona has distinct personality (not generic)
- [ ] Operating rules are specific and actionable
- [ ] Menu items map to real workflows or skills
- [ ] MaxTurns is appropriate for the work

### Step 4: Create Supporting Skills

If the agent needs custom workflows, create corresponding SKILL.md files in `skills/` directories.

### Step 5: Save

Save agent file. Inform user to run `/reload-plugins` to pick up the new agent.
