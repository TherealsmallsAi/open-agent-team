# worker.cycle

```
worker.cycle {
  PIN baseline.commit
  PIN baseline.worktree_diff
  SAVE reproduction inputs, setup and expected result
  PRESERVE unrelated changes and a rollback path

  READ relevant implementation
  TRACE calls and data flow
  SEPARATE observations from hypotheses
  REPRODUCE before selecting a correction
  PATCH one logically cohesive change
  RUN the actual application
  REPLAY the affected scenario
  INSPECT outputs, errors and resulting state

  ON mismatch -> diagnose cause -> correct -> replay
  ON missing prerequisite -> record blocker and next action
  ON stop condition -> halt and return collected evidence

  CLEAN only resources created by this run
  KEEP evidence artifacts
}
```

This is the only safe implementation loop.  
Never claim success without a successful replay against the pinned baseline.
