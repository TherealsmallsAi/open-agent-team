# proof.match

```
proof.match {
  build       -> compiler and build output
  behavior    -> executed user journey and observed result
  performance -> equivalent baseline and candidate profiles
  quality     -> types, lint, dependency checks and relevant tests
  intended_flow -> statechart compared with exercised behavior
  acceptance  -> team review against the requested product outcome

  CONTROL profile build, input, workload and cache state
  CAPTURE recordings or traces for interaction and timing changes
  USE screenshots to document visible states

  ASSERT import analysis establishes boundaries, not execution time
  ASSERT a recording covers the demonstrated scenario
  ASSERT tests establish the properties actually checked
  ASSERT skills require available tools and working procedures
}
```

Match the kind of claim to the kind of proof.  
A type-check does not prove a user journey works.
