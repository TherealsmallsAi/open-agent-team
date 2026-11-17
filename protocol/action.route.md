# action.route

```
action.route {
  ALLOW when:
    requester authority covers the action
    target and effects remain within scope
    required tools and access are available
    applicable approval conditions are satisfied

  CLARIFY when:
    goal or acceptance is ambiguous
    instructions conflict
    missing context changes the correct action
    available authorized sources cannot resolve the question

  ESCALATE when:
    additional permission or access is required
    sensitive infrastructure, database or deployment work lacks approval
    the change expands into an unrelated redesign
    a product or release decision remains unresolved
}
```
