---
name: create-verification-skill
description: Generate a project-local verification skill that drives the real app the way a user does. Use when a repo has no scripted way to prove UI/CLI/service behavior, or when asked to create a verify skill.
---

# Create a verification skill

Every serious project needs a scripted way to launch the app, exercise a feature the way a user would, and capture evidence. This skill generates that as a **project-local** skill that later agents can load cold.

## 1. Interview the repository (not the user)

Answer these from the codebase. Only ask the human what you cannot observe:

- **Surface**: web UI, CLI, desktop, API, mobile, library? Pick the primary one.
- **How to start**: install, seed data, start command(s), readiness signals (ports, health endpoints, log lines).
- **How to drive**: existing test harness (Cypress, Playwright, Jest, etc.), CLI flags, or browser automation.
- **Selectors / entry points**: real ones found in the repo.
- **Evidence**: screenshots, videos, logs, exit codes, DOM assertions, network traces.
- **Cleanup**: how to stop only the processes this run started.

## 2. Generate the skill

Write a project-local skill (example location depends on harness):

- Cursor / Grok-style: `.cursor/skills/verify-<app>/SKILL.md`
- Claude Code: `.claude/skills/verify-<app>/SKILL.md`
- Generic: `skills/verify-<app>/SKILL.md` or `.agents/skills/...`

Include these exact sections:

1. **Launch** — dependencies, seed, startup commands, readiness checks
2. **Doctor** — how to confirm the running instance belongs to *this* task
3. **Drive** — how to exercise the feature (prefer existing tests / helpers)
4. **Evidence** — what to keep (commands, exit codes, logs, screenshots, videos)
5. **Cleanup** — stop only processes created by this run

Also create a feature map directory:

```
.cursor/skills/verify-<app>/features/
  README.md
  authentication.md   # or whatever the first feature is
```

Each feature file should document:
- starting state
- route / entry point
- selectors or commands
- actions
- expected result
- failure conditions (missing seed, API down, error message never appears, etc.)

## 3. Execute once end-to-end

Run the generated instructions yourself.  
Confirm at least one negative path (e.g. invalid credentials) produces the expected error.  
Preserve the evidence after cleanup.

## 4. Open a draft PR for the skill files

Do **not** merge yourself.  
Do **not** modify application code or weaken existing assertions while generating the skill.

## 5. Handoff

The next agent should be able to:
- read the skill cold
- launch the app
- drive the documented feature
- return evidence that matches the commit under test
