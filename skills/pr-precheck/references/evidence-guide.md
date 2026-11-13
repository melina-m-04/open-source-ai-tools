# Evidence guide: where evidence lives in a PR package

## Plan fidelity (failure mode: silent drift)

Where it lives: In eval mode, inspect the plan-context block's scope pair,
planned files, requirements, and deviation notes; then compare them with the
candidate PR's unified diff, commit list, and description. In live mode, read
plan.md and its deviation notes, compare them with the branch diff against the
appropriate base branch, and check the draft PR title and description against
the implementation.

What good looks like: Every changed file and material behavior falls within the
plan's stated boundary or is covered by a documented, justified deviation.
Required planned behavior is implemented, and the description does not claim
functionality that the diff fails to deliver or omit a material limitation.
Silent drift includes unrelated additions, missing planned work without
explanation, and description claims that exceed or understate the actual change.

## Test evidence (failure mode: not tested)

Where it lives: In eval mode, inspect the plan-context block's test plan and
reproduction steps, the candidate PR's test-evidence section, and the outcomes
of the repository's checks or test suite when supplied. In live mode, compare
the test plan in plan.md with the captured test output, relevant test changes in
the branch diff, reproduction steps, and available repository check results.

What good looks like: Evidence identifies the behavior tested, the command or
reproduction steps used, the expected result, and the observed outcome. A
statement such as "tests pass" without supporting results does not establish
that the required behavior was tested. Missing test results or untested required
behavior must be reported rather than assumed successful.

## Diff quality (failure mode: unreviewable)

Where it lives: In eval mode, inspect the candidate PR's unified diff and commit
list. In live mode, inspect the branch diff against the appropriate base branch
and the relevant commit history.

What good looks like: The diff makes the intended fix or feature identifiable,
keeps changes relevant to the planned work, and provides enough context to
review the implementation. Look for debug leftovers, dead code, commented-out
blocks, accidental formatting churn, unrelated edits, and changes that obscure
the intended behavior. Record concrete examples rather than labeling a diff
"messy" without evidence.

## Standards and comms (failure mode: standards violation)

Where it lives: In eval mode, inspect the repo-facts block's PR template asks,
stated repository policy, contribution requirements, AI-use disclosure
requirements, and maintainer direction in the issue or PR thread. In live mode,
inspect the repository's PR template, CONTRIBUTING.md, applicable policy, the
issue thread, and the draft PR title and description.

What good looks like: Required PR template sections contain substantive,
accurate information; applicable contribution and policy requirements are
followed; required AI-use disclosures are present; and explicit maintainer
requests are addressed. Boilerplate that does not answer the template's
questions, missing required disclosures, or visibly ignored instructions are
concrete violations. Assess whether description claims match the diff under plan
fidelity, not as a separate communications failure. In eval mode, use only the
supplied bundle and do not fetch external information or inspect unrelated local
files.
