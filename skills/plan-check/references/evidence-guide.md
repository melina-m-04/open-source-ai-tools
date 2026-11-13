# Evidence guide: where evidence lives in a plan package

## Diagnosis and grounding

Where it lives: In an eval package, read the Repro evidence block for the
reproduced behavior, steps, environment, expected result, and actual result.
Read the Candidate plan for its stated cause. In live mode, use the
contributor's posted reproduction comment on the issue for the reproduction
evidence and the draft plan.md for the diagnosis.

What good looks like: The stated cause explains the failure that the
reproduction actually demonstrates and is consistent with the observed failure
point. A diagnosis that only repeats the symptom, ignores important reproduction
evidence, or contradicts it is not grounded.

## Scope

Where it lives: In an eval package, read the Issue block for the problem being
addressed, the Repo facts block for repository constraints and relevant facts,
and the Candidate plan for its stated change, exclusions, and affected files or
areas. In live mode, read the issue, repository facts or contribution
documentation identified in the package, and the draft plan.

What good looks like: The proposed work is limited to the diagnosed problem and
identifies meaningful boundaries on what will and will not change. The scope
should not introduce unrelated cleanup, redesign, or behavior changes that the
issue and evidence do not require.

## Executability

Where it lives: In an eval package, read the Candidate plan for the files or
areas to change, implementation approach, and order of work, then compare those
statements with the Repo facts block. In live mode, use plan.md and the relevant
repository files or documentation named by the evidence guide.

What good looks like: A developer unfamiliar with the plan can identify where
the change belongs and the core sequence of implementation without having to
guess a missing essential decision. The plan should connect the diagnosed cause
to concrete changes in the affected code or documentation.

## Test plan

Where it lives: In an eval package, read the Repro evidence block for the
original reproduction steps, expected result, and actual result, then read the
Candidate plan for its test plan and expected post-fix behavior. Use the Repo
facts block when repository-specific test commands or conventions affect how the
behavior can be verified. In live mode, use the contributor's posted repro
comment and the draft plan's test plan.

What good looks like: The planned test exercises the real affected behavior,
includes the reproduced failure case, and states an observable result that
should occur after the fix. A decisive test can distinguish the broken behavior
from the fixed behavior rather than only showing that a command ran.

## Honesty

Where it lives: In an eval package, read the Candidate plan for risks and
unknowns and, when present, its deviations. Compare those statements with the
Issue, Repro evidence, and Repo facts. In live mode, read the draft plan's
risks, unknowns, and ## Deviations section.

What good looks like: Material uncertainty is explicitly treated as uncertainty,
and unsupported assumptions are not presented as established facts. After
implementation, a change from the posted plan is recorded under ## Deviations
with what changed and why; a blank or omitted deviation record does not provide
evidence that the build matched the plan.

## Comms

Where it lives: In an eval package, read the Candidate plan comment against the
Issue and Thread highlights, then compare it with the Repo facts block for
contribution conventions, templates, maintainer requests, and any AI-use
disclosure requirement. In live mode, read the actual issue thread and
repository contribution guidance alongside the draft comment.

What good looks like: The comment communicates the proposed change in a way that
responds to relevant issue and maintainer context instead of using generic
boilerplate. It follows stated repository conventions and does not omit a
required disclosure or other material thread/repository requirement.
