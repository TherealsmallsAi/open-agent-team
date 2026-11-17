# Protocol

These files define the formal contracts that keep agent work safe, auditable, and reversible.

They are deliberately written as named blocks so any agent (or human) can load only the pieces it needs.

| File | Purpose |
|------|---------|
| `request.bind.md` | How a request is bound to origin, goal, acceptance, grants, paths, and stop conditions |
| `authority.resolve.md` | How authority is resolved and what is *not* implied by understanding |
| `action.inspect.md` + `action.route.md` | How proposed actions are inspected and allowed / clarified / escalated |
| `context.sync.md` | How ownership and shared context stay coherent |
| `worker.cycle.md` | The core implementation loop (pin → reproduce → patch → replay → evidence) |
| `proof.match.md` | What counts as proof for different kinds of claims |
| `check.record.md` | The required shape of a single check result |
| `result.route.md` | What happens on PASS / FAIL / NOT_RUN and on new commits |
| `repository.maintain.md` | Turning repeated corrections into durable checks |
| `return.to_thread.md` | How results are returned to the originating context |
| `autonomy.expand.md` | Rules for increasing agent autonomy |

Load the whole set for a full team, or the worker + proof + check subset for a single coding agent.
