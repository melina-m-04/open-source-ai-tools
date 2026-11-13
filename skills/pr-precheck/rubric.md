# Rubric: is this pull request ready to submit?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| scope-alignment | Plan, issue acceptance criteria, and branch diff | Changes match the approved plan and issue scope; no unjustified unrelated work | Required |
| plan-deviations | Plan deviation notes and branch diff | Material deviations are documented and justified | Required |
| implementation-completeness | Plan requirements, acceptance criteria, and branch diff | All required functionality is implemented | Required |
| test-evidence | Test results, commands, and relevant test changes | Relevant tests support the changed behavior; no unresolved relevant failures | Required |
| repository-requirements | Issue thread, PR template, and `CONTRIBUTING.md` | Applicable repository and issue requirements are satisfied | Required |
| pr-title-description | Draft PR title and description, compared with the diff | Accurately describes the change and follows applicable conventions | Required |
| evidence-quality | Evidence supplied for implementation and test claims | Material claims are supported by specific, consistent evidence | Required |

## Verdict rule

The final verdict must be exactly accept or reject.

Return accept only when every required check passes.

Return reject if any required check fails or is unclear.

Do not invent evidence, assume tests passed, or treat a claim as proof.

For every check, include a one-line evidence statement identifying the decisive
fact or quote.

Apply the grading procedure and the repository's explicit requirements when
resolving overlapping criteria.

If the rubric or procedure is missing or has no usable content, refuse to grade
rather than inventing grading rules.

Mode-specific rules:

In live mode, follow the scope and voice rules in SKILL.md and consult the
required repository sources.

In eval mode, use only the supplied package bundle. Do not fetch external
information or inspect unrelated local files.

In eval mode, do not apply live-mode scope or voice checks unless the supplied
evaluation rubric explicitly requires them.
