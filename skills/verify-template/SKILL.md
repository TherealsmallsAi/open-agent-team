---
name: verify-template
description: Starter project-local verification skill. Copy and adapt for your application. Agents load this to launch, drive, and prove behavior.
---

# Verify (template)

Replace `<app>` and the commands below with values that actually work in *your* repository.

## Launch

```bash
# Example — replace with real commands from the repo
# yarn install --frozen-lockfile
# yarn predev:ci   # or whatever seeds data / configures mocks
# yarn dev         # starts frontend + api (or your equivalent)
```

Readiness signals (adjust ports / health checks):

- Frontend: http://localhost:3000
- API: http://localhost:3001

Wait until both respond before driving.

## Doctor

Confirm the running processes were started by *this* run (check PIDs, ports, or a unique env var you set).  
If the environment is already occupied by another agent, stop and report BLOCKED.

## Drive

Prefer the repository’s existing test harness.

Example (Cypress-style):

```bash
yarn cypress:run --spec cypress/tests/ui/auth.spec.ts
```

Or drive a single user journey with the project’s helpers / page objects.

Document the exact selectors and assertions you used in the feature map.

## Evidence

Always capture:

- Exact commands run
- Exit codes
- Relevant logs
- Screenshots or video of the exercised path
- The commit SHA that was tested

Store artifacts under a predictable location (e.g. `cypress/screenshots`, `artifacts/verify/`, etc.).

## Cleanup

Stop only the processes this skill started.  
Leave the rest of the machine / container alone.

## Feature map

See `features/` for per-feature instructions.  
Start with the most critical user flow (usually authentication or the main happy path).
