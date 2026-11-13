# Rubric: is this plan ready to post and build from?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| diagnosis | The plan's stated cause read against the reproduction evidence's observed behavior, inputs, and failure point | Pass if the diagnosis explains the reproduced failure without contradicting the evidence and identifies a cause that the proposed change can address; fail if it ignores, contradicts, or merely restates the symptom as the cause | Required |
| scope | The plan's scope statement read against the issue, diagnosis, and repo facts | Pass if the proposed change is bounded to the diagnosed problem and the plan clearly excludes unrelated changes; fail if the change expands beyond what the evidence and issue justify | Required |
| approach | The plan's proposed implementation read against its diagnosis, scope, and relevant repo facts | Pass if a stranger could use the described approach to make the intended change in the identified files without having to guess the core implementation decisions; fail if the approach is missing, targets only the symptom, or leaves essential implementation decisions unresolved | Required |
| test-plan | The plan's test plan read against the reproduction evidence's steps and expected failure, plus the repo facts | Pass if the tests exercise the real affected behavior, include the reproduced failure case, and define an observable result that would demonstrate the fix; fail if the tests cannot distinguish the broken behavior from the fixed behavior or do not exercise the affected path | Required |
| unknowns | The plan's risks and unknowns read against the reproduction evidence, issue context, and repo facts | Pass if uncertainties that could affect the implementation or outcome are identified as uncertainties and are not presented as established facts; fail if important unknowns are ignored or unsupported assumptions are treated as certain | Required |
| conventions | The plan comment read against the issue thread highlights and repo-facts block | Pass if the proposed plan responds to relevant issue-thread context and follows stated repository conventions that affect the change; fail if it contradicts relevant thread requirements or repo conventions, or ignores them when they materially constrain the work | Required |
| execution-readiness | The plan's diagnosis, scope, files, approach, and test plan read together | Pass if a maintainer or developer who did not write the plan could start implementing the bounded change and know what behavior to verify without needing to infer a missing core decision; fail if essential execution information is absent or contradictory | Required |

## Verdict rule

Accept if every required check passes. Preferred checks, if any are added later,
never change the verdict. Treat `unclear` as a fail. Reject if any required
check fails or is unclear.
