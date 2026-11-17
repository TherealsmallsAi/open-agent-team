# result.route

```
result.route {
  PASS    -> retain current evidence and prepare required review
  FAIL    -> correct the demonstrated cause and rerun affected checks
  NOT_RUN -> name the prerequisite, responsible owner and next action

  ON code or environment change:
    REASSESS prior evidence
    RERUN checks whose assumptions or dependencies changed

  ASSERT evidence.commit == returned.commit
  ASSERT evidence.worktree == returned.worktree
}
```

A new commit invalidates previous PASS results for the affected checks.
