# check.record

```
check.record {
  requirement := [ACCEPTANCE_ITEM]
  commit      := [TESTED_COMMIT]
  worktree    := [TESTED_DIFF]
  environment := [BUILD_AND_REQUIRED_STATE]
  execution   := [COMMAND_OR_ACTIONS]
  expected    := [REQUIRED_OBSERVATION]
  observed    := [ACTUAL_RESULT]
  exit_code   := [VALUE_IF_APPLICABLE]
  artifacts   := [EVIDENCE_PATHS]
  status      := PASS | FAIL | NOT_RUN
  blocker     := [MISSING_PREREQUISITE_IF_ANY]
}
```

Every claim of “it works” must be backed by at least one filled check.record.
