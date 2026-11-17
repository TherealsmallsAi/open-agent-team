# How to use open-agent-team

## 1. Install the roles

Copy `roles/*.md` into the place your agent system stores persistent instructions or system prompts.

Create four bots / agents and give each one its role file:

- Chief
- Lead
- Builder
- Reviewer

Put them in one shared conversation / group so handoffs are visible.

## 2. Add the verification skill

For a new project:

1. Load `skills/create-verification-skill/SKILL.md`
2. Ask the agent to generate a project-local verify skill for the repo
3. Review the generated skill + feature map
4. Merge it so later agents can load it cold

Or start from `skills/verify-template/SKILL.md` and adapt the commands yourself.

## 3. Use structured tasks

Send tasks in the style of `examples/task-templates/`.  
The more explicit the acceptance criteria and boundaries, the less the agents invent.

## 4. Require evidence

Builder must return:

- exact head commit SHA
- commands + exit codes
- artifacts (logs / screenshots / video)

Reviewer must re-run (or re-inspect) against that exact SHA and issue a PASS / FAIL / BLOCKED verdict.

A new commit invalidates the previous verdict.

## 5. Gate merges with CI

Copy and adapt `examples/ci/verification.yml`.  
Make the verification job a required status check on the default branch.

## 6. Measure

Track:

- human review time per PR
- number of Reviewer → Builder correction rounds
- whether every acceptance criterion was actually checked
- usage / spend

Only expand parallelism after the single-task loop is reliable.

## Working with Grok Bot / Cursor / Claude Code / etc.

The files are plain markdown. Any system that can:

- keep role context across turns
- load SKILL.md files
- run shell commands and capture output

can use this kit. No proprietary format required.
