---
name: pr-precheck
description: Grade a PR package (a candidate pull request read against the plan it claims to implement and the issue that plan belongs to) and decide whether it is ready to submit. Use when checking your own branch, draft PR title, and description before opening the pull request, or when grading an eval package bundle.
---

# pr-precheck: rubric-driven PR grading

## The question

Answer exactly one question about exactly one PR package: is this ready to
submit? Treat the package as a candidate pull request containing a title,
description, commits, diff, and test evidence, read against the plan it claims
to implement and the issue that plan belongs to. Do not grade a different
artifact, combine multiple packages, or decide from gut feel. Execute the rubric
and procedure supplied in this tool directory.

## Inputs and modes

Operate in exactly one of two modes.

Live mode: Review the contributor's own proposed PR using all of the following:

plan.md, including its ## Deviations notes, from the working copy.

The branch's committed diff relative to the PR's target branch, obtained from
the working copy with git diff <base>...HEAD. The base is the branch the
repository's contributing docs name as the PR target, or the upstream default
branch if they name none.

The draft PR title and description in pr_draft.md.

The test results and before/after reproduction output in test_evidence.md.

The issue's actual discussion thread in the scoped repository.

The repository's PR template, if it has one (usually
.github/PULL_REQUEST_TEMPLATE.md, a file in .github/PULL_REQUEST_TEMPLATE/, or
PULL_REQUEST_TEMPLATE.md in the root or docs/).

The repository's CONTRIBUTING.md (in the root, .github/, or docs/) and any
contributor docs it links to, including applicable contribution and AI-use
policies.

If plan.md, pr_draft.md, or test_evidence.md is missing, say which one, and
grade the checks that depend on it unclear. Compare the diff with the plan and
its deviations, test results with the plan's test plan, and the PR description
with the actual diff and repository requirements. Do not claim to have inspected
evidence you could not access.

Eval mode: Treat the supplied package bundle as the entire world. Use only facts
contained in that bundle. Do not fetch external information, inspect the working
repository, or read unrelated local files. Grade every rubric check and apply
the complete verdict rule to the package.

## The scope seam (live mode only)

In live mode, read scope.md before inspecting any other input. Confirm that the
target repository falls within the scope it defines and obey all scope
restrictions. If scope.md is missing or empty, stop without grading and tell the
contributor to fill it in. If the PR is outside the permitted scope, refuse to
grade it. Never guess or silently expand scope. In eval mode, ignore scope.md
entirely.

## The voice seam (live mode only)

In live mode, read voice-guide.md and check the outgoing PR title and
description against its writing rules. Report each identifiable violation in the
readable summary, with evidence from the draft and the relevant rule. The voice
guide does not independently change the verdict; only rubric checks and the
rubric's verdict rule determine acceptance or rejection. In eval mode, ignore
voice-guide.md entirely.

## Component reads

Read and execute procedure.md as written. Use rubric.md as the sole authority
for the named checks, their evidence requirements, pass conditions, weights, and
verdict rule. Use references/evidence-guide.md to locate and interpret each
evidence family in the package. Complete every check required by the rubric and
provide one evidence line for each check.

If rubric.md has no substantive content or procedure.md has no substantive
content, refuse to grade and explain which component must be completed. Do not
invent checks or procedures to compensate for empty files. If a procedure step
is silent or underspecified, report the gap rather than improvising an
alternative process. Do not silently substitute your own judgment for the
rubric's criteria.

## Verdict and output

Return only one of two verdicts: accept means the package is ready to submit;
reject means hold it and address the problems. Assemble the verdict strictly
according to the rule in rubric.md, including its treatment of unclear grades.
Do not introduce a third verdict, reservations verdict, or independent scoring
system.

Provide a readable per-check summary before the final output. End the reply with
the following fenced JSON block, valid and last, with nothing after it. Preserve
the schema, key names, field order, and allowed values exactly:

```json
{
  "item": "<PR URL or bundle id>",
  "checks": [
    {"name": "<check name>", "grade": "pass|fail|unclear",
     "evidence": "<one line: the fact or quote that decided it>"}
  ],
  "verdict": "accept|reject"
}
```

Use the actual PR URL or eval bundle ID for item. Include every rubric check in
checks, using pass, fail, or unclear as the grade and one concise,
evidence-based line for each. Ensure the JSON parses correctly. Never append
text after the closing JSON code fence.

## Grading discipline

Evidence first: Grade no check without citing the fact, artifact, or quote that
determined its result. Never use unsupported statements such as "looks fine."

Grade the artifact, not the polish: Judge completeness, correctness, scope,
testing, reviewability, and compliance against the plan, issue, diff, and
applicable repository standards. Do not reward attractive formatting or
confident wording in place of evidence.

The rubric decides: Apply each check's written pass condition consistently, even
when its outcome feels counterintuitive. Revise the rubric, not an individual
grade, when a criterion is wrong.

The procedure decides how: Follow the written procedure. Report missing or
ambiguous steps instead of silently inventing a process.

Unclear defaults to fail: Apply the rubric's explicit rule for unclear. If the
rubric does not specify how an unclear grade affects the verdict, treat it as
failing. Do not treat an unverifiable claim as proof that the PR is ready.
