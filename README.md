# open-agent-team

**Free & open-source agent team kit** inspired by Lauren Tan’s ( @poteto ) pstack / Grok Bot method.

Roles, verification skills, authority protocol, and evidence-first workflows so agents can ship verified PRs instead of hoping the human catches everything.

MIT licensed. No vendor lock-in. Works with Grok Bot, Cursor, Claude Code, Codex, local agents, or any system that can load markdown skills / system prompts.

## Why this exists

High agent volume without verification just multiplies slop.  
This kit gives you:

- Clear **roles** (Chief → Lead → Builder → Reviewer)
- A **verification skill** pattern that makes agents launch the real app, drive features, and keep evidence
- A formal **authority + proof protocol** so agents know what they are allowed to do and what counts as done
- Ready-to-use **task templates** and CI examples

Human stays the merge authority. Agents produce reviewable evidence.

## Quick start

1. Copy the `roles/` and `skills/` folders into your agent’s skill / prompt directory (or point your system at this repo).
2. Give each bot its role file as system prompt / persistent memory.
3. Put the four bots in one group chat (or equivalent coordination surface).
4. Send structured tasks (see `examples/task-templates/`).
5. Require evidence + Reviewer verdict before you merge.

For a full single-repo verification skill, use `skills/create-verification-skill/`.

## Structure

```
open-agent-team/
├── roles/                     # Persistent role instructions
│   ├── chief.md
│   ├── lead.md
│   ├── builder.md
│   └── reviewer.md
├── skills/
│   ├── create-verification-skill/   # Generator that writes a project-local verify skill
│   └── verify-template/             # Starter verification skill you can copy & adapt
├── protocol/                  # Formal authority / worker / proof contracts
├── examples/
│   ├── task-templates/        # YAML-style task briefs
│   └── ci/                    # Example GitHub Actions verification job
└── docs/
```

## Core principles (short)

1. **Understand ≠ authorize.** Passing checks ≠ release approval.
2. **Reproduce before you patch.** Pin baseline commit + worktree.
3. **Evidence must match the returned commit.** Screenshots, logs, exit codes, and the exact SHA.
4. **One writer per branch.** Parallel only on independent work.
5. **Stop conditions are explicit.** Scope expansion, missing tools, or product decisions escalate to human.
6. **Turn repeated corrections into automated checks** (lint, type, test, or verification skill).

## Credits & inspiration

- Lauren Tan ( @poteto ) — pstack, verification-first agent work, and the public talks on shipping thousands of PRs with confidence.
- The broader open-source agent skill community.

This is an independent implementation, not an official pstack fork. pstack itself remains the excellent upstream reference (MIT, in Cursor’s plugins).

## License

MIT — see LICENSE.

Build teams that verify. Keep the human in the merge seat.
