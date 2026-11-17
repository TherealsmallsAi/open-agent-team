# request.bind

```
request.bind {
  origin := [SLACK_THREAD | ISSUE | CHAT | TASK_ID]
  requester := [REQUESTER]
  repo := [REPO]
  goal := [TASK]
  acceptance := [OBSERVABLE_RESULT]
  grants := [EXISTING_AUTHORIZATIONS]
  paths := [PERMITTED_EDIT_PATHS]
  stop_when := [LIMIT_OR_BLOCKER]
}
```

Bind every request to these fields before work begins.  
Missing acceptance criteria or stop conditions → clarify before coding.
